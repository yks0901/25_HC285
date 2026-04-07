
# 🧠 Strawberry Pollination Robot

딥러닝 기반 객체 인식과 SLAM을 결합하여 딸기꽃을 인식하고  
매니퓰레이터로 자동 수분을 수행하는 자율 로봇 시스템  

---

## 🔥 My Contributions

- YOLOv8 기반 딸기꽃 객체 인식 모델 구현  
- Depth 카메라 기반 3D 위치 추정 (핀홀 카메라 모델 + 왜곡 보정)  
- TF를 활용한 camera → map → base 좌표 변환 파이프라인 구축  
- RTAB-Map 기반 Visual SLAM 적용 (자율주행 및 위치 추정)  
- MoveIt 기반 매니퓰레이터 IK / motion planning / execution 구현  

---

## 🏗 System Architecture

Camera → YOLO → 3D 좌표 → TF 변환 → MoveIt → Manipulation  

<img width="500" src="https://github.com/yks0901/2025_/blob/main/asset/moveit_flow" />
<img width="500" src="https://github.com/yks0901/2025_/blob/main/asset/%EC%84%BC%EC%84%9C%20%ED%9D%90%EB%A6%84%EB%8F%84.png" />

<img width="500" src="https://github.com/yks0901/2025_/blob/main/asset/top2.png" />
<img width="500" src="https://github.com/yks0901/2025_/blob/main/asset/bottom2.png" />

<img width="600" src="https://github.com/yks0901/2025_/blob/main/asset/algorithm_flow" />


---
 ## 💡 작품 소개영상

[![한이음 드림업 프로젝트 소개](https://github.com/yks0901/2025_/blob/main/asset/%EC%8D%B8%EB%84%A4%EC%9D%BC.png)](https://youtu.be/DfwWIk6EnHk)
<a href="https://youtu.be/DfwWIk6EnHk">
  <img src="https://raw.githubusercontent.com/yks0901/2025_/main/asset/썸네일.png" width="600">
</a>
---


## ⚙️ Key Implementation

### 1. 3D 좌표 추정
- YOLO로 검출된 2D 픽셀 좌표를 3D 공간 좌표로 변환  
- 카메라 내부 파라미터 및 Depth 정보를 활용  
- 렌즈 왜곡 보정 적용 (`cv2.undistortPoints`)  

```python
def get_3d_point(self, pixel_x: int, pixel_y: int, depth_image: np.ndarray):
    try:
        if 0 <= pixel_x < self.WIDTH and 0 <= pixel_y < self.HEIGHT:
            depth = depth_image[int(round(pixel_y)), int(round(pixel_x))]

            if depth > 0:
                w, h = self.WIDTH, self.HEIGHT
                
                camera_matrix = np.array([[889.20439927, 0., 645.90808215],
                                          [0.,  891.14540673, 363.20254286],
                                          [0., 0., 1.]])
                
                dist_coeffs = np.array([[0.19324328, -0.6149969,   0.00296531, -0.00147052,  0.58687461]])
                
                new_camera_matrix, _ = cv2.getOptimalNewCameraMatrix(camera_matrix, dist_coeffs, (w, h), 1, (w, h))

                undistorted_pixel = cv2.undistortPoints(
                    np.array([[pixel_x, pixel_y]], dtype=np.float32),
                    camera_matrix,
                    dist_coeffs,
                    None,
                    new_camera_matrix
                ).reshape(-1)

                fx, fy = new_camera_matrix[0, 0], new_camera_matrix[1, 1]
                cx, cy = new_camera_matrix[0, 2], new_camera_matrix[1, 2]

                X = (undistorted_pixel[0] - cx) * depth / fx
                Y = (undistorted_pixel[1] - cy) * depth / fy
                Z = depth

                return (X * self.depth_scale, Y * self.depth_scale, Z * self.depth_scale)

        return None



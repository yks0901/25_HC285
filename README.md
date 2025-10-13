
## **💡1. 프로젝트 개요**

**1-1. 프로젝트 소개**
- 프로젝트 명 : 인공지능 기반 딸기꽃 수분 로봇
- 프로젝트 정의 : 인간을 대신하여 딸기꽃 인공 수분 로봇 개발
  
  <img width="400" height="400" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/20250511_182501.jpg/" /></br> 
  

**1-2. 개발 배경 및 필요성**
- 꿀벌 개체 수가 급격히 감소하고 있음(제주도 기준 2021년 2.5% → 2024년 29.9%). 농촌 고령화로 인한 노동력 부족이 심화되고 있으며, 딸기 시설재배에서 인공 수분의 필요성이 증가하나 기존 수작업 방식은 고령화된 농업 인구에게 큰 부담으로 작용하고 있음

**1-3. 프로젝트 특장점**
- 고가 장비 대신 상용화된 부품과 효율적 설계로 제작 비용 절감
- 딸기 외 다양한 작물 재배 환경에 적용 가능한 유연한 하드웨어/소프트웨어 구조
- 복잡한 조작 없이도 손쉬운 운용 및 유지보수가 가능한 사용자 친화적 설계
- AI 기반 정밀 탐지로 딸기꽃 추정 정확도 확보 
- 농약 사용 여부와 무관하게 작동하여 지속가능하고 친환경적인 농업 지원

**1-4. 주요 기능**
- 자율 주행 : 주변 환경 실시간 인식, 수집된 데이터 기반 딸기밭 내 자율적인 이동
- 정밀 수분 : 인식된 딸기꽃의 위치 정보 기반 매니퓰레이터를 정밀 제어하여 수분
- 딸기 꽃 인식 : 사전에 학습된 딥러닝 기반 객체 인식 알고리즘을 통해 딸기꽃 식별
- 높이 조절 통한 다양한 작업 범위 : 리프트 시스템 도입으로 매니퓰레이터의 높이 제어 가능

**1-5. 기대 효과 및 활용 분야**
- 기대 효과 : 생산성 향상, 노동력 절감, 수작업 의존도 감소, 스마트팜 자동화 촉진
- 활용 분야 : 딸기 재배 농장, 스마트팜/농업 연구소, 노업 자동화 산업 등

**1-6. 기술 스택**
- 프론트엔드 : React, Next.js, Tailwind CSS
- 백엔드 : Python(FastAPI), Node.js, Django
- AI/ML : PyTorch, TensorFlow
- 데이터베이스 : PostgreSQL, MongoDB, Elasticsearch
- 클라우드 : AWS
- 배포 및 관리 : GitHub Actions

---

## **💡2. 팀원 소개**
| <img width="80" height="100" src="https://github.com/yks0901/2025_/blob/main/asset/%ED%86%A0%EC%9D%B5%20%EA%B1%B4%EC%88%98%20%EC%82%AC%EC%A7%84.jpg" > | <img width="80" height="100" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/1759487705047.jpg" > | <img width="80" height="100" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/KakaoTalk_20251013_232203558.jpg" > | <img width="80" height="100" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/KakaoTalk_20251014_000518190.jpg" > | 
|:---:|:---:|:---:|:---:|
| **윤건수** | **박지훈** | **김소정** | **조원우** |
| • 개발총괄 <br> • UI/UX 기획 | • 백엔드 <br> • 프론트엔드 | • API 개발 <br> • DB 서버 구축 |• 데이터 분석 <br> • 전처리 |



---
## **💡3. 시스템 구성도**

- s/w 구성도(moveit 관련)
<img width="500" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/moveit_flow" />

- s/w 구성도(센서 흐름도)
<img width="500" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/%EC%84%BC%EC%84%9C%20%ED%9D%90%EB%A6%84%EB%8F%84.png" />

- h/w 구성도(상부)
<img width="500" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/top2.png" />

- h/w 구성도(하부)
<img width="600" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/bottom2.png" />

- 흐름도
<img width="600" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/algorithm_flow" />

---
## **💡4. 작품 소개영상**
> **참고**: 썸네일과 유튜브 영상을 등록하는 방법입니다.
```Python
아래와 같이 작성하면, 썸네일과 링크등록을 할 수 있습니다.
[![영상 제목](유튜브 썸네일 URL)](유튜브 영상 URL)

작성 예시 : 저는 다음과 같이 작성하니, 아래와 같이 링크가 연결된 썸네일 이미지가 등록되었네요! 
[![한이음 드림업 프로젝트 소개](https://github.com/user-attachments/assets/16435f88-e7d3-4e45-a128-3d32648d2d84)](https://youtu.be/YcD3Lbn2FRI?si=isERqIAT9Aqvdqwp)
```
[![한이음 드림업 프로젝트 소개](https://github.com/yks0901/2025_/blob/main/asset/20250511_182501.jpg/)](https://youtu.be/DfwWIk6EnHk)


---
## **💡5. 핵심 소스코드**
- 소스코드 설명 : 핀홀 카메라 모델을 구현한 코드이며, 인식된 객체의 3d 좌표를 추정합니다.

```python
    def get_3d_point(self, pixel_x: int, pixel_y: int, depth_image: np.ndarray):
        """Get 3D point from pixel coordinates with lens distortion correction."""
        
        try:
            if 0 <= pixel_x < self.WIDTH and 0 <= pixel_y < self.HEIGHT:
                depth = depth_image[int(round(pixel_y)), int(round(pixel_x))]

                if depth > 0:
                    w, h = self.WIDTH, self.HEIGHT
                    
                    camera_matrix = np.array([[889.20439927, 0., 645.90808215],
                                              [0.,  891.14540673, 363.20254286],
                                              [0., 0., 1.]])
                    
                    dist_coeffs = np.array([[0.19324328, -0.6149969,   0.00296531, -0.00147052,  0.58687461]])
                    
                    # Optimal new camera matrix
                    new_camera_matrix, _ = cv2.getOptimalNewCameraMatrix(camera_matrix, dist_coeffs, (w, h), 1, (w, h))

                    # Undistort pixel coordinates
                    undistorted_pixel = cv2.undistortPoints(
                        np.array([[pixel_x, pixel_y]], dtype=np.float32),
                        camera_matrix,
                        dist_coeffs,
                        None,
                        new_camera_matrix
                    ).reshape(-1)

                    # Updated camera parameters after distortion correction
                    fx, fy = new_camera_matrix[0, 0], new_camera_matrix[1, 1]
                    cx, cy = new_camera_matrix[0, 2], new_camera_matrix[1, 2]

                    X = (undistorted_pixel[0] - cx) * depth / fx
                    Y = (undistorted_pixel[1] - cy) * depth / fy
                    Z = depth

                    return (X * self.depth_scale, Y * self.depth_scale, Z * self.depth_scale)

            return None

        except Exception as e:
            self.get_logger().warn(f"Error calculating 3D point: {str(e)}")
            return None
```


```python
    def get_3d_point(self, pixel_x: int, pixel_y: int, depth_image: np.ndarray):
        """Get 3D point from pixel coordinates with lens distortion correction."""
        
        try:
            if 0 <= pixel_x < self.WIDTH and 0 <= pixel_y < self.HEIGHT:
                depth = depth_image[int(round(pixel_y)), int(round(pixel_x))]

                if depth > 0:
                    w, h = self.WIDTH, self.HEIGHT
                    
                    camera_matrix = np.array([[889.20439927, 0., 645.90808215],
                                              [0.,  891.14540673, 363.20254286],
                                              [0., 0., 1.]])
                    
                    dist_coeffs = np.array([[0.19324328, -0.6149969,   0.00296531, -0.00147052,  0.58687461]])
                    
                    # Optimal new camera matrix
                    new_camera_matrix, _ = cv2.getOptimalNewCameraMatrix(camera_matrix, dist_coeffs, (w, h), 1, (w, h))

                    # Undistort pixel coordinates
                    undistorted_pixel = cv2.undistortPoints(
                        np.array([[pixel_x, pixel_y]], dtype=np.float32),
                        camera_matrix,
                        dist_coeffs,
                        None,
                        new_camera_matrix
                    ).reshape(-1)

                    # Updated camera parameters after distortion correction
                    fx, fy = new_camera_matrix[0, 0], new_camera_matrix[1, 1]
                    cx, cy = new_camera_matrix[0, 2], new_camera_matrix[1, 2]

                    X = (undistorted_pixel[0] - cx) * depth / fx
                    Y = (undistorted_pixel[1] - cy) * depth / fy
                    Z = depth

                    return (X * self.depth_scale, Y * self.depth_scale, Z * self.depth_scale)

            return None

        except Exception as e:
            self.get_logger().warn(f"Error calculating 3D point: {str(e)}")
            return None
```

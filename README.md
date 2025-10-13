
## **💡1. 프로젝트 개요**

**1-1. 프로젝트 소개**
- 프로젝트 명 : 인공지능 기반 딸기꽃 수분 로봇
- 프로젝트 정의 : 딸기꽃을 인식하고 매니퓰레이터를 이용해 인공 수분을 수행하는 인공지능 기반 자율주행 로봇 시스템
  
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
- 로봇 운영체제(ROS2) : ROS2 Humble, Nav2, Moveit2, RTAB-Map, micro-ROS
- 백엔드 : Python(FastAPI), Node.js, Django
- AI/Computer Vision : YOLOv8, PyTorch, OpenCV 
- 제어 및 통신: Dynamixel SDK, OpenCR
- 시뮬레이션/ 모델링 : Gazebo, RViz2, Autodesk Inventor 
- 개발 및 관리 : Git, GitHub, VSCode

---

## **💡2. 팀원 소개**
| <img width="80" height="100" src="https://github.com/yks0901/2025_/blob/main/asset/%ED%86%A0%EC%9D%B5%20%EA%B1%B4%EC%88%98%20%EC%82%AC%EC%A7%84.jpg" > | <img width="80" height="100" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/1759487705047.jpg" > | <img width="80" height="100" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/KakaoTalk_20251013_232203558.jpg" > | <img width="80" height="100" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/KakaoTalk_20251014_000518190.jpg" > | 
|:---:|:---:|:---:|:---:|
| **윤건수** | **박지훈** | **김소정** | **조원우** |
| • 제어 로직 개발 <br> • 객체 인식 | • 하드웨어 설계 <br> • 역기구학 계산 | • RTAB-Map <br> • 서류 작성 |• 멘토링 <br> • 피드백 |



---
## **💡3. 시스템 구성도**

- S/W 구성도(moveit 관련)
<img width="500" height="600" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/moveit_flow" />

- S/W 구성도(센서 흐름도)
<img width="500" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/%EC%84%BC%EC%84%9C%20%ED%9D%90%EB%A6%84%EB%8F%84.png" />

- H/W 구성도(상부)
<img width="500" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/top2.png" />

- H/W 구성도(하부)
<img width="600" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/bottom2.png" />

- Flow Chart
<img width="600" height="500" alt="image" src="https://github.com/yks0901/2025_/blob/main/asset/algorithm_flow" />

---
## **💡4. 작품 소개영상**

[![한이음 드림업 프로젝트 소개](https://github.com/yks0901/2025_/blob/main/asset/%EC%8D%B8%EB%84%A4%EC%9D%BC.png)](https://youtu.be/DfwWIk6EnHk)


---
## **💡5. 핵심 소스코드**
- 소스코드 설명 : 핀홀 카메라 모델을 구현한 코드이며, 인식된 객체의 3d 좌표를 추정합니다. (yolov8_dis.py)

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

- 소스코드 설명 : 카메라 기준 좌표계에서 map프레임으로 좌표 변환합니다. (pose_transform_node.cpp)
 
```c++
    std::optional<geometry_msgs::msg::PoseStamped> transformCameraToMap(const geometry_msgs::msg::PoseStamped& camera_pose)
  {
    const std::string source_frame = "camera_color_optical_frame";
    const std::string target_frame = "map";

    if (!tf_buffer_.canTransform(target_frame, source_frame, tf2::TimePointZero)) {
      for (int i = 0; i < 10; ++i) {
        RCLCPP_WARN(this->get_logger(), "TF 기달리는 중: %s → %s", source_frame.c_str(), target_frame.c_str());
        std::this_thread::sleep_for(std::chrono::milliseconds(200));
        if (tf_buffer_.canTransform(target_frame, source_frame, tf2::TimePointZero)) {
          break;
        }
      }
      if (!tf_buffer_.canTransform(target_frame, source_frame, tf2::TimePointZero)) {
        RCLCPP_ERROR(this->get_logger(), "TF 사용할수없음: %s → %s", source_frame.c_str(), target_frame.c_str());
        return std::nullopt;
      }
    }

    try {
      auto transform = tf_buffer_.lookupTransform(target_frame, source_frame, tf2::TimePointZero);
      geometry_msgs::msg::PoseStamped map_pose;
      tf2::doTransform(camera_pose, map_pose, transform);
      return map_pose;
    } catch (const tf2::TransformException& ex) {
      RCLCPP_ERROR(this->get_logger(), "⚠ TF Error: %s", ex.what());
      return std::nullopt;
    }
  }
```

- 소스코드 설명 : map 기준에서 로봇의 base 기준으로 좌표변환 합니다. 이후 별도의 코드로 이를 퍼블리시합니다. (pose_transform_node.cpp)
 
```c++
   
void poseCallback(const bumblebee_interfaces::msg::ObjectData::SharedPtr msg)
{
  if (!mani_busy) {
    RCLCPP_INFO(this->get_logger(), "poseCallback 진입: name=%s, x=%.2f, y=%.2f, z=%.2f",
                msg->name.c_str(), msg->x, msg->y, msg->z);
    
    geometry_msgs::msg::PoseStamped pose_in_camera;
    pose_in_camera.header.stamp = this->now();
    pose_in_camera.header.frame_id = "camera_color_optical_frame";
    pose_in_camera.pose.position.x = msg->x;
    pose_in_camera.pose.position.y = msg->y;
    pose_in_camera.pose.position.z = msg->z;
    pose_in_camera.pose.orientation.w = 1.0;


    auto maybe_map_pose = transformCameraToMap(pose_in_camera);
    if (!maybe_map_pose) {
      RCLCPP_WARN(this->get_logger(), "map 변환 실패, return");
      return;
    }

    int id_to_use;
    if (is_duplicate(maybe_map_pose->pose, id_to_use)) {
      object_map_[id_to_use] = *maybe_map_pose;
      RCLCPP_INFO(this->get_logger(), "기존 객체 ID %d 위치 갱신(map 기준): x=%.2f y=%.2f z=%.2f",
                  id_to_use,
                  maybe_map_pose->pose.position.x,
                  maybe_map_pose->pose.position.y,
                  maybe_map_pose->pose.position.z);
    } else {
      id_to_use = current_id_;
      object_map_[id_to_use] = *maybe_map_pose;
      RCLCPP_INFO(this->get_logger(), "새로운 객체 ID %d 등록 (map 기준): x=%.2f y=%.2f z=%.2f",
                  id_to_use,
                  maybe_map_pose->pose.position.x,
                  maybe_map_pose->pose.position.y,
                  maybe_map_pose->pose.position.z);
      current_id_++;
    }

   
      if (checkRobotStopped(3.0)) {
    try {
      auto transform = tf_buffer_.lookupTransform("base_footprint", "map", tf2::TimePointZero);
      geometry_msgs::msg::PoseStamped pose_in_base;
      tf2::doTransform(*maybe_map_pose, pose_in_base, transform);
      base_footprint_pose_map_[id_to_use] = pose_in_base;
      RCLCPP_INFO(this->get_logger(), "base_footprint 기준 좌표 저장: ID=%d", id_to_use);
    } catch (const tf2::TransformException& ex) {
      RCLCPP_WARN(this->get_logger(), "map -> base_footprint 좌표 변환 실패: %s", ex.what());
    }

      }
  }
  else
    return;
}
```

- 소스코드 설명 : 발행된 좌표로 매니퓰레이션합니다. (moveit_pose_subscriber_node.cpp)

```c++
    void manipulation(){

    if(left_vel != 0.0 || right_vel != 0.0)
      return;
    
    RCLCPP_WARN(node_->get_logger(), "실행 발생!");

  for (auto& [id, obj] : target_map_) {
    if (obj.fertilized || (obj.z >1.05)) continue;

    if (last_joint_state_.name.empty()) {
      RCLCPP_WARN(node_->get_logger(), "조인트값 없음 ID %d", id);
      continue;
    }

    //std_msgs::msg::Bool busy_msg;
    busy_msg.data = true;
    busy_pub_->publish(busy_msg);


    // IK, planning, execution ... (이하 기존 로직 동일)


    //  RobotState 생성 및 IK 기반 자세 계산
    moveit::core::RobotStatePtr current_state(new moveit::core::RobotState(kinematic_model_));
    current_state->setToDefaultValues();

    const moveit::core::JointModelGroup* joint_model_group =
        kinematic_model_->getJointModelGroup(PLANNING_GROUP);

    geometry_msgs::msg::Pose pose;
    pose.position.x = obj.x - 0.008; // 오프셋 값
    pose.position.y = obj.y - 0.018; // 오프셋 값
    pose.position.z = obj.z + 0.046; // 오프셋 값
    pose.orientation.x = 0.0;
    pose.orientation.y = 0.0;
    pose.orientation.z = 0.0;
    pose.orientation.w = 1.0;

    std::vector<double> solution;
    bool found_ik = false;

    if (current_state->setFromIK(joint_model_group, pose, move_group_.getEndEffectorLink(), 0.1)) {
      current_state->copyJointGroupPositions(joint_model_group, solution);
      found_ik = true;
    }

    if (!found_ik) {
      RCLCPP_WARN(node_->get_logger(), "IK 해를 찾을 수 없음. ID %d", id);
      continue;
    }

    //  플래닝 및 실행
    move_group_.setJointValueTarget(solution);

    moveit::planning_interface::MoveGroupInterface::Plan plan;
    if (move_group_.plan(plan) == moveit::core::MoveItErrorCode::SUCCESS) {
      if (move_group_.execute(plan) == moveit::core::MoveItErrorCode::SUCCESS) {
        obj.fertilized = true;
        RCLCPP_INFO(node_->get_logger(), " 수분 위치 도달 ID %d", id);
      } else {
        RCLCPP_WARN(node_->get_logger(), "실행 실패 ID %d", id);
        continue;
      }
    } else {
      RCLCPP_WARN(node_->get_logger(), " 계획 실패 ID %d", id);
      continue;
    }

    move_group_.clearPoseTargets();
    std::this_thread::sleep_for(std::chrono::seconds(1));

    //  수분 동작 수행
    perform_pollination_with_joint7(solution, 0.177266);//perform_pollination_with_joint7(solution, 0.177266);
    std::this_thread::sleep_for(std::chrono::milliseconds(500));
    perform_pollination_with_joint7(solution, -0.177266);
     std::this_thread::sleep_for(std::chrono::milliseconds(500));

    //  초기 자세 복귀
    search_JointState();
    std::this_thread::sleep_for(std::chrono::seconds(1));
    busy_msg.data = false;
    busy_pub_->publish(busy_msg);
  }
  check_target();
  }
  
```

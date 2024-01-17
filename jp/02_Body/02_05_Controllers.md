### Controllers

<details open>
<summary>details</summary>

#### ROS

#### Head unit




```plantuml
@startuml
title ROS NODE on Head unit
scale max 640 width
top to bottom direction

!$topic_hv_left_text = "**/holistic_view/left"
!$topic_hv_right_text = "**/holistic_view/right"
!$topic_eye_control_text = "**/mitumeru/eye_control"
!$topic_neck_control_text = "**/mitumeru/neck_control"

!$msg_pose_data = "maid_robot_system_interfaces/msg/PoseData"
!$msg_eye_gaze = "maid_robot_system_interfaces/msg/EyeGaze"
!$msg_neck_angle = "maid_robot_system_interfaces/msg/NeckAngle"


  storage video_capture_node_left as "video_capture_node\n[left]"  #Physical  {
      rectangle TOPIC_CAMERA_RAW_LEFT [
      /**/image/raw/left
      ----
      sensor_msgs/msg/Image
      ]
  }

  storage DETECT_AR_NODE_LEFT as "detect_ar_node\n[left]"  #Application  {
    portin detect_ar_node_left_port as " "
      rectangle DETECT_AR_NODE_LEFT_OUT [
      /**/data/ar/left
      ----
      maid_robot_system_interfaces/msg/ArMarkers
      ]
  }

  storage MEDIAPIPE_NODE_LEFT as "mediapipe_node\n[left]"  #Application  {
    portin mediapipe_node_prot as " "
      rectangle MEDIAPIPE_NODE_LEFT_OUT [
      /**/data/pose/left
      ----
      maid_robot_system_interfaces/msg/PoseDetection
      ]
  }


  storage MEDIAPIPE_EXT_NODE_LEFT as "mediapipe_ext_node\n[left]"  #Application  {
    portin mediapipe_ext_node_prot_01 as " "
    portin mediapipe_ext_node_prot_02 as " "
      rectangle MEDIAPIPE_EXT_NODE_LEFT_OUT [
      /**/data/pose/left
      ----
      sensor_msgs/msg/Image
      ]
  }


TOPIC_CAMERA_RAW_LEFT --( detect_ar_node_left_port
TOPIC_CAMERA_RAW_LEFT --( mediapipe_node_prot
DETECT_AR_NODE_LEFT_OUT --( AR_OUT_LEFT
MEDIAPIPE_EXT_NODE_LEFT_OUT --( IMAGE_OUT_LEFT

TOPIC_CAMERA_RAW_LEFT --( mediapipe_ext_node_prot_01
MEDIAPIPE_NODE_LEFT_OUT --( mediapipe_ext_node_prot_02


@enduml
```








---


### mitumeru_node

### kubi_node


### face_recognition_node

USB-Webカメラより画像を取得し、姿勢制御情報を通達する。


```plantuml
@startuml
scale max 1024 width

title face_recognition_node
!include <tupadr3/devicons/python.puml>
!include <material/folder.puml>

salt
{{T
    + <$python> recognition_in_node.py      | recognition_in_nodeの本体
     ++ <$ma_folder> utils
     +++ <$python> usb_video_device.py        | USB-WebカメラのデバイスIDを取得する
     +++ <$python> cv_fps_calc.py             | FPSの計算を行う
     ++ <$ma_folder>features
     +++ <$ma_folder>ros
     ++++ <$python> face_recognition_ros.py   | recognition_in_nodeのROSインターフェース
     +++ <$ma_folder>mp
     ++++ <$python> imageanalysis.py          | mediapipeの画像解析
     ++++ <$python> poseinformation.py        | mediapipeの姿勢情報
     ++++ <$python> schematicdiagram.py       | 画像データに情報を書き込む
  }
}
@enduml
```

### Todo

計算処理はこのノードから切り離すべき？



## ノード名規則

<機能名>_<type>_node

| type   |                                                |     |
| ------ | ---------------------------------------------- | --- |
| calc   | 入力に従って演算するノードタイプ               |     |
| op     | 受け付けた処理にしたがって動作するノードタイプ |     |
| in     | 入力装置からの処理をROSに変換するノードタイプ  |     |
| notify | 外部へ通達するノードタイプ                     |     |




</details>


# Install


```bash
sudo apt install -y ros-humble-image-transport

# optional
sudo apt install -y ros-humble-compressed-image-transport ros-humble-theora-image-transport  ros-humble-image-transport-plugins
```



```bash
sudo apt install -y jq
```

## 使用しているソフトウェア

| Software Name | Package manager | 仕様している理由                   |
| ------------- | --------------- | ---------------------------------- |
| jq            | apt             | bash で config.json を処理するため |
|               |                 |                                    |

### ROS2 node

| Software Name                         | Unit      | 仕様している理由                   |
| ------------------------------------- | --------- | ---------------------------------- |
| ros-humble-image-transport            | Head Unit | カメラ描画を取得するため           |
| ros-humble-compressed-image-transport | Head Unit | 圧縮されたカメラ描画を取得するため |
| ros-humble-theora-image-transport     | Head Unit | カメラ描画をライブ配信をする       |
| ros-humble-image-transport-plugins    | Head Unit |                                    |
|                                       |           |                                    |
|                                       |           |                                    |
|                                       |           |                                    |


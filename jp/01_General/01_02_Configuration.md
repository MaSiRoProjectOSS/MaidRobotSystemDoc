### Configuration


<details>
<summary>details</summary>

#### ROS環境

* フォルダ```${PROJECT_FOLDER}/data/config.json```にインスール先などの設定が可能です。

```json
{
    "CAST": {
        "MRS_CAST_NAME": "miko",
        "MRS_CAST_ID": 1000
    },
    "MRS_ROS": {
        "MRS_ROS_DOMAIN_ID": 0,
        "MRS_ROS_OUTPUT_TYPE": "log",
        "MRS_ROS_NAMESPACE": "/maid_robot_system/${MRS_CAST_NAME}"
    },
    "MRS": {
        "MRS_WORKSPACE": "/opt/MaidRobotSystem",
        "MRS_SKIN_HOME": "/opt/MaidRobotSystem/data/skin/${MRS_CAST_NAME}"
    },
    "BUILD": {
        "BUILD_HEAD_UNIT": "ON",
        "BUILD_ARM_UNIT": "ON",
        "BUILD_WAIST_DOWN_UNIT": "ON",
        "BUILD_MOBILITY_UNIT": "ON",
        "BUILD_CLOUD_UNIT": "ON",
        "BUILD_MANAGEMENT_UNIT": "ON",
        "BUILD_DEVELOP": "ON"
    }
}

```

</details>


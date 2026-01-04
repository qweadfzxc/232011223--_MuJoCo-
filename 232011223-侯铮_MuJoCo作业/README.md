# MuJoCo MPC 汽车仪表盘项目

## 一、项目信息

- 学号：232011223
- 姓名：侯铮
- 班级：计科2305班  
- 完成日期：2025年12月30日  

---

## 二、项目概述
本项目基于 MuJoCo 物理仿真引擎与其 MPC（Model Predictive Control）控制框架，实现了一个简单汽车模型的运动控制与实时仪表盘可视化系统。项目通过 MJCF 文件构建汽车的动力学模型，并在仿真运行过程中实时获取车辆的速度、转速、位置等状态数据。在此基础上，使用 OpenGL 在 MuJoCo 渲染窗口中绘制自定义汽车仪表盘界面，包括速度表、转速表以及关键状态的数值显示。该项目综合运用了物理建模、控制算法以及图形渲染等技术，具有较强的实践与教学意义。

---

## 三、运行环境与依赖

### 3.1 软件环境
- 操作系统：Ubuntu 22.04 LTS  
- 编译器：gcc 11.3.0  
- 构建工具：CMake 3.22.1  
- 物理引擎：MuJoCo 2.x  

### 3.2 依赖说明
- 系统自带 OpenGL 库  
- 标准 C++17 编译环境  

---

## 四、编译与运行说明

### 4.1 编译步骤
```bash
cd mujoco_mpc
mkdir -p build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
cmake --build . -j4

```

4.2 运行方式

./bin/mjpc --mjcf=../mjpc/tasks/car/car_simple.xml

运行后将启动 MuJoCo 仿真窗口，小车在 MPC 控制下运动，同时显示实时仪表盘。
五、功能说明
5.1 已实现功能

    汽车动力学模型仿真
    
    基于 MPC 的车辆前进与转向控制
    
    实时速度表显示
    
    实时转速表显示
    
    车辆位置等状态的数值显示

5.2 进阶与扩展功能

    OpenGL 自定义二维仪表盘渲染
    
    仪表盘与仿真状态的实时同步更新
    
    可扩展的仪表盘数据接口设计

六、项目文件结构说明

    mjpc/tasks/car/car_model.xml
    定义汽车的结构、关节、执行器与动力学参数。
    
    mjpc/tasks/car/car_simple.xml
    定义仿真任务、传感器、控制器参数以及目标设置。
    
    dashboard_data.h
    定义仪表盘所需的数据结构以及数据获取接口。
    
    dashboard_render.h / dashboard_render.cc
    实现仪表盘的 OpenGL 渲染逻辑，包括速度表与转速表。

七、已知问题

    仪表盘在不同窗口分辨率下缩放适配性有限
    
    当前仪表盘仅支持显示，不支持交互操作

八、参考资料

    MuJoCo 官方文档
    
    MuJoCo MPC 示例工程
    
    OpenGL Programming Guide
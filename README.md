# CPR-PurePursuit-Controller-Ackerman
Controlador de Seguimiento de Trayectoria Pure Pursuit para ROS, con un vehículo con dirección Ackermann.

## Entorno:
- Ubuntu 18.04
- ROS Melodic

```bash 
    $roslaunch pure_pursuit_controller pure_pursuit.launch
```

### Tuning:
En General, el ***look_ahead_ratio*** y ***look_ahead_constant*** en *pure_pursuit_controller.yaml* determina la Look-ahead-Distance en el Pure-Pursuit, que afecta principalmente al rendimiento de Seguimiento de Trayectoria. Mirar [Matlab: PurePursuit](https://ww2.mathworks.cn/help/robotics/ug/pure-pursuit-controller.html) para más información.

## MANUAL DE USUARIO
## 1.Preparación

Instalar paquetes de ROS y compilar con catkin:

```
sudo apt install ros-melodic-joint-state-publisher-gui
sudo apt install ros-melodic-ros-control
sudo apt install ros-melodic-ros-controllers
sudo apt install ros-melodic-gmapping
sudo apt install ros-melodic-ackermann-msgs
sudo apt install ros-melodic-navigation
sudo apt install ros-melodic-teb-local-planner
```


```
cd ~/ros_workspace/src
cd ..
catkin_make
source devel/setup.bash
```

## 2. Tutorial de uso

### Lanzar robot y controlador

```
roslaunch racebot_gazebo tianracer.launch

roslaunch racebot_gazebo slam_navi.launch 
```

## 3.Referencias
[Ackermann vehicle](https://github.com/hdh7485/ackermann_vehicle)

[Pure Pursuit - ROS](https://github.com/reso1/PurePursuitControllerROS)

[Pure Pursuit - 2](https://github.com/jmaye/pure-pursuit-controller-ros)

[Matlab - PurePursuit](https://es.mathworks.com/help/robotics/ug/pure-pursuit-controller.html)

# CPR-PurePursuit-Controller-Ackerman
Controlador de Seguimiento de Trayectoria Pure Pursuit para ROS (Modificado desde [aquí](https://github.com/jmaye/pure-pursuit-controller-ros)),con un vehículo con dirección Ackermann.
![](images/rviz.png)

## Entorno:
- Ubuntu 18.04
- ROS Melodic

## Requisitos:
1. **tf desde map hasta base_link**, que se puede obtener utilizando el nodo *[AMCL](http://wiki.ros.org/amcl)*

2. La *reference_path* se publica en el marco *'map'*.

## Uso:

### Configuración:

**Ver pure_pursuit_controller.yaml**

### Lanzamiento:
0. Hacer ejecutable el archivo .py
```bash 
    $chmod +x [ruta_a_tu_espacio_de_trabajo]/scripts/show_trajectory.py
    $chmod +x [ruta_a_tu_espacio_de_trabajo]/scripts/test_send_ref_path.py
```
1. Correr AMCL:

```bash 
    $roslaunch amcl amcl_diff.launch
```

2. Correr el Pure Pursuit Controller:

```bash 
    $roslaunch pure_pursuit_controller pure_pursuit.launch
```

3. Enviar waypoints como ruta de referencia

```bash
    $roslaunch pure_pursuit_controller test_send_waypoints.launch
```

### Tuning:
En General, el ***look_ahead_ratio*** y ***look_ahead_constant*** en *pure_pursuit_controller.yaml* determina la Look-ahead-Distance en el Pure-Pursuit, que afecta principalmente al rendimiento de Seguimiento de Trayectoria. Mirar [Matlab: PurePursuit](https://ww2.mathworks.cn/help/robotics/ug/pure-pursuit-controller.html) para más información.


## Referencias:

- [Pure-Pursuit ROS](https://github.com/jmaye/pure-pursuit-controller-ros)

- [PythonRobotics: PurePursuit](https://github.com/AtsushiSakai/PythonRobotics/tree/master/PathTracking/pure_pursuit)

- [Matlab: PurePursuit](https://ww2.mathworks.cn/help/robotics/ug/pure-pursuit-controller.html)

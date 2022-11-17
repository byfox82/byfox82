[include menu.cfg] # custom lcd display menu 
 
 [stepper_x]
step_pin: PB13
dir_pin: !PB12
enable_pin: !PB14
microsteps: 16
rotation_distance: 40
endstop_pin: ^PC0
position_endstop: 0
position_min: 0
position_max: 230
homing_speed: 50 
 
 [tmc2209 stepper_x]
uart_pin: PC11
tx_pin: PC10
uart_address: 0
run_current: 0.580
hold_current: 0.500
stealthchop_threshold: 999999 
 
 [stepper_y]
step_pin: PB10
dir_pin: !PB2
enable_pin: !PB11
microsteps: 16
rotation_distance: 40
endstop_pin: ^PC1
position_endstop: -12
position_min: -12
position_max: 230
homing_speed: 50

 [tmc2209 stepper_y]
uart_pin: PC11
tx_pin: PC10
uart_address: 2
run_current: 0.580
hold_current: 0.500
stealthchop_threshold: 999999

 [stepper_z]
step_pin: PB0
dir_pin: PC5
enable_pin: !PB1
microsteps: 16
rotation_distance: 8
# endstop_pin: ^PC2
# position_endstop: 0.0
endstop_pin: probe:z_virtual_endstop
position_min: -4
position_max: 250

 [tmc2209 stepper_z]
uart_pin: PC11
tx_pin: PC10
uart_address: 1
run_current: 0.580
hold_current: 0.500
stealthchop_threshold: 999999

 [extruder]
step_pin: PB3
dir_pin: !PB4
enable_pin: !PD1
microsteps: 16
rotation_distance: 7.71
nozzle_diameter: 0.400
filament_diameter: 1.750
max_extrude_only_distance: 100
pressure_advance: 0.04
pressure_advance_smooth_time: 0.040
heater_pin: PC8
sensor_type: ATC Semitec 104GT-2
sensor_pin: PA0
control: pid
pid_Kp: 21.527
pid_Ki: 1.063
pid_Kd: 108.982
min_temp: 0
max_temp: 300

 [tmc2209 extruder]
uart_pin: PC11
tx_pin: PC10
uart_address: 3
run_current: 0.620
hold_current: 0.500
stealthchop_threshold: 999999

 [heater_bed]
heater_pin: PC9
sensor_type: EPCOS 100K B57560G104
Fsensor_pin: PC4
control: pid
pid_Kp: 54.027
pid_Ki: 0.770
pid_Kd: 948.182
min_temp: 0
max_temp: 130

 [heater_fan hotend_fan]
pin: PB15
heater: extruder
heater_temp: 50.0

 [controller_fan electronic_enclosure_fan]
pin: PC7
idle_timeout: 60

 [fan]
pin: PC6

 [mcu]
serial: /dev/serial/by-id/usb-Klipper_stm32g0b1xx_27000D000150414235363020-if00
# serial: /dev/ttyAMA0
# restart_method: command

 [printer]
kinematics: cartesian
max_velocity: 300
max_accel: 3000
max_accel_to_decel: 1000
square_corner_velocity: 5.0
max_z_velocity: 5
max_z_accel: 100

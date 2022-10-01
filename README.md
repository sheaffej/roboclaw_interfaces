# roboclaw_interfaces

This repo contains the ROS2 messages used by the associated ROS2 Roboclaw driver node ([sheaffej/roboclaw_driver2](https://github.com/sheaffej/roboclaw_driver2))

See the `sheaffej/roboclaw_driver2` [README.md](https://github.com/sheaffej/roboclaw_driver2/blob/main/README.md) for steps on how to use this repo.

The ROS2 messages are simply:

`SpeedCommand.msg`:
```
# Motor speed in QPPS
int32 m1_qpps
int32 m2_qpps

# Acceleration
uint32 accel

# Max seconds before automatically stopping
uint32 max_secs
```

`Stats.msg`:
```
# Motor 1 & 2 encoder values
int32 m1_enc_val
int32 m2_enc_val

# Motor 1 & 2 speed values in QPPS (+/-)
int32 m1_enc_qpps
int32 m2_enc_qpps
```


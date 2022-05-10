# 6-rotor_pos_control

In order to update the original PX4 firmware from the PX4 Autopilot repository, first you need to clone the master repository into your computer with the following command

git clone https://github.com/PX4/PX4-Autopilot.git

After that, is necessary to replace the next folders in PX4-Autopilot/src/modules/
- mc_att_control
- mc_pos_control
- mc_rate_control 

and the folder MultirotorMixer must be repleced in PX4-Autopilot/src/lib/mixer/

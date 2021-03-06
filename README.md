# 6-rotor_pos_control

In order to update the original PX4 firmware from the PX4 Autopilot repository, first you need to clone the master repository into your computer with the following command

$ git clone https://github.com/PX4/PX4-Autopilot.git

After that, is necessary to replace the folders from this repository to the respectibely forlders of the original PX4 firmware
- the folder MultirotorMixer                must be repleced in PX4-Autopilot/src/lib/mixer/
- the folder mc_att_control                 must be replaced in PX4-Autopilot/src/modules/
- the contents files in mc_pos_control      must be repleced in PX4-Autopilot/src/modules/mc_pos_control/PositionControl/
- the folder mc_rate_control                must be replaced in PX4-Autopilot/src/modules/

Once all the files are replaced, it is necessary to build the firmware for a first time

$ DONT_RUN=1 make px4_sitl gazebo

this command will generate a new folder in PX4-Autopilot/build/ named px4_sitl_default. In this folder we will replace the file mixer_multirotor_normalized.generated.h in PX4-Autopilot/build/px4_sitl_default/src/lib/mixer/MultirotorMixer/, by replacing this file we modify the mixer parámeters enabling the fully actuation mixing in the hexa-rotor.

Finally, for simulation only, it is requierd to replace the alst file typhoon_h480.sdf in PX4-Autopilot/Tools/sitl_gazebo/models/typhoon_h480/, this file is a modification of the hexa-rotor model rotating the motors according to the calculated mixing matrix.

Now it is possible to run the SITL simulation by running

$ make px4_sitl gazebo_typhoon_h480

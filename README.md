# DJI-MIPI-Switch
2-Camera Input MIPI Switch for Caddx Vista/DJI Air Unit/Runcam Link systems


## V1.0: Initial Revision (INACTIVE)

![image](https://github.com/user-attachments/assets/19f00abc-7030-4193-8217-5f199d6d0264)

- The MIPI Switch has 2 MIPI D-PHY CSI inputs and 1 output, all using the DF56C-26P-0.3V(51) connector standard to the 26P DJI FPV system.
- Switching is performed by the PI3WVR646GEEX analog multiplexer, which is the only device in the video signal path.
- Routing is all length and impedence matched within each connector path. The 3 different connectors have different trace lenghts but this does not matter since each camera just sees a slightly longer or shorter total cable length.
- The selection between A and B cameras is controlled by a Pololu RCS01B, which provides a user adjustable PWM threshhold.
- This PCB has 25.5 x 25.5mm mounting holes to match the Caddx Vista and Runcam Link VTX.
- Note1: This board does not pass through the I2C pins, which means cameras that require configuration will not work. Only 60fps cameras are supported.
- Note2: This board is now INACTIVE. Pinout is incorrect.


## V1.1: Fixes V1.0 issues (FUNCTIONAL, SEE NOTE 2)

![image](https://github.com/user-attachments/assets/c56ef4ff-1371-4ec6-afa3-4b5e3d338c48)
![image](https://github.com/user-attachments/assets/7a22f38d-aa0f-444b-b377-054abdd3db6e)

- Fixed incorrect assumption that the DJI MIPI Coaxial Cable uses a 1-1 pin configuration. This means that pin 1 on the VTX footprint connects to pin 1 on the Camera. In reality, the cable is a 1-n or 1-26 configuration, which flips the pin numbering on one end. VTX-CAM = one flip, so VTX-PCB-CAM needs 3 to match. Therefore V1.1 has mirrored connector pinouts on the camera output connectors, leading to the correct orientation at all stages.
- Improved the silkscreen labeling on the board, including marking the orientation of the PWM input
- Added 20 x 20 mm mounting holes for flexibility
- Note1: Do not use the pinout in this schematic, it has the MIPI lanes in the wrong order and polarity. It does not affect the function of this board, but only because this chip has interchangeable lanes.
- Note2: This board works, however it does have a bug when switching back and forth rapidly (>1Hz). This crashes the VTX until power cycle.


## V2.0: Integrated PWM reading (TBD)

- Size TBD
- Fixed MIPI lane order and polarity on the connectors.
- Replaces 2.54mm pin header with smaller but still common JST SH1.0
- Replaces Pololu RCS01B with integrated PWM reading circuit TBD
- Blocks rapid switching via TBD
- Stretch goal: I2C handling


# Current Pinout Reference:

![DJI MIPI Pinout](https://github.com/user-attachments/assets/92999fe0-bf99-419b-b137-15249c2e8324)




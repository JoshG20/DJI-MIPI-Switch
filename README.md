# DJI-MIPI-Switch
2-Camera Input MIPI Switch for Caddx Vista/DJI Air Unit/Runcam Link systems

V1.0: Initial Revision (INACTIVE)
The MIPI Switch has 2 MIPI D-PHY CSI inputs and 1 output, all using the DF56C-26P-0.3V(51) connector standard to the 26P DJI FPV system.
Switching is performed by the PI3WVR646GEEX analog multiplexer, which is the only device in the video signal path.
Routing is all length and impedence matched within each connector path. The 3 different connectors have different trace lenghts but this does not matter since each camera just sees a slightly longer or shorter total cable length.
The selection between A and B cameras is controlled by a Pololu RCS01B, which provides a user adjustable PWM threshhold.
This PCB has 25.5 x 25.5mm mounting holes to match the Caddx Vista and Runcam Link VTX.
Note: This board does not pass through the I2C pins, which means cameras that require configuration will not work. Only 60fps cameras are supported.
Note: This board is a prototype, function is not guaranteed. (Spoiler: V1.0 did not function)

V1.1: Fixes V1.0 issues (UNTESTED)
-Fixed incorrect assumption that the DJI MIPI Coaxial Cable uses a 1-1 pin configuration. This means that pin 1 on the VTX footprint connects to pin 1 on the Camera. In reality, the cable is a 1-n or 1-26 configuration, which flips the pin numbering on one end. VTX-CAM = one flip, so VTX-PCB-CAM needs 3 to match. Therefore V1.1 has mirrored connector pinouts on the camera output connectors, leading to the correct orientation at all stages.
-Improved the silkscreen labeling on the board, including marking the orientation of the PWM input
-Added 20 x 20 mm mounting holes for flexibility

V2.0: Integrated PWM reading (PLANNED)
-Replaces Pololu RCS01B with integrated PWM reading circuit based on the work of Ken Hewitt at HewittOnline.net. The circuit has a variable resistor for adjusting the PWM threshold.

Current Pinout Reference:
![DJI MIPI Pinout](https://github.com/user-attachments/assets/962b1f98-0d47-4575-b036-7b70cad809e5)



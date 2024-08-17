# DJI-MIPI-Switch
2-Camera Input MIPI Switch for Caddx Vista/DJI Air Unit/Runcam Link systems

The MIPI Switch has 2 MIPI D-PHY CSI inputs and 1 output, all using the DF56C-26P-0.3V(51) connector standard to the 26P DJI FPV system.
Switching is performed by the PI3WVR646GEEX analog multiplexer, which is the only device in the video signal path.
Routing is all length and impedence matched within each connector path. The 3 different connectors have different trace lenghts but this does not matter since each camera just sees a slightly longer or shorter total cable length.
Note: This board does not pass through the I2C pins, wich means cameras that require configuration will not work. Only 60fps cameras are supported.
Note: This board is a prototype, function is not guaranteed.

The selection between A and B cameras is controlled by a Pololu RCS01B, which provides a user adjustable PWM threshhold.
This PCB has 25.5 x 25.5mm mounting holes to match the Caddx Vista and Runcam Link VTX.

The board is designed to be produced and assembled by JLCPCB, with the exception of the Pololu RCS01B, which is hand soldered later.
The stackup is the JLC04161H-3313 with 4 layers (Front-GND-GND-Back) and components all on the front side. The only special option required is 0.2mm via hold drilling.
Note: PI3WVR646GEEX footprint is not standard, it features elongated pads to allow inner traces to pass between them, this avoids Via-in-pad usage and reduces the cost, in exchange for sligtly increased misalignment risk during assembly.

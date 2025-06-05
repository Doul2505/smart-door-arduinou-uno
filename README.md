# smart-door-arduinou-uno
🔐 Face Recognition Door Lock with HuskyLens & Arduino
This project uses the HuskyLens AI camera and an Arduino to build a smart door lock that unlocks only when an authorized face is recognized. The lock is controlled via a relay module, and includes a built-in cooldown mechanism to prevent rapid toggling.

📦 Features
✅ Unlocks with authorized faces (pre-learned using HuskyLens)

🔒 Automatically locks when the authorized face disappears

⏱ Includes a 5-second cooldown after locking to prevent abuse

🔌 Relay-controlled output to drive an electric strike or lock

🛠 Hardware Required
🧠 Arduino Uno / Nano / Mega (or compatible)

👁️ HuskyLens AI Camera

🔌 Relay Module (to control locking mechanism)

🔧 Jumper wires, power supply, breadboard (optional)

⚡ 5V power source (shared or separate for camera/relay)

🔗 Wiring Diagram
Component	Connected To
HuskyLens SDA	Arduino A4 (SDA)
HuskyLens SCL	Arduino A5 (SCL)
Relay IN	Arduino Pin 3
VCC/GND	To Arduino 5V/GND

Note: Check your Arduino model's I2C pins — this example assumes an Uno.

📋 Setup Instructions
Install Required Library:

Download and install the HuskyLens Library from the DFRobot GitHub or via the Arduino Library Manager.

Connect the Hardware:

Wire the HuskyLens and relay to your Arduino as described above.

Train the HuskyLens:

Power up the HuskyLens standalone.

Switch to "Face Recognition" mode.

Long-press the learning button to learn a new face. Repeat for multiple faces if needed.

You can assign different IDs to faces for multi-user access.

Upload the Code:

Open the provided .ino file in the Arduino IDE and upload it to your board.

Test the System:

When the HuskyLens sees a face with an authorized ID (e.g., 1 or 2), the relay will turn ON.

Once the face is gone, the system locks again after a short delay.

🧠 How It Works
The Arduino communicates with the HuskyLens over I2C.

It checks whether a learned face (ID 1 or 2) is currently visible.

If an authorized face is detected:

The relay is triggered (unlocks the door).

If the face disappears:

The relay is deactivated after a short delay (locks the door).

A cooldown period of 5 seconds prevents immediate reactivation.

🔒 Security Notes
This is a basic prototype — not meant for high-security use.

Use it for hobby projects, smart lockers, or pet doors.
![IMG_20250529_183928](https://github.com/user-attachments/assets/e572649b-c48f-42dc-a156-9e93cd1559d6)
![IMG_20250529_183939](https://github.com/user-attachments/assets/4e045d4d-12ee-430c-8b22-bade9ce8fd3c)
![IMG_20250529_183933](https://github.com/user-attachments/assets/408fe5fc-62de-4b44-936f-4844cdd2545c)

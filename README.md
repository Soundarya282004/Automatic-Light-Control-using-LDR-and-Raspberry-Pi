# Automatic-Light-Control-using-LDR-and-Raspberry-Pi
This project automatically controls a light based on ambient brightness using an LDR (Light Dependent Resistor) and a Raspberry Pi.

🔌 Hardware Required

- Raspberry Pi
- LDR (Light Dependent Resistor)
- Relay Module
- Switch (Optional manual override)
- Jumper Wires
- Light bulb / Lamp

🔧 GPIO Pin Connections

Component	GPIO Pin
LDR Sensor	GPIO 2
Relay Module	GPIO 3
Switch	GPIO 4
<img width="255" height="97" alt="image" src="https://github.com/user-attachments/assets/249473a8-4ae3-42b7-b032-dac264611fbe" />

💻 Software Requirements

Install GPIO library (usually preinstalled on Raspberry Pi OS):

pip install RPi.GPIO

▶ How to Run the Code
Step 1 — Save the file

Save as:

main.py

Step 2 — Connect hardware properly

Make sure LDR, Relay, and Switch are wired to correct GPIO pins.

Step 3 — Run the script on Raspberry Pi
python3 main.py

⚙️ How the System Works

You can add this section to GitHub under “Working”.

🌞 When It’s Bright
if GPIO.input(ldr) != GPIO.HIGH:


The LDR detects light → Relay turns OFF → Light turns OFF.

BUT…

If the switch is ON (emergency/manual mode):

if D != 1:
    GPIO.output(relay, True)


Light turns ON even if it’s bright.

🌙 When It’s Dark
else:
    GPIO.output(relay, True)


LDR detects darkness → Relay turns ON → Light turns ON automatically.

🔁 Loop

The program checks light conditions every 1 second:

time.sleep(1)

⛔ Stop the Program

Press:

    CTRL + C


GPIO pins will reset safely because of:

GPIO.cleanup()

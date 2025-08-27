# Solar-Tracker-Project-Dual-Axis
This project is a dual-axis solar tracker built with Arduino, photoresistors (LDRs), and servo motors.  It automatically aligns a small solar panel toward the sun by comparing light levels on four sensors. The goal was to improve energy harvesting efficiency and also experiment with powering a power bank.

##  Concept
The system uses 4 LDRs arranged in a cross pattern to detect sunlight direction.  
The Arduino reads the values and moves two servo motors (X-axis and Y-axis) so the solar panel always faces the brightest light source.  

---

## 🔧 Components
- Arduino Uno R3  
- 2x SG90 Servo Motors  
- 4x LDRs + 4 10kΩ resistors  
- Breadboard + jumper wires  
- 5V solar panel (with USB output planned for charging a power bank)  
- Custom mount (3D printed / hand-built prototypes)  

---

## ⚡ Circuit Design
- Each LDR is wired as a voltage divider with a 10kΩ resistor.  
- LDR outputs connect to Arduino analog pins A0–A3.  
- Servo X on digital pin 13 (horizontal).  
- Servo Y on digital pin 9 (vertical).  
- Solar panel intended to charge a portable power bank through a USB adapter.  

---

## 📝 Code Explanation
1. **Setup**  
   - Attach servos and set their starting position.  

2. **Loop**  
   - Read light values from all 4 LDRs.  
   - Compute average light for top vs bottom, left vs right.  
   - Compare differences:  
     - If top brighter → tilt up.  
     - If the bottom is brighter → tilt down.  
     - If left brighter → rotate left.  
     - If right brighter → rotate right.  
   - Use tolerance to avoid jitter.  

3. **Output**  
   - Servos adjust the solar panel to stay aligned with the brightest source.  

---

## 🧪 Challenges
- Cardboard mounts were too weak → switched to sturdier materials and tested 3D-printed versions.  
- Servo jitter required adjusting tolerance and tightening mount bolts.  
- Finding the right solar panel (5V, small size, with USB) was difficult. Larger panels worked, but were too heavy for the mount.  
- Power bank integration was tricky since most banks buffer stored energy instead of showing live solar charging.  

---

## ✅ Results
- The dual-axis tracking mechanism successfully works when tested with artificial light.  
- Limitations came from solar panel weight/size vs mount strength.  
- Next steps: upgrade mount materials, source a correct solar panel, and finalize power bank charging.  

---

## 📚 Resources
- [Instructables: Arduino Solar Tracker](https://www.instructables.com/Arduino-Solar-Tracker/)  
- [Hackster.io: Solar Tracker + Phone Charger](https://www.hackster.io/FIELDING/solar-panel-sun-tracker-phone-charger-f669ce)  
- [YouTube: DIY Arduino Solar Tracker](https://www.youtube.com/watch?v=dkV3xCrZAqc)  


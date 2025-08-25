# Smart Attendance System (RFID + NodeMCU + Google Sheets)

This project implements a **smart attendance system** using **NodeMCU (ESP8266)**, **RFID module (RC522)**, and an **I2C LCD display**.  
It identifies users with RFID cards, logs attendance to **Google Sheets**, and provides visual + audio feedback via LCD and buzzer.

---

## 📦 Hardware Requirements
- **NodeMCU (ESP8266)**  
- **RFID-RC522 Module**  
- **I2C 16x2 LCD Display**  
- **Active Buzzer**  
- **RFID Tags/Cards (MIFARE Classic 1K or similar)**  
- Jumper wires and breadboard  

---

## 🔌 Circuit Connections

| Component      | NodeMCU Pin |
|----------------|-------------|
| RC522 SDA/SS   | D4          |
| RC522 RST      | D3          |
| RC522 MOSI     | D7          |
| RC522 MISO     | D6          |
| RC522 SCK      | D5          |
| Buzzer (+)     | D8          |
| LCD (I2C) SDA  | D2          |
| LCD (I2C) SCL  | D1          |
| GND / VCC      | GND / 3.3V  |

> ⚠️ Note: RC522 RFID reader must be powered from **3.3V** (not 5V).

---

## 🖥️ Software Setup

### 1. Install Arduino IDE
Download and install from: [Arduino IDE](https://www.arduino.cc/en/software)

### 2. Install ESP8266 Board Package
- Go to **File → Preferences**  
- Add the following URL to *Additional Board Manager URLs*:

http://arduino.esp8266.com/stable/package_esp8266com_index.json

- Then install **ESP8266 by ESP8266 Community** via *Tools → Board Manager*.

### 3. Install Required Libraries
In Arduino IDE, install the following libraries via **Sketch → Include Library → Manage Libraries**:
- `MFRC522` (by Miguel Balboa) – for RFID module  
- `LiquidCrystal_I2C` – for LCD display  
- `ESP8266WiFi` – for Wi-Fi connection  
- `Wire` & `SPI` (usually pre-installed)  

### 4. Google Sheets Setup
1. Open Google Sheets → *Extensions → App Script*.  
2. Paste the contents of `App Script.txt` provided in this repo.  
3. Deploy the script as a **web app** with access to *Anyone with the link*.  
4. Copy the web app URL and update it inside your NodeMCU sketch (where data is sent).  

---

## ▶️ Usage
1. Power the NodeMCU and peripherals.  
2. LCD will display: **"Scan your card"**.  
3. Place an RFID card near the reader.  
 - ✅ If recognized → LCD shows "Welcome [Name]" + single beep.  
 - ❌ If unknown → LCD shows "Unknown" + 3 beeps.  
4. Attendance data is automatically logged in Google Sheets.  

---

## 📊 Features
- Secure RFID-based identification  
- Real-time attendance logging into Google Sheets  
- LCD feedback for user interaction  
- Audio feedback (buzzer) for known/unknown cards  
- Easily expandable for multiple users  

---

## 📂 Project File Structure

├── Smart_Attendance.ino       # Main Arduino sketch ├── App Script.txt             # Google Sheets script for data logging ├── README.md                  # Documentation

---

## 🛠️ Future Improvements
- Add Wi-Fi auto-reconnect functionality  
- Use Firebase for cloud storage instead of Sheets  
- Create Android app for attendance monitoring  
- Encrypt UID transmission for better security  

---

## 🤝 Contributing
Contributions are welcome! Please fork this repo and submit a pull request.  

---

## 📜 License
This project is licensed under the **MIT License** – feel free to use and modify it.

---

## 👨‍💻 Author
**Shad Ebny Wahid**  
- 📧 Email: shadebnywahid@gmail.com  
- 🌐 [Facebook](https://www.facebook.com/saadw50) | [Twitter](https://twitter.com/saadw50) | [YouTube](https://www.youtube.com/c/eee_bd_by_saad)



<h1 align="center">Hi 👋, I'm Shad Ebny Wahid</h1>
<h3 align="center">A BSc Student in Electrical and Electronic Engineering in Jamalpur Science and Technology University, Bangladesh</h3>

<p align="left"> <a href="https://twitter.com/saadw50" target="blank"><img src="https://img.shields.io/twitter/follow/saadw50?logo=twitter&style=for-the-badge" alt="saadw50" /></a> </p>

- 🔭 I’m currently working on [Smart Attendance System](https://github.com/saadw50/smart_attendence_system_rfid)

- 🌱 I’m currently learning **Android Studio, COMSOL, Google API**

- 🤝 I’m looking for help with **Facebook Profile Information generator**

- 👨‍💻 All of my projects are available at [www.facebook.com/saadw50](www.facebook.com/saadw50)

- 📫 How to reach me **shadebnywahid@gmail.com**

- 📄 Know about my experiences [https://drive.google.com/file/d/1q19jDYHpGHEHJq8MfL7ZnVBcALHE4oKg/view?usp=sharing](https://drive.google.com/file/d/1q19jDYHpGHEHJq8MfL7ZnVBcALHE4oKg/view?usp=sharing)

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://twitter.com/saadw50" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/twitter.svg" alt="saadw50" height="30" width="40" /></a>
<a href="https://fb.com/saadw50" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/facebook.svg" alt="saadw50" height="30" width="40" /></a>
<a href="https://instagram.com/pagal__tissue_le_lo" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="pagal__tissue_le_lo" height="30" width="40" /></a>
<a href="https://www.youtube.com/c/eee_bd_by_saad" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/youtube.svg" alt="eee_bd_by_saad" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://developer.android.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/android/android-original-wordmark.svg" alt="android" width="40" height="40"/> </a> <a href="https://www.arduino.cc/" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/arduino-1.svg" alt="arduino" width="40" height="40"/> </a> <a href="https://www.blender.org/" target="_blank" rel="noreferrer"> <img src="https://download.blender.org/branding/community/blender_community_badge_white.svg" alt="blender" width="40" height="40"/> </a> <a href="https://www.cprogramming.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="c" width="40" height="40"/> </a> <a href="https://cloud.google.com" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/google_cloud/google_cloud-icon.svg" alt="gcp" width="40" height="40"/> </a> <a href="https://www.adobe.com/in/products/illustrator.html" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/adobe_illustrator/adobe_illustrator-icon.svg" alt="illustrator" width="40" height="40"/> </a> <a href="https://www.java.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="40" height="40"/> </a> <a href="https://www.linux.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="linux" width="40" height="40"/> </a> <a href="https://www.mathworks.com/" target="_blank" rel="noreferrer"> <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/Matlab_Logo.png" alt="matlab" width="40" height="40"/> </a> <a href="https://nodejs.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs" width="40" height="40"/> </a> <a href="https://www.photoshop.com/en" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt="photoshop" width="40" height="40"/> </a> <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> <a href="https://unity.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/unity3d/unity3d-icon.svg" alt="unity" width="40" height="40"/> </a> </p>

<h3 align="left">Support:</h3>
<p><a href="https://ko-fi.com/saadw50"> <img align="left" src="https://cdn.ko-fi.com/cdn/kofi3.png?v=3" height="50" width="210" alt="saadw50" /></a></p><br><br>

<p><img align="center" src="https://github-readme-stats.vercel.app/api/top-langs?username=saadw50&show_icons=true&locale=en&layout=compact" alt="saadw50" /></p>

# Nomisys – Système de Contrôle d'Accès Sécurisé Multi-Facteurs

Nomisys est un système complet d’accès sécurisé combinant :
- Lecture RFID (carte/badge)
- Reconnaissance d'empreinte digitale
- Communication WiFi via ESP8266
- Affichage via écran LCD I2C
- Notifications en temps réel par Telegram
- Interface Web pour journaliser les accès

---

## 📷 Présentation du projet

Lorsqu'un utilisateur présente une **carte RFID valide** et que son **empreinte** est reconnue, l’accès est accordé.  
Chaque événement est :
- Affiché sur l’écran LCD
- Envoyé en temps réel via WiFi à une page Web
- Notifié sur Telegram.

---

## 🔌 Matériel Nécessaire

| Composant                    | Quantité | Remarques |
|-------------------------------|----------|-----------|
| Arduino Uno R3                | 1        | Contrôleur principal |
| Module WiFi ESP8266            | 1        | Communication via UART |
| Lecteur RFID MFRC522           | 1        | Interface SPI |
| Capteur d'empreintes R307      | 1        | Interface UART |
| Écran LCD 16x2 avec module I2C | 1        | Interface utilisateur |
| Buzzer (optionnel)             | 1        | Indication sonore |
| LEDs (optionnelles)            | 2-3      | Statut système |
| Alimentation 5V               | 1        | (ou USB) |

---

## ⚡ Schéma de câblage

| Périphérique                  | Broche Arduino | Détail |
|:-------------------------------|:---------------|:-------|
| MFRC522 SDA (SS)                | D10            | Slave Select SPI |
| MFRC522 SCK                     | D13            | Clock SPI |
| MFRC522 MOSI                    | D11            | MOSI SPI |
| MFRC522 MISO                    | D12            | MISO SPI |
| MFRC522 RST                     | D9             | Reset du module |
| MFRC522 GND                     | GND            | Masse |
| MFRC522 3.3V                    | 3.3V           | Alimentation |
| Capteur Empreintes TX           | D2             | Reception Arduino |
| Capteur Empreintes RX           | D3             | Transmission Arduino |
| Capteur Empreintes VCC          | 5V             | Alimentation |
| Capteur Empreintes GND          | GND            | Masse |
| LCD I2C SDA                     | A4             | Donnée I2C |
| LCD I2C SCL                     | A5             | Horloge I2C |
| ESP8266 TX                      | D7             | Réception Arduino |
| ESP8266 RX                      | D8             | Transmission Arduino (avec diviseur de tension) |
| ESP8266 VCC                     | 3.3V           | Alimentation |
| ESP8266 GND                     | GND            | Masse |

---

## 🧠 Architecture du système


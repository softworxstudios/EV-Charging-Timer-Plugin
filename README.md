# EV Charging Timer Plugin v1.1.0  
**SoftWorx Studios**

Automate timed shut-off of any charger (or other device) in Home Assistant based on a user-selectable charge-percentage, with real-time progress tracking. Download the plugin by copying this link into the HA "Import Blueprint" section, then click preview, and download.

Open Settings → Automations & Scenes → Blueprints
Click Import Blueprint
Paste the raw-file URL of the blueprint:
https://github.com/softworxstudios/EV-Charging-Timer-Plugin/raw/main/EV_Charging_Timer_BluePrint.yaml

---

## 📝 Prerequisites

### 1 · Helpers

Create these three helpers **before** importing the blueprint.

| Helper | Where to create | Settings |
| ------ | --------------- | -------- |
| **Timer** | *Settings → Devices & Services → Helpers → Create Helper*<br>Choose **Timer** | • Name: `EV Charging Timer` (or anything you like)<br>• Default duration: `6:30:00` → represents 100 % (change anytime in *Timers*)<br>• *(Optional)* turn on *Restore after startup* |
| **Number** (Charge Percentage) | *Settings → Devices & Services → Helpers → Create Helper*<br>Choose **Number** | • Name: `EV Charge Percentage`<br>• Min = 0 Max = 100<br>• Unit of measurement: `%` (UI may hide this field – it’s optional) |
| **Number** (Charge Progress) | *Settings → Devices & Services → Helpers → Create Helper*<br>Choose **Number** | • Name: `EV Charge Progress`<br>• Min = 0 Max = 100<br>• Step = 0.1<br>• Unit of measurement: `%` (optional) |

---

## 📥 Import the Blueprint

1. Open **Settings → Automations & Scenes → Blueprints**  
2. Click **Import Blueprint**  
3. Upload the provided YAML file or paste its contents.  
4. Click "Preview" then **Import**  
5. You will now see **EV Charging Automation Blueprint** in the blueprint list.

---

## ⚙️ Create the Automation

*(A stub automation is generated automatically when you finish the import.  
Use these steps only if you deleted it or want additional instances.)*

1. **Settings → Automations & Scenes**  
2. Click **+ Add Automation → Use Blueprint**  
3. Choose **EV Charging Automation Blueprint**  
4. Fill in the inputs:  

| Input | What to pick |
| ----- | ------------ |
| **Charger Switch** | The switch entity that powers your charger |
| **Charge Timer** | The **Timer** helper you created earlier |
| **Charge Percentage** | The **Number** helper for desired charge percentage |
| **Charge Progress** | The **Number** helper for tracking charge progress |

5. Click **Save**

That’s it!  
Turn the charger switch **ON**, set a percentage, and the blueprint will start the timer and switch the plug off when the calculated time elapses. The charge progress will update automatically every few seconds.

---


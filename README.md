# EV Charging Timer Plugin&nbsp;v1.0.0  
**SoftWorx Studios**

Automate timed shut-off of any charger (or other device) in Home Assistant based on a user-selectable charge-percentage.

---

## 📝 Prerequisites

### 1 · Helpers

Create these two helpers **before** importing the blueprint.

| Helper | Where to create | Settings |
| ------ | --------------- | -------- |
| **Timer** | *Settings → Devices & Services → Helpers → Create Helper*<br>Choose **Timer** | • Name: `EV Charging Timer` (or anything you like)<br>• Default duration: `6:30:00` → represents 100 % (change anytime in *Timers*)<br>• *(Optional)* turn on *Restore after startup* |
| **Number** | *Settings → Devices & Services → Helpers → Create Helper*<br>Choose **Number** | • Name: `EV Charge Percentage`<br>• Min = 0 Max = 100<br>• Unit of measurement: `%` (UI may hide this field – it’s optional) |

---

## 📥 Import the Blueprint

1. Open **Settings → Automations & Scenes → Blueprints**  
2. Click **Import Blueprint**  
3. Paste the raw-file URL of the blueprint:  

https://github.com/softworxstudios/EV-Charging-Timer-Plugin/raw/main/EV_Charging_Timer_BluePrint.yaml

4. Click "Preview then **Import**  
5. You will now see **EV Charging Timer (Percentage-Based)** in the blueprint list.

---

## ⚙️ Create the Automation

*(A stub automation is generated automatically when you finish the import.  
Use these steps only if you deleted it or want additional instances.)*

1. **Settings → Automations & Scenes**  
2. Click **+ Add Automation → Use Blueprint**  
3. Choose **EV Charging Timer (Percentage-Based)**  
4. Fill in the inputs:  

| Input | What to pick |
| ----- | ------------ |
| **Smart Plug** | The switch entity that powers your charger |
| **Timer Entity** | The **Timer** helper you created earlier |
| **Charge Percentage Input** | The **Number** helper you created earlier |
| **Maximum Charge Time** | Full-charge hours (default `6.5`) |

5. Click **Save**

That’s it!  
Turn the smart plug **ON**, set a percentage, and the blueprint will start the timer and switch the plug off when the calculated time elapses.

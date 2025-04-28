EV Charging Timer Plugin v1.0.0 - SoftWorx Studios

Description: A plugin made for Home Assistant that allows for automated timed shut-off of any specified entity or device.

Integration Steps

Step 1: Create Required Helpers
Before importing the blueprint, create these helpers in Home Assistant. This step is critical for it to function.
    
1. Timer Helper: 
         Go to Settings > Devices & Services > Helpers > Create Helper. 
         Select "Timer". 
         Name it (e.g., "EV Charging Timer"). 
         Set a default duration (e.g., 6:30:00) This defines the "max" time, or the 100% value. You can change this value under timers at any point.
    
2. Number Helper: 
         Go to Settings > Devices & Services > Helpers > Create Helper 
         Select "Number". 
         Name it (e.g., "EV Charge Percentage"). 
         Min: 10, Max: 100, Step: 5 
         Unit of measurement: % 


Step 2: Import the Blueprint
    1. Go to Settings > Automations & Scenes > Blueprints 
    2. Click "Import Blueprint" button 
    3. Paste this URL: https://github.com/softworxstudios/EV-Charging-Timer-Plugin/EV-Charging-Timer-BluePrint.yaml
    4. Click "Preview" then "Import" 

Step 3: Create the Automation
    1. Go to Settings > Automations & Scenes 
    2. Click "+ Add Automation" 
    3. Click "Use Blueprint" 
    4. Select "EV Charging Timer (Percentage-Based)" 
    5. Configure the inputs: 
         Smart Plug: Select your EV charger's smart plug 
         Timer Entity: Select the timer helper you created 
         Charge Percentage Input: Select the number helper you created 
         Maximum Charge Time: Set to your desired maximum (default 6.5 hours) 
    6. Click "Save"

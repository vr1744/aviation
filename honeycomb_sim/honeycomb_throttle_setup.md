Guidance for setting up the **Honeycomb Bravo Throttle Quadrant** autopilot panel using **FlyWithLua** in **X-Plane 12**, based on the most reliable community solution.

The **best plugin** for this (especially on Mac/Apple Silicon, but also works on Windows/Linux for many users) is the **Honeycomb Bravo Plugin** by Jorge Uvo. It handles the autopilot knobs (IAS/CRS/HDG/VS/ALT), right encoder (inc/dec), LEDs, and aircraft-specific profiles automatically — without relying on the official Honeycomb Configurator or Aerosoft AFC Bridge (which often cause conflicts, especially on Mac).

**Direct download link** (requires free X-Plane.org account):  
https://forums.x-plane.org/files/file/89635-honeycomb-bravo-plugin/

### Current Plugin Details (as of latest version)
- **Version**: 1.1.1  
- **Release Date**: March 1, 2024  
- **Files included**:  
  - `Honeycomb Bravo.lua` (the core script)  
  - `Honeycomb Bravo Plugin Manual.pdf` (detailed instructions)  
  - Three `.joy` files: `HoneycombBravoThrottle_Mac.joy`, `HoneycombBravoThrottle_Win.joy`, `HoneycombBravoThrottle_Linux.joy`  
- **Supported aircraft/profiles**: Default X-Plane aircraft, Zibo Mod B738, EVO BE9L G1000, C172 Skyhawk (standard & G1000), SR22 (added in v1.1.1).  
- **Key fixes in v1.1.1**: Improved C172 G1000 altitude knob behavior; added SR22 support.  
- **Compatibility notes**: Strongly tested on Mac (Apple Silicon native/with Rosetta, Intel). Windows/Linux should work but less tested. Requires **X-Plane 12** and **FlyWithLua NG+**.

### Step-by-Step Setup Instructions (Reviewed & Confirmed from Plugin Page)
1. **Install FlyWithLua NG+** (if not already done):  
   Download the latest from: https://forums.x-plane.org/files/file/82888-flywithlua-ng-next-generation-plus-edition-for-x-plane-12-win-lin-mac/  
   Unzip and place the `FlyWithLua` folder into:  
   `X-Plane 12/Resources/plugins/`  
   Launch X-Plane once to activate. If you get an error,
   open terminal, run the command: `xattr -cr ~/X-Plane\ 12/Resources/plugins/FlyWithLua/`

2. **Remove conflicting software** (critical to avoid issues):  
   - Delete any **AFC Bridge** plugin folder (from Aerosoft/Honeycomb Configurator).  
   - Uninstall or disable the official **Honeycomb Configurator** software.

3. **Download & extract the plugin**:  
   Get it from: https://forums.x-plane.org/files/file/89635-honeycomb-bravo-plugin/  
   Unzip the package.

4. **Copy the joystick config files** (important for button/LED recognition):  
   - Backup the originals in this folder first:  
     `X-Plane 12/Resources/joystick configs/`  
   - Copy the appropriate `.joy` file (Mac/Win/Linux) from the plugin's "joystick configs" folder into that same directory.  
     **Note**: X-Plane updates sometimes overwrite these files — re-copy if needed after an XP update.

5. **Install the Lua script**:  
   Copy `Honeycomb Bravo.lua` to:  
   `X-Plane 12/Resources/plugins/FlyWithLua/Scripts/`

6. **Launch X-Plane and calibrate**:  
   - Load any aircraft (start with default C172 to test).  
   - **Immediately rotate the left autopilot knob (the mode selector with IAS/CRS/HDG/VS/ALT labels) all the way counter-clockwise to the IAS position**. This syncs/calibrates the script to the hardware.  
     → **Do this every time you load a new aircraft** — it's the most common "why isn't it working?" fix.

7. **Map the knobs in X-Plane**:  
   Go to **Settings → Joystick & Equipment → Axis** (or search for commands):  
   - **Right knob (encoder wheel)**:  
     - Increase → Assign `HoneycombBravo/increase`  
     - Decrease → Assign `HoneycombBravo/decrease`  
   - **Left knob (mode selector positions)**:  
     - IAS position → `HoneycombBravo/mode_ias`  
     - CRS → `HoneycombBravo/mode_crs`  
     - HDG → `HoneycombBravo/mode_hdg`  
     - VS → `HoneycombBravo/mode_vs`  
     - ALT → `HoneycombBravo/mode_alt`

8. **Other controls**:  
   Throttles, mixture, prop, flaps, gear, trim wheel, autopilot buttons (AP, HDG, NAV, APR, REV, etc.), and annunciator LEDs work via the `.joy` file and plugin — map them normally in X-Plane if needed, or use defaults.

9. **Test**:  
   Load the C172 or Zibo 738 → engage autopilot modes → twist knobs → watch LEDs light up and values change smoothly. It should feel native and responsive.

### Quick Troubleshooting
- **Knobs/LEDs not responding** → Re-calibrate left knob to IAS; restart XP; check Log.txt for errors.
- **After XP update** → Re-copy `.joy` files if overwritten.
- **Mac-specific** → This is one of the best native Apple Silicon solutions — many users prefer it over official tools.
- **More aircraft support** → Check the plugin's discussion/comments on the download page for user updates or forks.

This setup is widely praised in the community (e.g., forum threads and YouTube tutorials from 2024–2025) as the cleanest, most reliable way to get full autopilot functionality on the Bravo in X-Plane 12. If issues persist, post in the plugin's thread: https://forums.x-plane.org/files/file/89635-honeycomb-bravo-plugin/ (read comments for tips).

# OverTheWire: Natas Walkthrough Notes

> Level 0 

> Level Information
- **URL**: `http://natas0.natas.labs.overthewire.org`
- **Username**: `natas0`
- **Password**: `natas0`
- **Goal**: Find the password for natas1


> Solution Steps
1. Open browser and navigate to the URL above
2. Enter credentials when prompted:
   - Username: natas0
   - Password: natas0

>Step 2: Initial Observation
The page displays: *"You can find the password for the next level on this page."  

>Step 3: View Page Source

**Method A - Direct Browser (Easiest)** 
- **Right-click** anywhere on the page and select **"View Page Source"**
- OR use keyboard shortcut: `Ctrl + U` (Windows/Linux) or `Cmd + U` (Mac)

**Method B - Using Burp Suite** 
1. Configure Burp Suite as a proxy 
2. Ensure **"Intercept is on"** 
3. *Right-click* anywhere in the     intercepted request
   - Select *"Send to Repeater"* from the context menu
4. Click on **Repeater** tab (next to Proxy tab)
   - You'll see the captured request waiting there  

5. In Repeater, click the **"Send"** button
   - The response appears in the right panel   
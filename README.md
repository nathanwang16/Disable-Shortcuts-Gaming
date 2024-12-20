# **Karabiner-Elements JSON File Manual**

!!!GPT4o Generated!!!

This Karabiner-Elements configuration script is designed to disable specific keyboard shortcuts when Minecraft is the active application. It ensures that certain key combinations do not interfere with gameplay by temporarily disabling them.

---

### **What the Script Does**

1. **Disables Specific Shortcuts**:

   - **Command+1** and **Command+2**: Commonly used for tab or view switching.
   - **Command+Space**: Opens Spotlight search, which can interrupt gameplay.
   - **Command+Tab**: Used for switching applications.
   - **Control+Tab**: Used for tab navigation.
   - **Command+Q**: Used to quit applications, often accidentally.
   - **Caps Lock**: Prevents its functionality during gameplay.
2. **Applies Rules Only to Minecraft**:

   - These key combinations are disabled **only** when Minecraft is the active application.
   - The script uses Minecraft’s unique application identifiers to ensure other apps are unaffected.
3. **Automatically Re-Enables Shortcuts**:

   - When you switch away from Minecraft, all disabled shortcuts are restored automatically.

---

### **How to Use This Script**

#### **Step 1: Install Karabiner-Elements**

1. Download and install Karabiner-Elements from the official website: [https://karabiner-elements.pqrs.org](https://karabiner-elements.pqrs.org).
2. Open Karabiner-Elements and ensure it’s working by checking the preferences.

---

#### **Step 2: Configure the Script**

1. Locate the Karabiner configuration file:

   - Path: `~/.config/karabiner/karabiner.json`.
   - If the folder or file does not exist, create it manually.
2. Open the configuration file in a text editor:

   ```bash
   nano ~/.config/karabiner/karabiner.json
   ```
3. Add the script under the `"profiles"` section:

   - Copy and paste the configuration provided into the `"complex_modifications"` → `"rules"` section.

---

#### **Step 3: Reload Karabiner-Elements**

1. Save the file and close the text editor.
2. Restart Karabiner-Elements:
   - Open Karabiner Preferences → Quit and reopen the app.
   - Alternatively, click "Reload Karabiner-Elements" in the Misc tab.

---

### **Customizing the Script**

1. **Modify Shortcut Rules**:

   - Add or remove shortcuts by editing the `"from"` section in the script.
   - Example: To disable **Command+W**, add:
     ```json
     {
       "key_code": "w",
       "modifiers": {
         "mandatory": ["command"]
       }
     }
     ```
2. **Add New Applications**:

   - Replace the `bundle_identifiers` with the identifier of another app to apply the rules to it.
   - Use Karabiner’s EventViewer to find the app’s bundle identifier.

---

### **Tips for Using the Script**

1. Ensure Minecraft’s bundle identifier is correct:

   - Default: `"^com\\.mojang\\.minecraftlauncher.*"`.
   - Check using Karabiner’s EventViewer if needed.
2. Test the script:

   - Open Minecraft and confirm the specified shortcuts are disabled.
   - Switch to another app and confirm the shortcuts are restored.

---

### **Preparation Checklist**

- Install Karabiner-Elements.
- Verify the correct configuration file location (`~/.config/karabiner/karabiner.json`).
- Use a text editor to modify the JSON configuration.
- Test the setup after applying the changes.

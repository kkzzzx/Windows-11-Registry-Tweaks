# Windows-11-Registry-Tweaks
List of latest actually working registry tweaks for Windows 11 that make it better. To skip doing this manually, go to Releases to download .reg files which you can run to commit these steps with no effort and risk <b>(FILES ARE ONLY FOR THE REGISTRY EDITOR PARTS AND DO NOT DO ANYTHING OUTSIDE IT, WHICH YOU HAVE TO DO MANUALLY!)</b>
<hr>
Working editions: <b>Home, Pro, Enterprise</b><br>
Working versions: <b>23H2, 24H2, 25H2</b>
<hr>
⚠️ <b>READ THIS BEFORE MOVING FORWARD!</b><br>
Editing the Windows Registry can cause serious system problems, including system instability as software might stop working as expected. Always create a <b><a href="https://support.microsoft.com/en-us/windows/system-restore-a5ae3ed9-07c4-fd56-45ee-096777ecd14e" target="_blank">restore point</a></b> beforehand, <b><a href="https://support.microsoft.com/en-us/topic/how-to-back-up-and-restore-the-registry-in-windows-855140ad-e318-2a13-2829-d428a2ab0692" target="_blank">back up the registry</a></b>, and follow steps strictly — using the exact key names and values provided. Everything is <b>CASE-SENSITIVE</b> and every name, word or number should be <b>EXACTLY</b> as this guide is showing!
<hr>
<b>1. 🕗 Show seconds in Windows Clock</b><br><br>
<img width="95" height="50" alt="Time" src="https://github.com/user-attachments/assets/ab8d5da5-07fa-4c29-8886-7a8f2540d8a3" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
⚙️ <b>In Settings (safer and easier)</b>: Enter <b>Settings</b> (Win key + I) and go to <b>Time & language > Date & time > Show time and date in the System Tray</b> and check <b>Show seconds in System Tray clock (uses more power)</b><br><br>
<b>🗃️ In Registry Editor</b><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced</b> (copy and paste the path in the Registry Editor)<br>
3. On the right side look for value called <b>ShowSecondsInSystemClock</b><br>
4. If the value exists, double click it and change value from 0 to 1.<br>
5. <b>If value does not exist</b>, right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
6. Name it <b>ShowSecondsInSystemClock</b> and hit Enter. Double click it and change value from 0 to 1.<br>
7. Open <b>Task Manager</b> go to <b>Processes</b> tab and search for <b>Windows Explorer</b> process. <b>Right click it and hit restart.</b><br>
8. Explorer should go black for 1-2 seconds and when it appears again, it will show seconds!
</details>
<hr>
<b>2. 🔧 Stop Windows 11 from f***ing up (installing) new drivers</b><br><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
1. Search for <b>View advanced system settings</b> and <b>System Properties</b> should open up.<br>
2. Go to <b>Hardware</b> tab and click <b>Device Installation Settings</b>.<br>
3. When Device Installation Settings appears select <b>No (your device might not work as expected)</b> (don't worry about the warning, it works perfectly fine but if, in rare circumstances, it doesn’t, you can always manually update the drivers)<br>
4. Press <b>Save changes</b> and close the window.<br><br>
V 📢 <b>(for Pro / Enterprise editions only)</b><br>
5. Search for <b>Edit group policy</b> and <b>Local Group Policy Editor</b> should open up.<br>
6. Go to <b>Computer Configuration > Administrative Templates > Windows Components > Windows Update > Manage updates offered from Windows Update</b><br>
7. Look for <b>Do not include driver with Windows Update</b>, double click it, check <b>Enabled</b> and click Apply > OK, then close window.<br><br>
V ✅ <b>(for all editions)</b><br>
8. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
9. Go to <b>Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows</b> (copy and paste the path in the Registry Editor)<br>
10. Look for key (folders on the left side) named <b>WindowsUpdate</b>. If it doesn't exist, right click parent folder <b>Windows</b> and hover over <b>New ></b> and click <b>Key</b><br>
11. Name it <b>WindowsUpdate</b> and hit Enter. Click the newly created folder and right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
12. Name it <b>ExcludeWUDriversInQualityUpdate</b> and hit Enter. Double click it and change value from 0 to 1.<br>
13. <b>Restart the Windows</b> so it can take effect!
</details>
<hr>
<b>3. ✨ Remove Recommended from the Start Menu</b><br><br>
<img width="422" height="462" alt="recommend" src="https://github.com/user-attachments/assets/fce4be2b-c5d6-4ebc-b929-a14110e6a3ce" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\current\device\Start</b> (copy and paste the path in the Registry Editor)<br>
3. Right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
4. Name it <b>HideRecommendedSection</b> and hit Enter. Double click it and change value from 0 to 1.<br>
5. Go to <b>Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PolicyManager\current\device\Education</b> (copy and paste the path in the Registry Editor)<br>
6. Right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
7. Name it <b>IsEducationEnvironment</b> and hit Enter. Double click it and change value from 0 to 1.<br>
8. Go to <b>Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Explorer</b> (copy and paste the path in the Registry Editor)<br>
9. Right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
10. Name it <b>HideRecommendedSection</b> and hit Enter. Double click it and change value from 0 to 1.<br>
11. Open <b>Task Manager</b> go to <b>Processes</b> tab and search for <b>Windows Explorer</b> process. <b>Right click it and hit restart.</b><br>
12. Explorer should go black for 1-2 seconds and when it appears again, Recommended section will be removed!
</details>
<hr>
<b>4. 🌐 Remove Web Search from the Search Menu</b><br><br>
<img width="400" height="342.5" alt="web" src="https://github.com/user-attachments/assets/295164cd-6564-46cd-b026-8bc7deb1581c" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_CURRENT_USER\Software\Policies\Microsoft\Windows\Explorer</b> (copy and paste the path in the Registry Editor)<br>
3. Look for key (folders on the left side) named <b>Explorer</b>. If it doesn't exist, right click parent folder <b>Windows</b> and hover over <b>New ></b> and click <b>Key</b><br>
4. Name it <b>Explorer</b> and hit Enter. Click the newly created folder and right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
5. Name it <b>DisableSearchBoxSuggestions</b> and hit Enter. Double click it and change value from 0 to 1.<br>
6. Open <b>Task Manager</b> go to <b>Processes</b> tab and search for <b>Windows Explorer</b> process. <b>Right click it and hit restart.</b><br>
7. Explorer should go black for 1-2 seconds and when it appears again, Web Search will be removed!
</details>
<hr>
<b>5. ↗️ Remove shortcut arrow icon</b><br><br>
<img width="160" height="96" alt="chrome" src="https://github.com/user-attachments/assets/dba2fa36-a095-4188-9b85-fe7bb94456d8" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer</b> (copy and paste the path in the Registry Editor)<br>
3. Right click parent folder <b>Explorer</b> and hover over <b>New ></b> and click <b>Key</b><br>
4. Name it <b>Shell Icons</b> and hit Enter. Click the newly created folder and right click the empty space on the right side, hover over <b>New ></b> and click <b>String Value</b><br>
5. Name it <b>29</b> and hit Enter. Double click it and set the value to <b>C:\Windows\System32\imageres.dll,197</b><br>
6. <b>Restart the Windows</b> so it can take effect!
</details>
<hr>
<b>6. 🚀 Verbose Startup / Shutdown messages</b><br><br>
<img width="540.5" height="360" alt="messages" src="https://github.com/user-attachments/assets/a62b6799-31af-4403-9a9b-51224de1f5bd" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System</b> (copy and paste the path in the Registry Editor)<br>
3. Look for DWORD value (values on the right side) named <b>VerboseStatus</b>. If it doesn't exist, right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
4. Name it <b>VerboseStatus</b> and hit Enter. Double click it and change value from 0 to 1.<br>
6. <b>Restart the Windows</b> so it can take effect!
</details>
<hr>
<b>7. 📝 Restore Old right click Context Menu</b><br><br>
<img width="588" height="323.1" alt="context" src="https://github.com/user-attachments/assets/ef7b88fb-a8d3-4dfd-bc1d-b8380824eec8" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_CURRENT_USER\Software\Classes\CLSID</b> (copy and paste the path in the Registry Editor)<br>
3. Right click parent folder <b>CLSID</b> and hover over <b>New ></b> and click <b>Key</b><br>
4. Name it <b>{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}</b> and hit Enter. Right click the newly created folder and hover over <b>New ></b> and click <b>Key</b><br>
5. Name it <b>InprocServer32</b> and hit Enter. Click the newly created folder and double click the <b>Default</b> string value. Don't change anything and click OK.<br>
6. Open <b>Task Manager</b> go to <b>Processes</b> tab and search for <b>Windows Explorer</b> process. <b>Right click it and hit restart.</b><br>
7. Explorer should go black for 1-2 seconds and when it appears again, it will be restored!
</details>
<hr>
<b>8. 📌 Restore Ribbon Command Bar</b><br><br>
<img width="711.5" height="377.5" alt="ribbon" src="https://github.com/user-attachments/assets/26c75755-3f16-4620-99e7-71b2f6a7ee9e" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
🎛️ <b>Control Panel (not parmanent)</b><br>
Open <b>Control Panel</b> and click <b>Up Arrow ↑</b> in the top left corner and it should bring it back temporarily!<br><br>
<b>🗃️ In Registry Editor (parmanent)</b><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Shell Extensions</b> (copy and paste the path in the Registry Editor)<br>
3. Look for key (folders on the left side) named <b>Blocked</b>. If it doesn't exist, right click parent folder <b>Shell Extensions</b> and hover over <b>New ></b> and click <b>Key</b><br>
4. Name it <b>Blocked</b> and hit Enter. Click the newly created folder and right click the empty space on the right side, hover over <b>New ></b> and click <b>String Value</b><br>
5. Name it <b>{e2bf9676-5f8f-435c-97eb-11607a5bedf7}</b> and hit Enter. Don't change anything.<br>
6. Open <b>Task Manager</b> go to <b>Processes</b> tab and search for <b>Windows Explorer</b> process. <b>Right click it and hit restart.</b><br>
7. Explorer should go black for 1-2 seconds and when it appears again, it will be restored!
</details>
<hr>
<b>9. 🎨 Change left click Highlight colors</b><br><br>
<img width="351" height="144" alt="highlight" src="https://github.com/user-attachments/assets/f18d2abd-81bb-445d-833f-8defe3ec4591" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
(In the <b>Releases</b>, strings contain <b>default</b> values. Open with <b>Notepad</b> and change values according to your preferences, than save the file and run it! Manual changes are provided under.<br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_CURRENT_USER\Control Panel\Colors</b> (copy and paste the path in the Registry Editor)<br>
3. Look for String values (values on the right side) named <b>Hilight</b> and <b>HotTrackingColor</b><br>
4. <b>Hilight</b> changes highlight <b>BORDER</b>, <b>HotTrackingColor</b> changes highlight <b>FILL</b><br>
5. Each value contains <b>RGB</b> value of a color! You can add your own but they should be this format without dots or commas. Examples:<br>
Red 🟥 - 255 0 0<br>
Blue 🟦 - 0 0 255<br>
Green 🟩 - 0 255 0<br>
Yellow 🟨 - 255 255 0<br>
Purple 🟪 - 204 0 204<br>
White ⬜ - 255 255 255<br>
6. Double click the value you wanna change (border or fill), replace old rgb value with a new one and click OK.<br>
7. <b>Restart the Windows</b> so it can take effect!
</details>
<hr>
<b>10. 🔒 Remove Lock Screen (PIN/Fingerprint screen shows up immediately)</b><br><br>
<img width="700" height="394.1" alt="lock" src="https://github.com/user-attachments/assets/c67a9058-6b7b-4f30-82c6-607fa4dd82bd" /><br>
<details>
<summary>Click to reveal step by step guide.</summary><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows</b> (copy and paste the path in the Registry Editor)<br>
3. Right click parent folder <b>Windows</b> and hover over <b>New ></b> and click <b>Key</b><br>
4. Name it <b>Personalization</b> and hit Enter.  Click the newly created folder and right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
5. Name it <b>NoLockScreen</b> and hit Enter. Double click it and change value from 0 to 1.<br>
6. <b>Restart the Windows</b> so it can take effect!
</details>
<hr>

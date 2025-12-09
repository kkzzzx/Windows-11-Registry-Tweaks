# Windows-11-Registry-Tweaks
List of latest actually working registry tweaks for Windows 11 that make it better. To skip doing this manually, go to Releases to download .reg files which you can run to commit these steps with no effort and risk <b>(FILES ARE ONLY FOR THE REGISTRY EDITOR PARTS AND DO NOT DO ANYTHING OUTSIDE IT, WHICH YOU HAVE TO DO MANUALLY!)</b>
<hr>
Working editions: <b>Home, Pro, Enterprise</b><br>
Working versions: <b>23H2, 24H2, 25H2</b>
<hr>
⚠️ <b>READ THIS BEFORE MOVING FORWARD!</b><br>
Editing the Windows Registry can cause serious system problems, including system instability as software might stop working as expected. Always create a <b><a href="https://support.microsoft.com/en-us/windows/system-restore-a5ae3ed9-07c4-fd56-45ee-096777ecd14e" target="_blank">restore point</a></b> beforehand, back up the registry, and follow steps strictly — using the exact key names and values provided.
<hr>
<b>1. 🕗 Show seconds in Windows Clock</b><br><br>
<img width="95" height="50" alt="Time" src="https://github.com/user-attachments/assets/ab8d5da5-07fa-4c29-8886-7a8f2540d8a3" /><br><br>
⚙️ <b>In Settings (safer and easier)</b>: Enter <b>Settings</b> (Win key + I) and go to <b>Time & language > Date & time > Show time and date in the System Tray</b> and check <b>Show seconds in System Tray clock (uses more power)</b><br><br>
<b>🗃️ In Registry Editor</b><br>
1. Search and open <b>Registry Editor</b> and press Yes when <i>User Account Control</i> pops up.<br>
2. Go to <b>Computer\HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced</b> (copy and paste the path in the Registry Editor)<br>
3. On the right side look for value called <b>ShowSecondsInSystemClock</b><br>
4. If the value exists, double click it and change value data from 0 to 1.<br>
5. <b>If value does not exist</b>, right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
6. Name it <b>ShowSecondsInSystemClock</b> and hit Enter. Double click it and change value from 0 to 1.<br>
7. Open <b>Task Manager</b> go to <b>Processes</b> tab and search for <b>Windows Explorer</b> process. <b>Right click it and hit restart.</b><br>
8. Explorer should go black for 1-2 seconds and when it appears again, it will show seconds!
<hr>
<b>2. 🔧 Stop Windows 11 from f***ing up (installing) new drivers</b><br><br>
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
10. Look for key (folders on the left side) named <b>Windows Update</b>. If it doesn't exist, right click parent folder <b>Windows</b> and hover over <b>New ></b> and click <b>Key</b><br>
11. Name it <b>Windows Update</b> and hit Enter. Click the newly created folder and right click the empty space on the right side, hover over <b>New ></b> and click <b>DWORD (32-bit) Value</b><br>
12. Name it <b>ExcludeWUDriversInQualityUpdate</b> and hit Enter. Double click it and change value from 0 to 1.<br>
13. <b>Restart the Windows</b> so it can take effect!
<hr>
<b>3. ✨ Remove Recommended from the Start Menu</b><br><br>
<img width="422" height="462" alt="recommend" src="https://github.com/user-attachments/assets/fce4be2b-c5d6-4ebc-b929-a14110e6a3ce" /><br>
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
12. <b>Restart the Windows</b> so it can take effect!
<hr>

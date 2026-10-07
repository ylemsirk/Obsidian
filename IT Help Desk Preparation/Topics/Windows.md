### Windows Fundamentals & Navigation

1. What are the main differences between Windows 10 and Windows 11 that a Help Desk technician should know when supporting remote users (UI changes, system requirements, feature differences)?
    
2. Explain the differences between Windows Home, Pro, Enterprise, and Education editions. Why is it important for a Help Desk agent to know which edition a user has before troubleshooting certain features (e.g., BitLocker, Remote Desktop host, local Group Policy)?
    
3. A user says their Start menu is not responding. What remote troubleshooting steps would you take? Include restarting Windows Explorer, checking for pending updates, and using Ctrl+Shift+Esc to access Task Manager.
    
4. How would you remotely guide a user to check their Windows version, build number, and edition? Why is the build number important when troubleshooting a recent issue after an update?
    
5. Explain the purpose of the Settings app versus the Control Panel. Give two examples of tasks that can only be done in one or the other, and how you would guide a user to find a specific setting.
    
6. What is the system tray, and how would you help a user find a missing icon (e.g., antivirus, VPN, or OneDrive) that has been hidden? Include how to customize which icons appear.
    
7. A user cannot find a file they saved recently. What Windows search tools and File Explorer options (recent files, search filters, indexing) would you use remotely to help them locate it?
    
8. Describe the Windows virtual desktop feature. How can it help a user organize their work, and what common confusion might a user have when they accidentally switch desktops?
    
9. What are the most useful Windows keyboard shortcuts for remote support (e.g., Win+R, Win+X, Ctrl+Shift+Esc, Win+P, Alt+Tab)? Give a scenario for each where it saves time during a remote session.
    
10. A user complains that their display looks zoomed in or text is too small. How would you guide them to adjust display scaling and resolution in Windows Settings?
    

---

### Local User Accounts & Profiles

11. Explain the difference between a local Administrator account, a Standard user account, and a Guest account. Why should remote users generally work as Standard users, and what limitations would they experience?
    
12. How would you remotely guide a user to create a new local user account in Windows? What are the steps in Settings, and why might you create a temporary account for troubleshooting?
    
13. What is User Account Control (UAC), and why does it prompt for permission when installing software or changing system settings? How would you explain a UAC prompt to a frustrated user who thinks it is a virus?
    
14. A user logs in and sees a message “You've been signed in with a temporary profile.” What does this mean, what are the risks (data loss), and what steps would you take to resolve it remotely?
    
15. Describe the folder structure of a Windows user profile (Desktop, Documents, Downloads, AppData). A user says their files are “gone” after logging into a different account. How would you check if the files are in another profile's folder?
    
16. What is Windows Hello, and how do PIN, fingerprint, and facial recognition differ from a traditional password? A user forgot their PIN but knows their password. How would you guide them to reset the PIN remotely?
    
17. Explain the purpose of Credential Manager. A user keeps getting prompted for a password to access a network share even after checking “Remember me.” How would you check and clear stored credentials remotely?
    
18. How would you remotely reset a local user account password if the user forgot it? What are the limitations and risks, and what precautions must you take to verify identity?
    
19. A user wants to change their account picture and screen saver. Walk through the remote steps in Windows Settings, and explain why these settings might be locked by an administrator (without going into Active Directory).
    
20. What is the difference between signing out, switching users, locking the computer, and restarting? In what remote support scenario would you use each, and what are the risks of choosing the wrong one while a user has unsaved work?
    

---

### System Tools & Diagnostics

21. Explain the main tabs of Task Manager (Processes, Performance, App History, Startup, Users, Details, Services). How would you remotely guide a user to use Task Manager to identify a program that is freezing their computer?
    
22. What is Resource Monitor, and how does it differ from Task Manager? In a scenario where a user reports high disk usage but Task Manager shows only “System” consuming it, how would you use Resource Monitor to drill down?
    
23. Describe Event Viewer and its main log categories (Application, Security, System). A user's computer restarted unexpectedly. How would you remotely guide them to find the critical event (e.g., Event ID 41, Kernel‑Power) and what would it tell you?
    
24. What is Reliability Monitor, and how can it help you quickly see a timeline of crashes, updates, and software installations? Walk through a remote scenario where a user's PC started crashing after a specific date.
    
25. Explain the purpose of Device Manager. A user's webcam stopped working. How would you remotely guide them to check for a yellow exclamation mark, update the driver, or roll back the driver?
    
26. What is services.msc, and how would you remotely help a user check if a specific service (e.g., Windows Audio, Print Spooler) is running or stopped? How would you restart a service, and what caution should you take?
    
27. What is System Configuration (msconfig), and how does it differ from Task Manager's Startup tab? When would you use msconfig for a “clean boot” to diagnose a performance or startup issue?
    
28. Describe the Computer Management console. What tools does it contain (Disk Management, Event Viewer, Services, Local Users and Groups), and how would you remotely guide a user to open it?
    
29. What is the Windows Memory Diagnostic tool, and when would you use it? A user experiences random BSODs with memory‑related error codes. How would you guide them to run the diagnostic remotely?
    
30. What is dxdiag, and how can it help when troubleshooting graphics or audio issues? How would you remotely guide a user to run it and interpret the display/sound tabs?
    

---

### Performance & Maintenance

31. A user reports their computer is extremely slow. Walk through a remote diagnostic sequence using Task Manager, checking CPU, memory, disk, and startup programs. What are the most common causes you would identify and how would you address each?
    
32. Explain the difference between high CPU usage caused by a legitimate application (e.g., video editing) versus a background process or malware. How would you determine the difference remotely?
    
33. A user's PC shows 100% disk usage constantly. List at least four common causes (Windows Search, SysMain/Superfetch, Windows Update, antivirus scan, failing HDD) and describe how you would identify and mitigate each remotely.
    
34. How would you guide a user to safely disable unnecessary startup programs? What is the difference between disabling a startup item and uninstalling the application, and what risks should you warn the user about?
    
35. What is Disk Cleanup, and how does it differ from Storage Sense? Walk through a remote session where a user needs to free up 10 GB of space quickly. What would you clean first?
    
36. Explain the difference between defragmentation (for HDDs) and TRIM (for SSDs). Why should you never defragment an SSD, and how would you remotely verify the type of drive a user has?
    
37. A user's Windows Update is stuck at “Downloading 0%.” What remote troubleshooting steps would you take, including restarting the Windows Update service, running the built‑in troubleshooter, and clearing the SoftwareDistribution folder?
    
38. A user says their computer broke after a Windows update. How would you remotely roll back a quality update or feature update? What are the time limits (e.g., 10 days to roll back a feature update) and what data should you warn them about?
    
39. Explain the difference between a quality update, a feature update, and a driver update. Which one is most likely to cause issues immediately after installation, and how would you prioritize troubleshooting?
    
40. A user receives a message that Windows is not activated. What are the common causes (hardware change, license expired, wrong edition), and how would you remotely guide them to check activation status and re‑enter a product key?
    

---

### Storage, Files & Backup

41. Describe Disk Management. A user plugged in a new external drive, but it does not appear in File Explorer. How would you remotely guide them to check Disk Management, assign a drive letter, or initialize the disk?
    
42. Explain the basics of NTFS permissions (Full Control, Modify, Read & Execute, Read, Write). A user cannot delete a file even though they created it. What permission issue might be occurring, and how would you troubleshoot remotely?
    
43. How would you remotely set up a simple file share on a Windows PC so a user can share a folder with a colleague on the same local network? What permissions and sharing settings must be configured?
    
44. What is BitLocker, and why is it important for laptops? A remote user's laptop is asking for a BitLocker recovery key after a BIOS update. How would you guide them to find the key (Microsoft account, USB, printed copy) and what should you do if it cannot be found?
    
45. Explain File History and how it differs from a full system image backup. A user accidentally deleted an important document a week ago. How would you remotely check if File History or Previous Versions can recover it?
    
46. What is System Restore, and how does it differ from a backup? A user installed a bad driver and now their PC is unstable. Walk through the remote steps to use System Restore, and explain what it does and does not restore.
    
47. A user emptied the Recycle Bin but needs a file back. What options exist within Windows (Previous Versions, File History, third‑party tools), and how would you set expectations about success rates?
    
48. What is the difference between a quick format and a full format? A user wants to wipe a USB drive before giving it away. What would you recommend to ensure data cannot be recovered, and how would you guide them remotely?
    
49. How would you remotely help a user map a network drive? What information do you need (server name, share name, credentials), and what common errors (e.g., “The network path was not found,” “Access is denied”) would you troubleshoot?
    
50. Explain OneDrive integration in Windows. A user says their files are “missing” but they see OneDrive icons in File Explorer. How would you explain Files On‑Demand and how to make files always available offline?
    

---

### Security & Protection

51. Describe the Windows Security Center and its main areas (Virus & threat protection, Firewall & network protection, App & browser control, Device security). How would you remotely check if Windows Defender is active and up to date?
    
52. A user thinks they have a virus. What remote steps would you take to run a quick scan, a full scan, and an offline scan using Windows Defender? What would you do if the malware cannot be removed?
    
53. Explain the Windows Firewall and its three profiles (Domain, Private, Public). A user cannot access a specific application because the firewall is blocking it. How would you remotely create an inbound or outbound rule to allow it? (Keep it local, no Group Policy.)
    
54. What is Controlled Folder Access, and how does it protect against ransomware? A user is trying to save a file to their Documents folder but gets an error that it is blocked. How would you troubleshoot this remotely?
    
55. What is Safe Mode, and how does it differ from a Clean Boot? A user's PC crashes constantly in normal mode but works in Safe Mode. What does that tell you, and what would be your next remote steps?
    
56. A user reports that their browser homepage changed and they see pop‑up ads. What remote steps would you take to remove potentially unwanted programs (PUPs) and reset browser settings across Chrome, Edge, and Firefox?
    
57. Explain User Account Control (UAC) settings and why lowering them is dangerous. A user wants to disable UAC to stop prompts. How would you respond, and what safer alternative could you offer?
    
58. What is Windows Sandbox, and when might it be useful for a remote user? What are its limitations (requires Pro/Enterprise, not for production use)?
    
59. A user received a suspicious email attachment and opened it. What immediate remote actions would you take to check for compromise, including running a Defender scan, checking Task Manager for unusual processes, and reviewing Event Viewer for suspicious logons?
    
60. How would you remotely check if a Windows PC has pending security updates and whether the antivirus definitions are current? What would you do if updates are failing repeatedly?
    

---

### Troubleshooting & Recovery

61. A user reports a Blue Screen of Death (BSOD). They wrote down the stop code “IRQL_NOT_LESS_OR_EQUAL.” What does this suggest, and what remote steps would you take to identify the problematic driver or hardware?
    
62. Explain the Windows Recovery Environment (WinRE). How would you guide a user to access it (holding Shift while clicking Restart), and what tools are available (Startup Repair, System Restore, Command Prompt)?
    
63. What is “Reset this PC,” and how does it differ from a clean install? A user wants to reset their PC but keep their files. Walk through the remote steps and explain the “Keep my files” versus “Remove everything” options.
    
64. A user's computer will not boot past the manufacturer logo. What remote steps could you guide them through using Advanced Startup options, and at what point would you escalate to a hardware technician?
    
65. A specific application crashes every time the user opens it. How would you remotely troubleshoot: checking Event Viewer for the faulting module, reinstalling the application, running it as administrator, or checking for compatibility mode?
    
66. Windows Explorer keeps crashing and restarting. What remote steps would you take: checking for shell extensions, running sfc /scannow, and testing in Safe Mode?
    
67. The Start menu and Search stop working after an update. What remote fixes would you try: restarting Windows Explorer, running the Windows Search troubleshooter, checking for corrupted system files, or creating a new user profile?
    
68. A user's taskbar is missing or unresponsive. What remote steps would you take to restore it (Ctrl+Shift+Esc, restart explorer.exe, check for pending updates)?
    
69. A user reports no audio from their speakers. Walk through remote troubleshooting: checking playback devices, volume mixer, Windows Audio service, and reinstalling the audio driver.
    
70. A user's external monitor is not detected. What remote steps would you take: pressing Win+P, checking display settings, updating graphics driver, and testing with a different cable or port?
    
71. A user cannot print to a network printer. What remote steps would you take: checking the print queue, verifying the printer is online, pinging the printer's IP, and reinstalling the printer driver?
    
72. Windows is running very slowly and sfc /scannow reports corrupted files it cannot fix. What remote options remain: DISM /RestoreHealth, System Restore, or a repair upgrade?
    
73. A user's clock is consistently wrong, causing website and authentication errors. How would you remotely check and fix time sync settings in Windows?
    
74. A user downloaded a program that installed unwanted toolbars and changed their browser settings. What remote steps would you take to remove the toolbars, reset the browser, and check for scheduled tasks that might reinstall them?
    
75. A user reports that their laptop battery drains extremely fast and Windows shows “Battery not detected.” What remote steps would you take to check battery health (powercfg /batteryreport) and determine if it is a driver issue or a hardware failure?
    

---

### Command Line Basics (Tier I Awareness)

76. What is the Command Prompt, and what are the most useful commands for a remote Help Desk technician (ipconfig, ping, tracert, sfc, chkdsk, netstat)? Give a scenario where each would be helpful.
    
77. What is PowerShell, and how does it differ from Command Prompt? What basic PowerShell commands would you use to check system information (Get‑ComputerInfo, Get‑Process) during a remote session?
    
78. How would you remotely guide a user to open an elevated Command Prompt or PowerShell window? Why is running as administrator sometimes necessary and what risks should you warn about?
    
79. What is the purpose of the sfc /scannow command, and how would you explain to a user what it does and how long it might take? What would you do if it finds errors but cannot fix them?
    
80. A user's disk is reporting errors. What is chkdsk, and how would you remotely run it safely? What is the difference between chkdsk /f and chkdsk /r, and what should you warn the user about before running it?
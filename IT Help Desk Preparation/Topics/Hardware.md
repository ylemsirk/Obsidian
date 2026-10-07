### Hardware Fundamentals & Identification

1. A user calls and says “my computer won’t turn on.” What are the first five questions you would ask to determine if the problem is power, battery, or hardware failure? Include questions about LEDs, fans, and power cables.
    
2. Explain the difference between RAM and storage (SSD/HDD) in simple terms a non‑technical user can understand. Give an example of when a user confuses the two and how that confusion might misdirect your troubleshooting.
    
3. You are remotely assisting a user who wants to know how much RAM their Windows PC has. What steps would you walk them through (without using any third‑party tools), and what screen would you have them read back to you?
    
4. A user reports their PC is “slow.” You suspect not enough RAM. What remote tools or commands would you use to check RAM usage and identify which application is consuming the most? How would you guide the user to close a memory‑hungry process using Task Manager?
    
5. What is the role of the motherboard in a computer? When a remote user reports that a specific port (e.g., USB or Ethernet) stops working, why might the motherboard be a suspect, and how would you rule out driver or cable issues first?
    
6. Describe the difference between an SSD and an HDD. A user asks if upgrading from HDD to SSD will make their laptop faster. How would you explain the benefits in terms of boot time, application loading, and durability, and what caveats (e.g., data migration) should you mention?
    
7. What is a GPU? Differentiate between integrated and dedicated graphics. A remote user working from home with a desktop suddenly sees no display output from the dedicated GPU but the system appears to be on. How would you guide them to test if the integrated GPU (if present) works by checking cable connections to the motherboard instead?
    
8. Explain what a PSU does and the common signs of a failing power supply. If a user reports random shutdowns under load, how would you remotely determine if it is likely a PSU issue versus overheating? What software or BIOS readings could you have them check?
    
9. What is a NIC (Network Interface Card)? A user’s Ethernet connection drops intermittently but Wi‑Fi works. How would you troubleshoot the NIC remotely: driver rollback, disabling/enabling in Device Manager, checking link speed, and testing with a different cable?
    
10. Compare a Wi‑Fi adapter (USB dongle vs built‑in). A remote user’s laptop suddenly cannot see any Wi‑Fi networks. What steps would you have them perform to rule out the adapter being disabled (airplane mode, physical switch, Fn key combo) before considering driver reinstallation?
    
11. Describe the purpose of a cooling system (fans, heatsinks, liquid cooling). A user hears a loud fan noise and the laptop is hot to the touch. What remote actions can you take: check CPU temperature via built‑in tools (if available), recommend elevating the laptop, cleaning vents, or adjusting power settings?
    
12. What is a docking station and how does it extend laptop connectivity? A remote user with a laptop and dock reports no video output to an external monitor. Outline the remote troubleshooting steps: checking dock power, cable connections, the laptop’s USB‑C/Thunderbolt port, and driver/firmware updates for the dock.

13. What is BIOS/UEFI? What settings might a Help Desk technician reasonably check, and which settings should not be changed without authorization?

14. When would you suspect a problem exists below the operating system level? Give examples where BIOS/UEFI diagnostics or vendor hardware diagnostics would be more useful than Windows troubleshooting.

15. What is POST, and what is the difference between a computer that fails POST, fails to boot the operating system, and boots Windows but becomes unusable?

16. Explain the basic boot sequence from pressing the power button to Windows loading. At what stages could a failure occur, and what symptoms would help you identify the stage?

17. Explain the basic boot sequence from pressing the power button to Windows loading. At what stages could a failure occur, and what symptoms would help you identify the stage?

18. What is BitLocker, and what should a Help Desk technician do if a user is prompted for a BitLocker recovery key after a hardware or firmware change? What information should never be requested or stored insecurely?

---

### Diagnostics & Performance Issues

19. A user says “my PC is running out of storage.” What built‑in Windows tool would you have them open to see what is taking up space, and how would you guide them to safely delete temporary files without causing data loss?
    
20. Explain what “Disk usage 100%” means in Task Manager and name three common causes (e.g., Windows Search, Superfetch/SysMain, antivirus scan). How would you remotely identify which process is causing it and what temporary or permanent fix would you apply?
    
21. You are remotely connected to a user’s PC and notice CPU usage is consistently at 95%+ with a process named “System” or “svchost.exe”. What is the first thing you would check to determine if it is legitimate Windows activity or malware, and what built‑in tools can you use?
    
22. A user’s laptop is overheating and shutting down during video calls. What remote steps can you take: checking power plan, reducing maximum processor state, updating BIOS/firmware, and guiding the user to clean vents or use a cooling pad?
    
23. What is the difference between “RAM insufficient” and “CPU overloaded” in terms of symptoms? How would you distinguish the two using Task Manager or Resource Monitor, and what different solutions would you propose for each?
    
24. A user reports that a newly installed USB device is “not detected.” List the remote troubleshooting sequence: checking Device Manager for unknown devices, trying different USB ports, testing on another computer (if possible), and updating/reinstalling drivers. How would you guide a non‑technical user through Device Manager?
    
25. You suspect a driver problem is causing a webcam to fail. What is the difference between rolling back a driver, uninstalling a device, and updating a driver in Device Manager? Which one would you try first, and why?
    
26. A user’s external hard drive appears in Device Manager but not in File Explorer. What is the likely cause (drive letter conflict, partition issue, or need for initialization)? How would you remotely guide them through Disk Management to assign a drive letter?
    
27. Describe the “Blue Screen of Death” (BSOD). A user sends you a photo of a BSOD with the error “MEMORY_MANAGEMENT.” What does this suggest, and what remote diagnostic steps can you take before recommending hardware replacement? Mention Windows Memory Diagnostic and checking for recent driver changes.
    
28. A user says their PC takes 10 minutes to boot. What are the most common causes (startup programs, HDD vs SSD, pending updates, malware) and how would you remotely check startup items using Task Manager or msconfig?
    
29. How can you remotely check if a laptop’s battery is failing? A user complains the battery drains from 100% to 10% in 30 minutes. What built‑in Windows report (powercfg /batteryreport) would you have them generate and what information would you look for?
    
30. You receive a ticket: “No sound from my speakers.” Walk through remote troubleshooting: checking volume mixer, default playback device, disabling/enabling audio driver, and testing with headphones to isolate the issue.
    
31. A user’s monitor displays “No Signal” after connecting via HDMI. What questions would you ask to determine if the issue is the cable, the monitor input selection, the laptop’s display output setting (duplicate/extend), or a hardware fault? How would you guide them through pressing Windows + P?
    

---

### Peripherals & Connectivity

32. Explain the difference between USB‑A, USB‑C, and Thunderbolt. A user wants to connect two external monitors to their laptop using a USB‑C dock but only one monitor works. How would you determine if the laptop’s USB‑C port supports video output (DisplayPort Alt Mode) and what specs to check?
    
33. What is the difference between HDMI and DisplayPort? A user has a monitor with both inputs and a laptop with HDMI output. They connect with HDMI and get no signal, but the monitor works with another PC via DisplayPort. What steps would you take to ensure the correct input is selected and the HDMI cable is not faulty?
    
34. A user reports their Bluetooth mouse keeps disconnecting. What remote steps can you take: checking battery level, removing and re‑pairing the device, updating Bluetooth drivers, and checking for interference from other wireless devices? How would you decide if the mouse is defective?
    
35. Describe how to remotely guide a user to connect a Bluetooth headset to a Windows PC for the first time. Include pairing mode, adding the device in Settings, and setting it as the default playback/recording device.
    
36. A user says their USB keyboard types the wrong characters or misses keystrokes. What could cause this (sticky keys, regional layout, damaged cable, low battery for wireless)? How would you remotely differentiate between a software setting and a hardware problem?
    
37. Explain the purpose of a driver for a printer. A remote user’s printer is connected via USB and prints garbled text. What is the first thing you would check (printer driver version, print queue, cable) and how would you reinstall the driver remotely using the manufacturer’s website?
    
38. A user has a multifunction printer (print/scan/copy) connected via network. Printing works, but scanning fails. Why might scanning require a separate driver or software (like WSD or TWAIN) and how would you troubleshoot remotely: checking services, reinstalling scanner driver, or using Windows Fax and Scan?

39. What is the difference between a locally attached printer, a network printer, and a printer deployed through a print server? How does the troubleshooting process differ for each?

40. What is the Windows Print Spooler service? What symptoms would indicate that the spooler is stuck or stopped, and how would you safely restart it?

41. A printer is reachable by ping but Windows reports it as offline. What does this tell you, and what would you investigate next?

42. A user can print a test page successfully, but one specific application cannot print. What does this suggest, and how would you narrow the issue to the application, driver, permissions, or print queue?

43. A user sends a document to the printer and the job remains stuck in the print queue. What troubleshooting steps would you take before deleting and reinstalling the printer?

44. What are the differences between common Windows printer ports such as WSD, Standard TCP/IP, USB, and a shared printer connection? When might the port configuration cause a printer to appear offline?
    
45. What is a headset’s “sidetone” or “mic monitoring”? A remote call center agent complains they can’t hear themselves in the headset. How would you adjust this in Windows sound settings or the vendor’s software, and what if the option is not available?
    
46. A user connects a USB flash drive and sees a message “USB device not recognized.” List the possible causes and remote fixes: power management settings disabling the USB port, driver corruption, the drive itself being dead, or the port being damaged. How would you guide the user to test on another computer?
    
47. Explain the difference between a webcam built into a laptop and an external USB webcam. A user’s external webcam is not detected during a video call, but the laptop’s built‑in camera works. What would you check: privacy shutter, USB port, camera permission settings in Windows, and the application’s video input selection?
    
48. A user reports their external monitor is detected by the laptop but the display is black. What Windows display settings would you have them check: multiple displays (extend vs duplicate), resolution, refresh rate, and graphics driver? How would you guide them to adjust these remotely?
    
49. You are supporting a remote user who uses a docking station with a laptop. When they undock and re‑dock, sometimes the external monitor does not come back on. What are possible causes (dock firmware, display driver, USB‑C power delivery) and what steps would you take to update the dock firmware remotely?
    
50. What is the purpose of “Safely Remove Hardware” for USB storage? A user yanks out a USB drive and later says files are missing. How would you explain the risk of data corruption and what built‑in tool can sometimes recover files? (Do not promise recovery, but check for previous versions or chkdsk.)
    
51. A user complains their mouse cursor moves erratically and jumps around the screen. Is this more likely a hardware issue or a software issue? How would you remotely rule out touchpad interference on a laptop, surface problems for an optical mouse, or driver issues?
    
52. Explain how to troubleshoot a webcam that shows a black screen during a Zoom call but works in the Windows Camera app. What settings in Zoom or the browser (permission for camera) could be causing the application to not access the camera, and how would you check them remotely?

53. When troubleshooting a device driver, how do you decide between updating, rolling back, uninstalling/reinstalling, or leaving the driver unchanged? What evidence would justify each action?

54. What hardware-related information can you find in Windows Event Viewer? Which logs or event types might help investigate unexpected shutdowns, driver failures, disk errors, or USB device problems?

55. What information do you need to verify before using or recommending a replacement charger, especially USB-C chargers? Consider voltage, wattage, USB Power Delivery support, and manufacturer requirements.

56. Why does the fact that two cables or ports use USB-C connectors not guarantee they support the same features? Give examples involving charging, data speed, video output, Thunderbolt, and USB4.
    

---

### Remote Support Scenarios (Higher Difficulty)

57. **Scenario:** A user calls and says their computer is frozen and unresponsive. The mouse and keyboard do nothing. What is the first remote action you can take (Ctrl+Alt+Del, check if remote session is frozen, or have them do a hard shutdown)? How would you decide between a clean restart and losing unsaved work?
    
58. **Scenario:** You are remotely connected to a user’s PC. You notice the CPU temperature is 95°C and the fan is running at maximum. The user says it happens only when they run a specific application. What would you check: power settings, CPU intensive processes, or a failing cooling fan? What immediate remote setting could you change to lower temperature while still allowing the app to run?
    
59. **Scenario:** A user reports that after a Windows update, their Wi‑Fi adapter disappeared from Device Manager. What steps would you take: checking for hidden devices, rolling back the driver, using System Restore, or downloading the driver from the manufacturer on another device and transferring via USB? How would you guide a non‑technical user through these?
    
60. **Scenario:** A user’s laptop battery is swollen (they notice the case bulging). They are working from home. What are the immediate safety instructions you must give, and what remote support actions are appropriate? (You must advise them to stop using it, unplug, and not puncture the battery.)
    
61. **Scenario:** A user connects a projector via HDMI to their laptop for a presentation, but the projector shows “No Input.” The laptop screen is on. How would you walk them through the steps: pressing Windows + P to cycle display modes, checking the HDMI cable, selecting the correct input on the projector, and checking display resolution compatibility?
    
62. **Scenario:** A remote employee uses a USB headset for calls. The audio quality is poor—cutting in and out. What are the possible causes: USB power management turning off the port, wireless interference (if Bluetooth), bandwidth issues, or a faulty USB cable? How would you adjust power settings remotely to prevent USB ports from sleeping?
    
63. **Scenario:** A user’s external webcam is recognized by Windows but not available in Microsoft Teams. The built‑in camera works in Teams. What Teams‑specific settings would you check (device permissions, app‑level camera selection) and how would you determine if it’s a Teams policy or a driver/software conflict?
    
64. **Scenario:** A user reports a “clicking” noise from their desktop PC and very slow file access. You suspect a failing HDD. What remote diagnostics would you run (chkdsk, SMART status via command line, or third‑party tools) and how would you interpret a high number of reallocated sectors? What advice would you give regarding backing up data immediately?
    
65. **Scenario:** A user has a laptop that will not charge when plugged in. The LED near the charging port is off. They have tried a different outlet and the same charger works with another laptop (if available). What would you check: the DC jack for damage, the charger’s wattage compatibility, and the battery health report? What evidence would allow you to distinguish between a likely charger, battery, charging port, or internal motherboard issue, and at what point should you stop troubleshooting remotely and escalate for physical inspection?
    
66. **Scenario:** A user’s external monitor flickers when connected via USB‑C dock. They have tried different cables and a different monitor; the issue persists. What could be the cause: dock firmware, laptop USB‑C port not providing enough power or bandwidth, or graphics driver? How would you remotely update the dock firmware and graphics driver, and what would you do if the problem persists?
    
67. **Scenario:** A user says their laptop’s keyboard has stopped working, but the on‑screen keyboard works. They are using a USB external keyboard now. What remote steps would you take: checking if the keyboard is disabled in Device Manager, updating the keyboard driver, or if a recent update caused a driver conflict? How would you guide them to check Device Manager for a yellow exclamation mark?
    
68. **Scenario:** A remote user reports that their computer randomly restarts when they play a graphics‑intensive game. The system is a desktop with a dedicated GPU. What would you suspect first: PSU insufficient wattage, overheating GPU, or driver crash? How would you gather evidence remotely (checking Windows Event Viewer for critical Kernel‑Power 41 events) and what recommendation would you make if the PSU is underpowered?
    
69. **Scenario:** A user’s laptop is extremely slow and Task Manager shows 100% disk usage with “System” process writing constantly. You suspect Windows Search indexer or Superfetch. What commands or settings can you change remotely to stop these services temporarily and see if performance improves? How would you explain the change to the user?
    
70. **Scenario:** A user wants to connect a second monitor to their laptop using a USB‑C to HDMI adapter. They plug it in, but nothing happens. The laptop’s USB‑C port is only for data (no video). How would you confirm this by checking the laptop’s specs online or in the manual, and what alternative would you suggest (e.g., using a USB display adapter or a different port)?
    
71. **Scenario:** A user reports that their wireless mouse and keyboard are both lagging badly. They are in a home office with many other wireless devices. What could cause interference (Wi‑Fi on 2.4 GHz, USB 3.0 ports causing RF noise, low batteries) and how would you guide them to test by moving devices or using a USB extension cable for the receiver?
    
72. **Scenario:** You receive a ticket that a user’s printer is offline. The printer is connected via Wi‑Fi. The user says other devices can print. What steps would you take: checking the printer’s IP address, pinging it from the user’s PC, ensuring the correct printer is set as default, and clearing the print queue. How would you remotely guide the user to run a ping test?
    
73. **Scenario:** A user’s webcam image is upside down. What could cause this (driver setting, physical mounting, or application rotation) and how would you fix it remotely by adjusting the camera’s properties in Device Manager or the application’s settings?
    
74. **Scenario:** A laptop user cannot adjust screen brightness. The brightness slider is grayed out. What are the possible causes: display driver issue, missing monitor driver, or a policy setting? How would you remotely reinstall the display driver and check for any group policy restrictions?
    
75. **Scenario:** A user’s external monitor shows a message “Out of Range” when connected. What does this mean and how would you fix it by changing the resolution or refresh rate in Windows safe mode or using a different monitor temporarily to adjust settings?
    
76. **Scenario:** A user reports that their USB ports are not working at all. They have tried multiple devices. The laptop is on and the OS is responsive. What would you check: USB controllers in Device Manager, BIOS setting for USB, and whether the ports are physically damaged. How would you guide them to check for disabled controllers and reinstall them?
    
77. **Scenario:** A remote employee uses a USB headset and a separate USB webcam. Both stop working after a Windows update. What is the first thing you would do: check Device Manager for warning icons, roll back the update, or update chipset/USB drivers? How would you prioritize these actions?
    
78. **Scenario:** A user’s computer makes a continuous beeping sound when turned on, and nothing appears on screen. What does this indicate (hardware POST error) and how can you guide the user to count beeps and report the pattern? What information would you document for escalation?
    
79. **Scenario:** A user says their SSD is “full” but they don’t have many files. You suspect hidden system files or a large hibernation file. What commands or tools would you use to identify large files (TreeSize, WinDirStat, or Disk Cleanup) and how would you safely reduce space without deleting personal data?
    
80. **Scenario:** A user’s laptop gets extremely hot and the fan is very loud, but CPU usage is low. What could cause this (dust, failed fan, poor thermal paste) and what remote steps can you take? You may not be able to fix hardware, but you can advise on using a cooling pad and checking power settings.
    
81. **Scenario:** A user accidentally disabled their Wi‑Fi adapter in Device Manager and now cannot get online to remote into their PC. What instructions would you give them to re‑enable it using only keyboard navigation (since no network)? Walk through using Device Manager via Run command and enabling the device.

82. **Scenario:** A USB security key or smart card reader is detected by Windows but authentication still fails. How would you distinguish between hardware detection, driver issues, middleware, certificate problems, and account authentication problems?

83. **Scenario:** A peripheral works perfectly on another computer. What does that prove, what does it not prove, and how does that change your troubleshooting hypothesis?

### EXTRA

84. At what point should a Tier 1 Help Desk technician stop troubleshooting a suspected hardware problem and escalate it? What information should be documented before escalation?
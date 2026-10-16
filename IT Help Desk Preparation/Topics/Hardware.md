Priority key: **L1 = must master before applying**, **L2 = important but secondary**, **L3 = defer / adjacent module**.
### Section A — Hardware Fundamentals & Component Function

**1.** Explain the role of the CPU and describe common symptoms of a CPU-related problem (overheating, throttling, sudden shutdowns under load). Which symptoms point toward the CPU, and which are more consistent with RAM or storage? **(L1)**
*Expected criteria:* distinguishes throttling/thermal symptoms from RAM errors (BSOD, memory errors) and storage symptoms (clicking, corruption, extreme slowness); avoids concluding a specific component is dead from a single symptom.

**2.** Differentiate volatile memory (RAM) from non-volatile storage (SSD/HDD) in plain terms, and explain why a user’s confusion between "memory" and "disk space" changes your diagnostic path. **(L1)**
*Expected criteria:* RAM is temporary working memory; storage is persistent. User says "I ran out of memory" → clarify which one before acting.

**3.** Describe the motherboard’s role in relation to CPU, RAM, storage, expansion cards, and ports. If a single USB or Ethernet port stops working while others work, what does that suggest and how do you isolate it? **(L1)**
*Expected criteria:* checks cable, device, driver, and alternative port first; a single dead port points to the port itself rather than the whole board; does not jump to "motherboard replacement."

**4.** Compare integrated and dedicated GPUs. A desktop appears powered on but shows no image and has a dedicated GPU. Outline your checks before concluding the GPU is faulty. **(L1)**
*Expected criteria:* verify monitor input, cable, and whether the video cable is plugged into the dGPU or the motherboard; try the integrated output if available; reseat only with authorization.

**5.** Explain what a desktop PSU does, common signs of PSU failure, and why a Tier 1 technician must never open or internally test a PSU. **(L1)**
*Expected criteria:* random shutdowns, failure to power on, burning smell; PSUs hold lethal charge; document, replace under warranty, or escalate.

**6.** Describe laptop power subsystems: AC adapter, DC jack, battery, and internal charging circuit. List symptoms that could point to each. **(L1)**
*Expected criteria:* no LED with known-good charger → charger or jack; LED on but battery drains → battery or charging circuit; escalates internal repairs.

**7.** Explain the purpose of cooling systems (heatsinks, fans, thermal paste) and symptoms of overheating. What safe on-site actions can a Tier 1 technician take versus what must be escalated? **(L1)**
*Expected criteria:* cleaning vents with approved tools, ensuring airflow, verifying fan spin, updating manufacturer-approved power/thermal settings via sanctioned tools; opening a laptop to repaste is Tier 2/vendor.

**8.** Differentiate NIC, Wi-Fi adapter, and Bluetooth adapter. If Ethernet drops intermittently but Wi-Fi works, outline your checks without assuming the NIC is faulty. **(L2 — networking overlap)**
*Expected criteria:* cable, port on wall, switch port, driver status; recognizes that intermittent drop can be infrastructure-side.

**9.** Distinguish internal components, peripherals, and accessories with examples. Why does this distinction matter for ticket routing and warranty? **(L1)**
*Expected criteria:* internal = CPU, RAM, SSD; peripheral = monitor, keyboard, printer; accessory = dock, cable, adapter. Warranty and authorization depend on the category.

**10.** Describe practical differences between desktops, laptops, and workstations (upgradability, power, portability, typical use). **(L1)**
*Expected criteria:* desktops are more upgradable; laptops limited by form factor; workstations prioritize reliability and sustained performance.

### Section B — Compatibility, Installation & Replacement

**11.** How do you verify RAM compatibility before upgrading? Cover DDR generation, form factor (DIMM vs SODIMM), capacity, speed, and how to look up the model’s specifications. **(L1)**
*Expected criteria:* DDR3/4/5, DIMM vs SODIMM, max supported capacity per slot and total, speed compatibility (may downclock); verifies via manufacturer’s manual/model lookup.

**12.** How do you determine whether a machine supports a SATA SSD, an NVMe SSD, or both? What physical and firmware-level checks apply? **(L1)**
*Expected criteria:* physical slot type (M.2 SATA vs M.2 NVMe keying), M.2 slot spec (PCIe lanes), BIOS/UEFI recognition, official model documentation.

**13.** What information must you confirm before using a replacement laptop charger? Cover voltage, wattage, connector, USB-PD, and manufacturer requirements. **(L1)**
*Expected criteria:* matching voltage and polarity, sufficient wattage, correct connector; USB-PD with sufficient wattage only if the laptop supports it; check manufacturer recommendation.

**14.** Why can two USB-C ports or cables look identical but support different features (charging, data, video, Thunderbolt/USB4)? How do you verify what a specific port supports? **(L1)**
*Expected criteria:* USB-C is a connector, not a capability; check port spec sheet, motherboard/laptop manual, cable certification; DP Alt Mode vs plain data.

**15.** How would you check whether a laptop or desktop supports a proposed upgrade (extra RAM, additional drive, second monitor) before recommending it? **(L1)**
*Expected criteria:* identify exact model number (label, System Information, vendor tool), consult manual/spec sheet, verify slot availability, power/thermal headroom, and warranty.

**16.** How do you verify monitor and adapter compatibility (resolution, refresh rate, port type, active vs passive adapter)? **(L1)**
*Expected criteria:* max resolution and refresh supported; HDMI/DP version; active adapters required for certain conversions (DP→HDMI passive often works one way only).

**17.** When should a Tier 1 technician replace a component, attempt a repair, or escalate? Give at least two examples of each. **(L1)**
*Expected criteria:* replace = RAM, storage, keyboard module if authorized; repair = reseat, clean, reseat cable; escalate = PSU, motherboard, soldering, battery replacement inside a sealed unit.

### Section C — Diagnostic Methodology & Fault Isolation

**18.** Describe a structured diagnostic method (identify, hypothesize, test one variable, verify, document). Apply it to a PC that "won’t turn on." **(L1)**
*Expected criteria:* clarify symptoms, check power source and LED/fan behavior, isolate one variable at a time, document each test, verify before closing.

**19.** A PC powers on (fans spin, LEDs on) but shows no image. List your checks in order and explain what each rules out. **(L1)**
*Expected criteria:* monitor input, cable, alternate monitor, GPU output vs motherboard output, reseat only with authorization; each step rules out a variable.

**20.** A PC fails before Windows loads (POST error, beep codes, error message). What information do you record, and what does it tell you? **(L1)**
*Expected criteria:* exact beep pattern, POST code, error text; vendor documentation to decode; distinguishes POST failure from OS boot failure.

**21.** A laptop only runs on AC power and shuts down the moment it is unplugged. What are the possible causes, and how do you narrow them down? **(L1)**
*Expected criteria:* battery health, battery seating, power settings, charging circuit; uses manufacturer battery report; escalates internal repair if battery is not user-replaceable.

**22.** A device (USB drive, webcam, printer) is not detected. Describe your isolation approach: port, cable, driver, device on another machine. **(L1)**
*Expected criteria:* change one variable at a time; if the device works on another machine, the problem is the original machine’s port/driver/config.

**23.** A workstation restarts randomly. What evidence would you collect before concluding it is hardware? **(L2 — Windows overlap)**
*Expected criteria:* Event Viewer for unexpected shutdown, thermal readings, recent updates or driver changes, power events; does not label PSU/GPU as the cause without evidence.

**24.** A user reports slow performance, overheating, fan noise, or freezing. How do you distinguish a hardware cause from an OS, malware, or configuration cause? **(L1)**
*Expected criteria:* Resource Monitor/Task Manager first, temperature readings, physical inspection for dust; avoids assuming disk or CPU is failing.

**25.** A storage drive shows symptoms of failure (clicking, SMART warnings, file corruption, extremely slow access). What should you do first, and what must you never do? **(L1)**
*Expected criteria:* back up or make data accessible first; do not run chkdsk or defrag on a suspected failing drive; do not power-cycle repeatedly; escalate for data recovery if needed.

**26.** A peripheral (monitor, keyboard, mouse, webcam, headset, printer) stops working. Outline the general isolation steps that apply to any peripheral. **(L1)**
*Expected criteria:* power, cable, port, driver, alternative device, alternative machine; substitute a known-good component to isolate.

**27.** A user reports a single failed connection or a single error but everything else works. Why is a single reproducible symptom sometimes more useful than many vague ones, and how do you test reproducibility? **(L2)**
*Expected criteria:* reproducibility narrows the cause; repeated attempts and observation of context (time, action, application) provide usable evidence.

### Section D — Physical Safety, Assembly & Maintenance

**28.** What is ESD and how do you prevent it when handling components? Which components are most at risk? **(L1)**
*Expected criteria:* anti-static wrist strap, grounded surface, avoid carpets, hold components by edges; RAM, motherboard, GPU, NIC are most at risk.

**29.** What should you prepare before opening a desktop or laptop (workspace, tools, power off, unplug, battery, documentation, user data)? **(L1)**
*Expected criteria:* clean workspace, correct tools, power disconnected, laptop battery removed/disconnected if serviceable, documentation on hand, user data protected.

**30.** How do you safely remove and reseat RAM, storage, or an expansion card without damaging connectors, slots, or the board? **(L1)**
*Expected criteria:* release retention clips, never force, align keyed notch, no contact with gold contacts, no static discharge.

**31.** How do you safely clean a computer’s interior and vents? What should you never do? **(L1)**
*Expected criteria:* approved compressed air, short bursts, hold fans to prevent over-spinning, lint-free cloths; never liquid inside, never touch pins, never over-spin fans.

**32.** A user shows you a swollen or leaking battery. What are the immediate safety actions, and why must you not puncture, bend, or continue using it? **(L1)**
*Expected criteria:* stop use, do not charge, isolate from flammable materials, follow local battery disposal policy; puncturing risks fire/chemical exposure.

**33.** Why should a Tier 1 technician not open or repair a PSU? **(L1)**
*Expected criteria:* dangerous stored voltage even when unplugged; replacement or warranty route only.

**34.** After any physical intervention, what verification steps do you perform before returning the equipment to the user? **(L1)**
*Expected criteria:* boot test, POST pass, OS boots, all components recognized (Device Manager, System Information), peripherals functional, user data intact, ticket updated.

**35.** How do warranty and company policy affect what a Tier 1 technician may do with hardware? **(L1)**
*Expected criteria:* opening sealed units, using non-OEM parts, or repairing under warranty may void coverage; follow company procedure and escalate when in doubt.

### Section E — Boot, Firmware & Basic Diagnostics

**36.** What is POST, and how does it differ from the OS boot process? How do you use POST beep codes or LED indicators? **(L1)**
*Expected criteria:* POST = firmware self-test before OS load; beep/LED patterns decode through vendor documentation; failure at POST is hardware/firmware, failure after is OS.

**37.** What is BIOS/UEFI, and which settings might a Tier 1 technician reasonably check? Which settings must never be changed without authorization? **(L1)**
*Expected criteria:* may check boot order, time/date, secure boot status, virtualization status; must not change voltages, CPU settings, secure boot, TPM, or RAID without approval; never flash BIOS without authorized procedure.

**38.** Under what conditions would updating firmware/BIOS be justified, and why must a Tier 1 technician not perform it without an approved procedure? **(L1)**
*Expected criteria:* manufacturer security advisory, compatibility fix, vendor instruction; power loss during flashing can brick the device; requires approved procedure and stable power.

**39.** Which built-in Windows tools are appropriate for Tier 1 hardware diagnosis (Device Manager, Task Manager, System Information, Event Viewer, Disk Management, vendor diagnostics)? Describe what each reveals. **(L1)**
*Expected criteria:* Device Manager = device/driver status; Task Manager = resource use; System Information = model/specs; Event Viewer = error timeline; Disk Management = volumes/letters; vendor diagnostics = component tests.

**40.** How would you use vendor hardware diagnostics, and when is that preferable to Windows-based troubleshooting? **(L2)**
*Expected criteria:* hardware self-tests (Dell ePSA, HP UEFI diagnostics, Lenovo diagnostics) give component-level results independent of Windows; preferable when OS cannot boot or when hardware is suspected.

**41.** What can Event Viewer tell you about unexpected shutdowns or hardware errors, and what are the limits? **(L2)**
*Expected criteria:* Kernel-Power 41 = unexpected shutdown, not root cause; disk error events point to storage but require vendor diagnostic confirmation.

### Section F — Monitors, Peripherals & Docking Stations

**42.** A monitor shows "No Signal." Outline your step-by-step checks. **(L1)**
*Expected criteria:* input source selection, cable type and condition, source device output (Win+P), alternate monitor/port, verify monitor powers on with its own menu.

**43.** A monitor is detected but shows a black screen. What Windows display settings and driver checks apply? **(L1)**
*Expected criteria:* Win+P (extend/duplicate), resolution and refresh, brightness, GPU driver status, test with another display.

**44.** A laptop with a USB-C dock does not output video to an external monitor. What do you verify? **(L1)**
*Expected criteria:* dock power, cable type, laptop port capability (DP Alt Mode / Thunderbolt), dock driver/firmware, alternate port on dock, known-good monitor.

**45.** A Bluetooth mouse or keyboard disconnects or lags. What do you check? **(L2)**
*Expected criteria:* battery, pairing, interference (2.4 GHz, USB 3.0), receiver placement (for wireless dongles), driver status, known-good device test.

**46.** A USB keyboard types wrong characters. How do you distinguish hardware from layout/sticky keys/language? **(L1)**
*Expected criteria:* test on another machine, check region/layout, disable Sticky/Filter Keys, try another keyboard.

**47.** How do you safely remove USB storage, and why does it matter? What can you attempt if a user removed it improperly, without promising recovery? **(L1)**
*Expected criteria:* use Safely Remove/Eject; check Recycle Bin, Previous Versions, File History, professional recovery options; do not run chkdsk as a data-recovery tool.

### Section G — Printers & Shared Devices

**48.** Differentiate locally attached, network, and print-server-deployed printers. How does troubleshooting differ? **(L1)**
*Expected criteria:* USB = local port/driver; network = IP reachability and print protocol; print server = server-side queue and permissions.

**49.** What is the Print Spooler, and what symptoms suggest it is stuck? How do you safely restart it? **(L1)**
*Expected criteria:* services.msc restart, clear stuck jobs, verify driver; safe on a workstation, be cautious on a print server (escalate if shared).

**50.** A printer responds to ping but Windows reports it offline. What does this tell you and what do you investigate next? **(L1)**
*Expected criteria:* network path OK; check the queue, printer port configuration, spooler, printer power state, correct printer object (stale IP).

**51.** A test page prints fine but one application cannot print. What does that suggest, and how do you narrow the cause? **(L1)**
*Expected criteria:* application-side issue; test from Notepad, check app print settings, permissions, print-to-PDF, reinstall app printer reference.

**52.** A print job is stuck in the queue. What steps do you take before deleting and reinstalling the printer? **(L1)**
*Expected criteria:* cancel job, restart spooler, verify printer online, clear queue, test page; only reinstall if the problem persists.

### Section H — Professional Workflow, Documentation & Escalation

**53.** What information should every hardware ticket include? **(L1)**
*Expected criteria:* user, asset tag/serial, location, exact symptoms, error text, recent changes, impact, tests performed, outcome.

**54.** Why is "minimal intervention" important, and how does it apply to hardware troubleshooting? **(L1)**
*Expected criteria:* change one thing at a time, avoid unnecessary replacements, protect user data and configuration, preserve ability to diagnose.

**55.** How do you decide whether to resolve or escalate a hardware issue? **(L1)**
*Expected criteria:* scope, authorization, risk, warranty, and required specialty; document findings before escalation.

**56.** What information must be documented before escalating a suspected hardware failure? **(L1)**
*Expected criteria:* symptoms, tests performed, evidence, asset details, prior tickets, user impact, and any temporary workaround in place.

**57.** How do you protect a user’s data during hardware diagnosis or component replacement? **(L1)**
*Expected criteria:* back up when possible, avoid destructive commands, do not reimage/format without authorization, confirm data availability before proceeding.

**58.** How do you confirm with the user that the issue is resolved, and what do you do if it recurs? **(L1)**
*Expected criteria:* have the user verify the original task, confirm peripheral functions, document outcome, reopen or escalate if recurrence.

---

## PART 3 — MISSING TOPICS ADDED & TOPICS MOVED

**Competencies added (not sufficiently covered in the original):**
- ESD and physical handling safety (Q28–31).
- Pre-work preparation and post-intervention verification (Q29, Q34).
- Warranty and authorization boundaries (Q35, Q38).
- Component compatibility methodology (Q11–17), especially RAM, storage, charger, and USB-C capability.
- Structured diagnostic reasoning for on-site work (Q18–27).
- Professional workflow: ticketing, minimal intervention, data protection, escalation documentation (Q53–58).
- Explicit separation between "suspect" and "confirm" for hardware failures.

**Topics reduced or moved to other modules:**
- **Networking module:** NIC driver/switch-port logic, intermittent Ethernet, packet-level diagnosis, IP/VLAN/firewall troubleshooting (part of Q8; original Q9).
- **Windows support module:** deep Event Viewer analysis, svchost, services, msconfig, power plans, driver architecture, BitLocker recovery workflow (original Q18, Q21, Q27, Q28, Q54).
- **Enterprise applications module:** Teams, Zoom, browser camera permissions, headset sidetone software (original Q45, Q52, Q63).
- **Advanced printing module:** WSD, TWAIN, IPP, scan-to-folder, print server administration (original Q38, Q44).
- **Security/identity module:** smart card/USB security key middleware and certificate issues, MFA, malware diagnosis (original Q82 and the security-side of several scenarios).
- **Tier 2 / vendor module:** internal laptop repairs, thermal repaste, PSU repair, motherboard-level diagnosis (original Q65, Q68, parts of Q11 and Q80).

---

## PART 4 — INTEGRATIVE PRACTICAL SCENARIOS

### Scenario 1 — Desktop will not power on
- **Situation:** A user reports their desktop does not turn on. No lights, no fans.
- **Information to obtain:** When did it last work, recent power events, location (surge strip, outlet), any recent hardware changes.
- **Evidence to look for:** Wall outlet, power strip, PSU switch, power cable, front-panel LED, fan spin.
- **Appropriate initial actions:** Verify power source with a known-good outlet/device; check cable seating; confirm PSU rear switch.
- **Errors to avoid:** Opening the PSU; assuming motherboard failure; swapping parts randomly.
- **Resolve or escalate criteria:** If a known-good cable/outlet restores power → resolve. If not → escalate for PSU/board diagnosis.

### Scenario 2 — Laptop will not charge
- **Situation:** A user’s laptop works on battery but does not charge.
- **Information to obtain:** Charger type, LED status, whether it charges in another room or with another charger, battery health history.
- **Evidence to look for:** Charger LED, DC jack condition, battery report, Windows charging indicator.
- **Appropriate initial actions:** Test with a known-good charger of the same spec; check jack for debris or damage; generate battery report.
- **Errors to avoid:** Using an incompatible charger; opening the laptop to reseat internal battery on a warranty unit.
- **Resolve or escalate criteria:** Bad charger → replace. Otherwise escalate for internal diagnosis.

### Scenario 3 — External monitor not detected through dock
- **Situation:** A user’s laptop with a USB-C dock shows no image on the external monitor.
- **Information to obtain:** Dock model, cable type, monitor model, whether it ever worked, recent updates.
- **Evidence to look for:** Dock power LED, monitor input, Win+P state, laptop USB-C port spec.
- **Appropriate initial actions:** Verify dock power, reseat cables, test with HDMI/DP direct, verify laptop port supports DP Alt Mode.
- **Errors to avoid:** Assuming the dock is faulty; installing random firmware without approval.
- **Resolve or escalate criteria:** Cable or setting issue → resolve. Firmware/dock hardware issue → escalate with documented tests.

### Scenario 4 — Printer reported offline
- **Situation:** Multiple users report a network printer as offline.
- **Information to obtain:** Printer IP, whether it responds to ping, printer display status, recent network changes.
- **Evidence to look for:** Ping result, printer panel, print queue, spooler status, IP consistency.
- **Appropriate initial actions:** Ping printer; check printer panel for errors; verify correct printer object and port; restart spooler locally.
- **Errors to avoid:** Reinstalling the printer before checking basic reachability; changing printer IP without coordination.
- **Resolve or escalate criteria:** Single-user queue issue → resolve. Printer-side or network-side → escalate.

### Scenario 5 — Slow PC with 100% disk usage
- **Situation:** A user reports the PC is slow and Task Manager shows 100% disk usage.
- **Information to obtain:** How long, what changed recently, which process is at the top, drive type.
- **Evidence to look for:** Process name, drive model (SSD vs HDD), Event Viewer disk errors, SMART status.
- **Appropriate initial actions:** Identify the process; check storage type; verify free space; collect evidence before disabling anything.
- **Errors to avoid:** Disabling services blindly; declaring the drive faulty.
- **Resolve or escalate criteria:** Identified non-critical process or free space → resolve. SMART warnings or disk errors → escalate for hardware.

### Scenario 6 — Random reboots
- **Situation:** A desktop restarts randomly during the workday.
- **Information to obtain:** Frequency, load at time of reboot, recent changes, room temperature.
- **Evidence to look for:** Event Viewer (Kernel-Power 41, thermal events), dust buildup, fan behavior.
- **Appropriate initial actions:** Clean vents (with authorization), verify airflow, document timestamps and processes running.
- **Errors to avoid:** Replacing the PSU or GPU without evidence; ignoring event logs.
- **Resolve or escalate criteria:** Thermal/dust issue → resolve with cleaning. Persistent after cleaning → escalate.

### Scenario 7 — USB peripheral not detected
- **Situation:** A user’s USB headset is not detected on their workstation but works on a colleague’s PC.
- **Information to obtain:** Port used, cable, driver state, other USB devices working.
- **Evidence to look for:** Device Manager entries, USB controller status, alternative port test.
- **Appropriate initial actions:** Try another port, another cable, another machine; check Device Manager.
- **Errors to avoid:** Assuming the device is defective; installing random drivers.
- **Resolve or escalate criteria:** Port issue → resolve. Recurring controller errors → escalate.

### Scenario 8 — Swollen laptop battery
- **Situation:** A user shows a laptop with a bulging chassis and reports the trackpad is hard to click.
- **Information to obtain:** When noticed, whether the laptop is still in use, warranty status.
- **Evidence to look for:** Physical bulge, heat, odor.
- **Appropriate initial actions:** Advise stopping use immediately; do not charge; isolate from flammables; follow disposal/replacement policy.
- **Errors to avoid:** Pressing on the battery; continuing to use the laptop; attempting DIY replacement on a warranty unit.
- **Resolve or escalate criteria:** Always escalate for safe battery replacement; ensure the user is safe first.

### Scenario 9 — Clicking hard drive with slow file access
- **Situation:** A desktop HDD makes a repetitive clicking noise and file access is extremely slow.
- **Information to obtain:** Frequency, presence of critical data, recent backups.
- **Evidence to look for:** SMART data, Event Viewer disk errors, listen to drive behavior.
- **Appropriate initial actions:** Stop non-essential use; advise user not to save new data; escalate immediately for backup/recovery.
- **Errors to avoid:** Running chkdsk or defrag; assuming software slowness.
- **Resolve or escalate criteria:** Always escalate when mechanical failure is suspected; prioritize data protection.

### Scenario 10 — Peripheral works elsewhere
- **Situation:** A user’s webcam works on a personal laptop but not on the corporate desktop.
- **Information to obtain:** Ports tried, driver state, privacy settings, application used.
- **Evidence to look for:** Device Manager, camera permissions, test in Windows Camera app.
- **Appropriate initial actions:** Test on another USB port; test in the built-in Camera app; check permissions.
- **Errors to avoid:** Reinstalling the OS; assuming the webcam is broken.
- **Resolve or escalate criteria:** Driver or permission issue → resolve. Persistent controller issue → escalate.

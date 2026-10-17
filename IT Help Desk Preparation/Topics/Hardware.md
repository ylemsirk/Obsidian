Priority key: **L1 = must master before applying**, **L2 = important but secondary**, **L3 = defer / adjacent module**.
### Section A — Hardware Fundamentals & Component Function

<mark style="background:#affad1">**1.** Explain the role of the CPU and describe common symptoms of a CPU-related problem (overheating, throttling, sudden shutdowns under load). Which symptoms point toward the CPU, and which are more consistent with RAM or storage? **(L1)**</mark>
<mark style="background:#affad1">*Expected criteria:* distinguishes throttling/thermal symptoms from RAM errors (BSOD, memory errors) and storage symptoms (clicking, corruption, extreme slowness); avoids concluding a specific component is dead from a single symptom.</mark>

**2.** Differentiate volatile memory (RAM) from non-volatile storage (SSD/HDD) in plain terms, and explain why a user’s confusion between "memory" and "disk space" changes your diagnostic path. **(L1)**
*Expected criteria:* RAM is temporary working memory; storage is persistent. Users say "I ran out of memory" ambiguously; clarify before acting. SSD = no moving parts, faster boot/app load, more shock-resistant; caveats = data migration, capacity per cost, backup before cloning, warranty/company policy on opening the unit.

**3.** Describe the motherboard’s role in relation to CPU, RAM, storage, expansion cards, and ports. If a single USB or Ethernet port stops working while others work, what does that suggest and how do you isolate it? **(L1)**
*Expected criteria:* checks cable, device, driver, and alternative port first; a single dead port points to the port itself rather than the whole board; does not jump to "motherboard replacement."

**4.** Compare integrated and dedicated GPUs. A desktop appears powered on but shows no image and has a dedicated GPU. Outline your checks before concluding the GPU is faulty. **(L1)**
*Expected criteria:* verify monitor input, cable, and whether the video cable is plugged into the dGPU or the motherboard; try the integrated output if available; reseat only with authorization.

**5.** Explain what a desktop PSU does, its common failure symptoms, and the difference between replacing a complete PSU and opening/repairing a PSU. Which action, if any, may a Tier 1 technician take, and what does that depend on? (L1)
Expected criteria: PSU converts AC to DC and supplies regulated rails; symptoms = no power, random shutdowns, burning smell, tripped breaker. Opening or repairing the PSU is never authorized — internal capacitors hold lethal charge even unplugged. Replacing the entire unit with an identical or approved equivalent may be within Tier 1 scope only if training, written authorization, company policy, and warranty conditions permit. Otherwise swap the machine, use a spare, or escalate. Always unplug from the wall before any physical intervention.

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
*Expected criteria:* A device (USB flash drive, external HDD, webcam, printer, or a specific USB port) is not detected. Describe your isolation approach: port, cable, driver, device on another machine, and known-good substitution. **(L1)**  
_Expected criteria:_ change one variable at a time. Test the device on another machine and test another device on the original port. If the device works elsewhere, the fault is the original machine's port, driver, or configuration. If the port works with another device, the fault is the original device. **Do not initialize, format, or repartition an external drive that holds user data — first check Disk Management, drive letter conflicts, and cable/port, and escalate before any destructive action.** A device that works elsewhere does not prove the machine is fine; it only narrows the fault.

**23.** A workstation restarts randomly. What evidence would you collect before concluding it is hardware? **(L2 — Windows overlap)**
*Expected criteria:* Event Viewer for unexpected shutdown, thermal readings, recent updates or driver changes, power events; does not label PSU/GPU as the cause without evidence.

**24.** A user reports slow performance, slow boot, high disk usage, or freezing. How do you distinguish a hardware cause from an OS, malware, or configuration cause? (L1)
Expected criteria: Resource Monitor and Task Manager first, temperature readings, physical inspection for dust. "Disk usage 100%" in Task Manager does not prove the drive is faulty — common causes include Windows Search, SysMain, Windows Update, antivirus scans, and pending updates. Slow boot is usually startup programs, pending updates, HDD vs SSD, or malware — not the CPU or PSU. Identify what is using the resource before disabling anything. Escalate for hardware only when there is corroborating evidence (SMART warnings, disk errors in Event Viewer, physical noise, overheating under idle load).

**25.** A storage drive shows symptoms of failure (clicking, SMART warnings, file corruption, extremely slow access). What is the correct order of actions? (L1)
Expected criteria: Preserve user data first — copy what is still readable to a known-good location or hand to data recovery, with the user's awareness and the company's procedure. Do not run chkdsk, defrag, or any intensive diagnostic on a drive suspected of mechanical failure — this can accelerate data loss. Do not repeatedly power-cycle. Document SMART values if a read-only tool is available. Escalate to Tier 2, the backup team, or a data-recovery service. Tier 1 does not attempt to "fix" a failing drive.

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

**32.** A user shows a laptop with a bulging chassis and a trackpad that is hard to click. What are the immediate safety actions, what must you never do, and what is the escalation path? (L1)
Expected criteria: Stop using and stop charging the laptop immediately. Do not press, bend, puncture, or attempt to remove the battery. Keep it away from flammable materials and heat. Follow the company's battery-hazard policy for isolation, transport, and disposal. Do not continue troubleshooting the laptop on-site. Escalate to the authorized repair path or vendor — battery replacement in a swollen-unit scenario is not a Tier 1 task, regardless of training.

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

**39.** Which built-in Windows tools are appropriate for Tier 1 hardware diagnosis (Device Manager, Task Manager, System Information, Event Viewer, Disk Management, vendor diagnostics)? Describe what each reveals. (L1)
Expected criteria: Device Manager = device and driver status; Task Manager = live resource use; System Information = model/specs; Event Viewer = error timeline; Disk Management = volumes/letters; vendor diagnostics = component-level hardware tests. When a device is misbehaving, decide between updating, rolling back, uninstalling, or reinstalling a driver based on evidence: roll back after a recent update, uninstall/reinstall after corruption, update only when a compatible newer driver is documented. Do not change drivers "just in case."

**40.** How would you use vendor hardware diagnostics, and when is that preferable to Windows-based troubleshooting? **(L2)**
*Expected criteria:* hardware self-tests (Dell ePSA, HP UEFI diagnostics, Lenovo diagnostics) give component-level results independent of Windows; preferable when OS cannot boot or when hardware is suspected.

**41.** Which built-in Windows tools are appropriate for Tier 1 hardware diagnosis (Device Manager, Task Manager, System Information, Event Viewer, Disk Management, vendor diagnostics)? Describe what each reveals. (L1)
Expected criteria: Device Manager = device and driver status; Task Manager = live resource use; System Information = model/specs; Event Viewer = error timeline; Disk Management = volumes/letters; vendor diagnostics = component-level hardware tests. When a device is misbehaving, decide between updating, rolling back, uninstalling, or reinstalling a driver based on evidence: roll back after a recent update, uninstall/reinstall after corruption, update only when a compatible newer driver is documented. Do not change drivers "just in case."

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

**50.** A printer responds to ping but Windows reports it offline. What does the ping actually tell you, and what do you investigate next? (L1)
Expected criteria: A successful ping only confirms an ICMP response from the device's IP stack — it does not prove that printing services, the print queue, the printer port, or the driver are working. Investigate whether the printer is a shared/print-server device or a direct IP printer; check the print spooler, the printer port configuration, the printer's own panel/status, and the queue. Also determine scope: a single user unable to print is usually a driver, queue, or profile issue; multiple users unable to print points to the printer, the print server, or the network path. After any change, have the user print a test page and confirm the original document can print.

**51.** A test page prints fine but one application cannot print (or the output is garbled). What does that suggest, and how do you narrow the cause? (L1)
Expected criteria: A successful test page proves the printer, port, and driver work for the OS test path. Failures in a single application point to that application's print settings, its driver selection, permissions, or file format. Garbled output from all applications points to a wrong or corrupt driver. Narrow by testing Notepad, Print-to-PDF, and the specific application; only reinstall the driver when evidence supports it.

**52.** A print job is stuck in the queue. What steps do you take before deleting and reinstalling the printer? (L1)
Expected criteria: cancel the job, restart the Print Spooler service locally, verify the printer is online and has no panel error, clear the queue, print a test page. On a shared print server, do not restart the spooler without coordinating with the print admin. Reinstall the printer only if the problem persists after these steps.

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

<p align="left">59. How do you distinguish a system suffering from insufficient RAM from one with CPU overload? What built-in tools do you use, what indicators do you look at, and how do the remediation steps differ? (L1)
Expected criteria: Task Manager / Resource Monitor → Memory vs CPU tab; RAM pressure = high memory %, heavy paging, disk thrash, low free memory; CPU overload = sustained high CPU on one or more processes with memory still available. Fixes differ: RAM pressure → reduce startup items, identify memory-hungry applications, escalate for hardware upgrade if the machine is under-spec; CPU overload → identify the process, check for malware or runaway tasks, and do not add RAM to fix a CPU problem.</p>

<p align="left">60. A laptop suddenly cannot see any Wi-Fi networks. What hardware and software checks do you perform before considering a driver reinstall or a hardware fault? (L1)
Expected criteria: check airplane mode, physical wireless switch, Fn key toggle, Device Manager for a disabled or missing adapter, adapter status in Network Connections, driver status and recent updates, then try a USB Wi-Fi adapter to isolate hardware from configuration. Reinstall or roll back the driver only after the above is exhausted; escalate if the adapter is not detected by the OS at all.</p>

<p align="left">61. A user reports a blue screen with the stop code MEMORY_MANAGEMENT. How do you triage this as a Tier 1 technician? What evidence do you collect, what tools do you use, and what conclusions can and cannot be drawn from a single stop code? (L2)
Expected criteria: collect the exact stop code, the minidump existence, time of the crash, recent changes (driver, update, hardware). Check Event Viewer and Reliability Monitor. A stop code names a symptom, not the cause — MEMORY_MANAGEMENT can result from faulty RAM, a bad driver, or software corruption. Do not replace RAM based on the stop code alone. Use Windows Memory Diagnostic or the vendor's hardware diagnostic if warranted, and escalate for deeper triage.</p>

<p align="left">62. A user complains their laptop battery drains quickly. How do you generate a battery report, what key values do you examine, and when does this become an escalation? (L1)
Expected criteria: powercfg /batteryreport produces an HTML report with design capacity, full-charge capacity, cycle count, and recent usage. Compare design vs current full-charge capacity to estimate wear. If wear is significant or the machine shuts down unexpectedly on battery, escalate for battery replacement — Tier 1 does not replace internal batteries on sealed units unless company policy permits.</p>

<p align="left">63. A user is prompted for a BitLocker recovery key after a motherboard or BIOS update. How do you handle this, what security rules apply to the recovery key, and what should never be stored or transmitted insecurely? (L2)
Expected criteria: explain why the prompt appeared (hardware or firmware change breaks the TPM-bound key protector); guide the user to retrieve the key from the authorized escrow (company AD/Entra ID, Microsoft account, or printed copy per policy). Never store the recovery key in email, chat, tickets, or unmanaged files. Never read the key aloud on a recorded line. Verify the user's identity through the authorized process before releasing any recovery information. After recovery, recommend re-enabling protection and re-escrowing. If no key is available, escalate — do not bypass or disable BitLocker without authorization.</p>

<p align="left">64. A laptop's built-in keyboard stops responding, but an external USB keyboard works. How do you isolate whether the problem is hardware, driver, or configuration? (L1)
Expected criteria: check Device Manager for a disabled or errored keyboard device, try on-screen keyboard to confirm the OS is responsive, check for a recent driver update, test in BIOS/UEFI — if the internal keyboard also fails in BIOS, the fault is hardware and must be escalated; if it works in BIOS but not in Windows, the fault is driver or configuration. A working external keyboard does not mean the internal keyboard is fine; it just confirms the OS can accept input from another source.</p>

<p align="left">65. A laptop's brightness slider is grayed out, or an external monitor shows "Out of Range." How do you diagnose and correct each case? (L1)
Expected criteria: brightness grayed out → check display driver status, monitor driver (generic PnP vs vendor), power settings, and whether a group policy restricts brightness. "Out of Range" on an external monitor → the resolution or refresh rate exceeds what the monitor supports; boot into a low-resolution mode or Safe Mode, lower the resolution/refresh, then reconnect. Do not assume the monitor is faulty.</p>

<p align="left">66. A user reports no audio from their speakers or USB headset. How do you isolate whether the problem is the output device, the driver, the application, or Windows configuration? (L1)
Expected criteria: check default playback device, volume mixer per application, mute state, whether a different output (headphones, another headset) works, whether audio works in another application, and whether Windows Audio and related services are running. Test with a known-good headset to isolate hardware. Reinstall the audio driver only when evidence supports a driver fault.</p>

---
## INTEGRATIVE PRACTICAL SCENARIOS

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
 - **Situation:** Multiple users report the same network printer as offline.
    
- **Information to obtain:** whether one user or several are affected, printer IP and panel status, whether anything changed on the network or print server.
    
- **Evidence to look for:** a successful ping confirms only that the printer's IP stack responds; it does **not** confirm that the print service, queue, port, or driver are functional. Check the printer's own panel, the print-server queue, and the driver status.
    
- **Appropriate initial actions:** determine scope (single user vs multiple users). If multiple users are affected, suspect the printer, print server, or network path. If a single user is affected, suspect that user's driver, queue, or profile.
    
- **Errors to avoid:** concluding the printer is fine because it answers ping; reinstalling drivers before checking scope; restarting the print server spooler without coordination.
    
- **Resolve or escalate criteria:** single-user driver/queue issue → resolve after the user prints the original document successfully. Multiple-user or printer/server-side → escalate with documented tests.

### Scenario 5 — Slow PC with 100% disk usage (corrected)

- **Situation:** A user reports slow performance; Task Manager shows 100% disk usage.
    
- **Information to obtain:** how long it has been happening, what changed recently, which process is at the top, drive type.
    
- **Evidence to look for:** top process, drive model (SSD vs HDD), Event Viewer disk errors, SMART values if a read-only tool is available.
    
- **Appropriate initial actions:** identify the process; verify free space; collect evidence before disabling anything.
    
- **Errors to avoid:** disabling services blindly; **declaring the drive faulty from "100%" alone**; running chkdsk on a suspect disk.
    
- **Resolve or escalate criteria:** identified a non-critical process or freed space → verify performance actually improves with the user before closing. SMART warnings or disk errors in Event Viewer → escalate for hardware.

### Scenario 6 — Random reboots (corrected)

- **Situation:** A desktop restarts randomly during the workday.
    
- **Information to obtain:** frequency, load at the time of reboot, recent changes, room temperature.
    
- **Evidence to look for:** Event Viewer (Kernel-Power 41, thermal events), dust buildup, fan behavior. Kernel-Power 41 records the unexpected shutdown but not its cause.
    
- **Appropriate initial actions:** clean vents if authorized, verify airflow, document timestamps and processes running.
    
- **Errors to avoid:** replacing PSU or GPU without evidence.
    
- **Resolve or escalate criteria:** after cleaning and airflow correction, **verify with the user that the reboots stop over a documented period** before closing. Persistent reboots → escalate.

### Scenario 7 — USB peripheral not detected
- **Situation:** A user’s USB headset is not detected on their workstation but works on a colleague’s PC.
- **Information to obtain:** Port used, cable, driver state, other USB devices working.
- **Evidence to look for:** Device Manager entries, USB controller status, alternative port test.
- **Appropriate initial actions:** Try another port, another cable, another machine; check Device Manager.
- **Errors to avoid:** Assuming the device is defective; installing random drivers.
- **Resolve or escalate criteria:** Port issue → resolve. Recurring controller errors → escalate.

### Scenario 8 — Swollen laptop battery (corrected)

- **Situation:** A user shows a laptop with a bulging chassis and a hard-to-click trackpad.
    
- **Information to obtain:** when it was noticed, warranty status, whether the laptop is still in use.
    
- **Evidence to look for:** physical bulge, heat, odor.
    
- **Appropriate initial actions:** **stop use and stop charging immediately**; isolate from flammables and heat; follow the company's battery-hazard disposal procedure.
    
- **Errors to avoid:** pressing, bending, puncturing, or attempting to remove the battery; continuing to troubleshoot on-site.
    
- **Resolve or escalate criteria:** always escalate to the authorized battery-replacement path. Tier 1 does not replace swollen batteries.

### Scenario 9 — Clicking hard drive with slow file access (corrected)

- **Situation:** A desktop HDD makes a repetitive clicking noise and file access is extremely slow.
    
- **Information to obtain:** presence of critical data, recent backup status.
    
- **Evidence to look for:** SMART data (read-only), Event Viewer disk errors, physical drive noise.
    
- **Appropriate initial actions:** **prioritize data preservation** — copy readable data to a known-good location or route to data recovery with the user's awareness and company procedure. Do not run chkdsk, defrag, or intensive diagnostics.
    
- **Errors to avoid:** running chkdsk "to fix" the drive; repeated power-cycling; declaring the disk dead before data is preserved.
    
- **Resolve or escalate criteria:** always escalate when mechanical failure is suspected; the priority is data, not drive repair.

### Scenario 10 — Peripheral works elsewhere (corrected)

- **Situation:** A user's webcam works on a personal laptop but not on the corporate desktop.
    
- **Information to obtain:** which ports were tried, driver state, privacy settings, and application used.
    
- **Evidence to look for:** Device Manager, camera permissions, test in the Windows Camera app.
    
- **Appropriate initial actions:** test on another USB port; test in the built-in Camera app; check permissions.
    
- **Errors to avoid:** reinstalling the OS; assuming the webcam is broken; concluding the desktop is fine just because the peripheral works elsewhere.
    
- **Resolve or escalate criteria:** after resolving, **verify with the user in the original application** before closing. Persistent controller issue → escalate.

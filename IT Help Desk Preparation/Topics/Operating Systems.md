1. What is an operating system, and what are its core responsibilities (process management, memory management, file systems, device drivers, user interface)? Explain each in simple terms as if you were describing it to a non‑technical user.
    
2. Differentiate between a desktop OS, a server OS, a mobile OS, and an embedded OS. Give one example of each and explain why a Help Desk technician might support all of them in a remote environment.
    
3. What is the kernel, and how does it differ from user space? Why is this distinction important when troubleshooting an application that crashes but does not bring down the entire system?
    
4. Explain how a Help Desk technician can identify processes consuming excessive CPU, memory, disk, or network resources. What evidence would you collect before deciding that a process is actually responsible for the user's performance problem?
    
5. What is a file system? Why do different operating systems use different file systems (e.g., NTFS, APFS, ext4), and how does this affect cross‑platform file sharing or external drive compatibility?
    
6. Describe the difference between a local user account and a domain/centralized account. Why is this distinction critical when a remote user cannot log in to their computer or access shared resources?
    
7. What is the principle of least privilege, and how does it apply to standard user accounts versus administrator/root accounts? How would you explain to a user why they should not browse the internet as an administrator?
    
8. Explain what a user profile is and what data it typically contains (documents, desktop, application settings). A remote user gets a new laptop and says “all my files are gone.” How would you determine if the files are missing or simply in a different profile?

9. What is a temporary user profile? What symptoms might indicate that Windows has logged a user into a temporary profile, and why should you avoid treating the temporary profile as the user's permanent storage location?
    
10. What is a driver, and why can an OS update sometimes break a device? Describe a general troubleshooting approach for a driver‑related problem that works on any OS.
    
11. Compare GUI (graphical user interface) and CLI (command‑line interface) from a Help Desk perspective. When would you choose one over the other during a remote session, and what are the risks of guiding a user through CLI commands?

12. What is the difference between a process and a thread? Why might a single application show multiple processes or consume CPU across multiple threads?

13. What is the difference between an incorrect system clock, incorrect time zone, and failed time synchronization? Why can each cause different symptoms?
    

### User Management & Security

14. What is multi‑factor authentication (MFA) at the OS level? How would you remotely assist a user who lost their phone and cannot receive MFA codes to log in?
    
15. Explain the concept of file and folder permissions in general terms (read, write, execute). A user cannot open a shared folder on a colleague’s computer. What general permission‑related issues would you investigate before escalating?
    
16. What is encryption at rest (e.g., full disk encryption)? Why is it important for laptops, and what are the implications for Help Desk if a user forgets their encryption password or recovery key?
    
17. Describe the purpose of an OS firewall and antivirus/anti‑malware software. A user complains their computer is slow and they see many pop‑ups. What general security checks would you perform remotely?
    
18. What is a safe mode or recovery mode? How would you guide a user to boot into it if their OS is not starting normally, and what types of problems can you diagnose once there?

19. What is the difference between authentication and authorization? Give a Help Desk example where a user successfully authenticates but is not authorized to access a resource.

20. What is User Account Control (UAC), and why can a user who is a member of the local Administrators group still be prompted for elevation?

21. What is permission inheritance? How can inherited permissions cause a user to have access or restrictions that are not immediately visible on the folder itself?

22. What is the difference between encrypting a disk and protecting an account with a password? Why does disk encryption still protect data if an attacker removes the drive and connects it to another computer?
    

### Software Management & Updates

23. Explain the general process of installing software on a computer. What are the common reasons an installation might fail across any OS (permissions, disk space, compatibility, antivirus, corrupted installer)?
    
24. Why are operating system updates important? Describe the risks of delaying updates and the potential issues that can arise immediately after an update. How would you remotely help a user who cannot boot after an update?
    
25. What is a package manager, and how does it differ from downloading an installer from a website? What are the security advantages of using official repositories?
    
26. A user wants to uninstall an application but it does not appear in the normal “Add/Remove Programs” list. What general troubleshooting steps would you take to remove stubborn software?
    
27. Explain the concept of startup programs (or login items). How can too many startup programs affect performance, and how would you remotely guide a user to disable unnecessary ones?
    

### Storage, Backups & Recovery

28. Differentiate between a full backup, an incremental backup, and a differential backup. Why should a Help Desk agent care about backup types when supporting remote users?

29. What is the difference between an update, an upgrade, a security patch, and a driver update? Why does the distinction matter when documenting or troubleshooting a problem?
    
30. What is a system restore point or snapshot? How would you guide a user to use it after a bad driver installation or a malware infection?

31. What is the difference between a partition, a volume, a filesystem, and a drive letter/mount point?

32. A user’s hard drive is full. What general strategies would you suggest to free up space, and how would you help them identify large files or folders without accidentally deleting important system data?
    
33. Explain the difference between an SSD and an HDD from an OS perspective (how the OS sees them, not the physical hardware). How does this affect disk defragmentation or TRIM?
    

34. What is the difference between a backup and file synchronization? Why does having files synced to OneDrive or another cloud service not necessarily mean the user has a complete backup?
    

### Basic Troubleshooting Methodology

35. Describe a general troubleshooting methodology for any OS‑related problem: identify the problem, establish a theory, test the theory, form a plan, implement, verify, document. Apply this to a ticket where a user reports “my computer is very slow.”
    
36. A user says their computer will not boot. What are the first five questions you would ask remotely to determine if the problem is hardware, OS corruption, or a recent change?
    
37. Explain the difference between a hard reboot and a soft reboot. When is each appropriate during a remote support session, and what are the risks of a hard reboot?
    
38. A user reports that an application freezes frequently. How would you determine if the issue is specific to that application, the OS, or the hardware? What general remote diagnostic steps would you take?
    
39. What is event logging, and why is it important across all operating systems? How would you guide a user to access basic system logs, and what types of errors would you look for when troubleshooting a crash or unexpected shutdown?

40. Why is reproducing a problem useful during troubleshooting? When might you deliberately avoid reproducing it, especially when data loss, security, or hardware damage is possible?

41. A user reports that an application is broken. What questions would you ask to determine whether the issue affects only that user, that computer, multiple users, or the entire organization? Why does determining scope matter?

42. How can a Help Desk technician determine whether a problem is a known issue rather than an isolated incident? What sources of information should they check before repeatedly troubleshooting the same problem?
    

### Cross‑Platform & Remote Support

43. A remote user switches between a Windows PC, a Mac, and a Linux laptop. What are the biggest challenges they might face with file compatibility, keyboard shortcuts, and software availability? How would you help them navigate these differences?
    
44. What is a remote desktop protocol? Compare common approaches (RDP, VNC, SSH, proprietary tools) at a high level. What security considerations should a Help Desk agent keep in mind when using remote access tools?
    
45. A user needs to transfer a large file from their work computer to their personal computer. What general methods would you suggest that work across different operating systems, and what security policies might apply?
    
46. Explain the concept of a user environment variable or system path. Why can an application work for one user but not another on the same computer? How would you approach this without getting into OS‑specific commands yet?
    
47. A user’s clock is wrong, causing authentication failures and website errors. Why is time synchronization important across operating systems, and how would you guide them to fix it remotely?
    
48. What is a “clean install” of an operating system, and when might it be necessary? What are the risks and what should a Help Desk agent do to prepare a user for a clean install (backup, license keys, application inventory)?
    
49. Describe the general process for creating a new user account on any OS. Why might a Help Desk agent need to create a temporary account to test if a problem is profile‑related?
    
50. A user reports that their computer restarts randomly. What OS‑related causes could be responsible (automatic updates, driver crashes, power settings, overheating)? How would you differentiate an OS issue from a hardware issue remotely?
    
51. Explain the purpose of a “hosts file” and how it can be used to block websites or redirect traffic. Why might a Help Desk agent need to check it when a user cannot reach a specific website, even though the internet works otherwise?
    
52. What are the key differences between a 32‑bit and a 64‑bit operating system? How does this affect software installation and memory usage, and how would you remotely check which version a user has?

53. A Windows application reports that a required service is not running. What is a service dependency, and how would you determine whether restarting one service could affect other applications?

54. A computer worked correctly before an OS update but stopped working afterward. How would you determine whether the update caused the issue, and what rollback or recovery options might be appropriate?

55. What security precautions should a Help Desk technician take before starting a remote support session? Consider user consent, authentication, session recording, privileged actions, sensitive information, and ending the session properly.

56. A remote support tool is connected, but the technician cannot interact with an administrator prompt. Why might this happen, and what legitimate mechanisms can an organization use to handle elevated actions remotely?
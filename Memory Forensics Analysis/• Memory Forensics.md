--- ---

<h2>What is Memory Forensics?</h2>

Memory forensics is the analysis of the volatile memory that is in use when a computer is powered on. Computers use dedicated storage devices called Random Access Memory (RAM) to remember what is being performed on the computer at the time. RAM is extremely quick and is the preferred method of storing and accessing data. However, it is limited compared to storage devices such as hard drives. This type of data is volatile because it will be deleted when the computer is powered off. RAM stores data such as your clipboard or unsaved files. 

We can analyse a computer's memory to see what applications (processes), what network connections were being made, and many more useful pieces of information. For example, we can analyse the memory of a computer infected with malware to see what the malware was doing at the time.

Let's think about cooking. You normally store all of your food in the fridge - a hard drive is this fridge. When you are cooking, you will store ingredients on the kitchen counter so that you can quickly access them, but the kitchen counter (RAM) is much smaller than a fridge (hard drive)

---

<h2>Why is Memory Forensics Useful?</h2>

Memory forensics is an extremely important element when investigating a computer. A memory dump is a full capture of what was happening on the Computer at the time, for example, network connections or things running in the background. Most of the time, malicious code attempts to hide from the user. However, it cannot hide from memory.

We can use this capture of the memory for analysis at a later date, especially as the memory on the computer will eventually be lost (if, for example, we power off the computer to prevent malware from spreading). By analysing the memory, we can discover exactly what the malware was doing, who it was contacting, and such forth.

---

<h2>An Introduction to Processes</h2>

At the simplest, a process is a running program. For example, a process is created when running an instance of notepad. You can have multiple processes for an application (for example, running three instances of notepad will create three processes). This is important to know because being able to determine what processes were running on the computer will tell us what applications were running at the time of the capture.

On Windows, we can use Task Manager_(pictured below)_ to view and manage the processes running on the computer.

![A picture of Window's Task Manager](https://tryhackme-images.s3.amazonaws.com/user-uploads/5de96d9ca744773ea7ef8c00/room-content/68217febd77dcd845ba608bb5ef6f34f.png)


On a computer, processes are usually categorised into two groups:
![[Pasted image 20221211180533.png]]
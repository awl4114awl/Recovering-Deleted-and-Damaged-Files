<p align="left">
<img src="https://i.imgur.com/t23TXuR.png" height="20%" width="20%" alt="daubert standard"/>
</p>

Introduction

Data recovery techniques are the principal ancestor to modern digital forensics. When computers were much simpler and not connected to the Internet, digital forensic investigations were largely a matter of finding and recovering deleted data from a single hard drive. While today's forensic investigations can span computers, networks, smartphones, and the cloud, data recovery is still a critical component.

 

When a user deletes a file, the file is typically moved to the Trash (Mac OS) or Recycle Bin (Windows). However, moving a file to the Trash or Recycle Bin does not actually delete the file. It simply changes the file's location and designates the file as planned for deletion. Just like the trash can in your own home, you can easily reach in and pull out an item if you change your mind about throwing it out. A file will only be considered "deleted" after the user runs the Empty Trash or Empty Recycle Bin function. However, emptying the Trash or Recycle Bin still does not actually remove the data. The only thing that is removed is the reference in the master file table that tells the operating system where the file was located. From the operating system’s perspective, you are only removing the map to the data, not the data itself. Removing the map gives the operating system permission to mark that area of the hard drive as "free" and overwrite it should new data need to be written there, but until an overwrite occurs, the data remains intact.

 

Of course, there are many other ways of deleting data beyond moving a file to the Recycle Bin and emptying it. Some more effective data deletion methods include delete with overwriting and physical destruction. A delete with overwriting means that the data is deleted, and then new random data is written to the drive several times, making the recovery of the original files very difficult or impossible. Physical destruction is just that – the destruction of the actual hard drive along with all the data stored on it. This can be accomplished through various methods, including shredding, melting, or crushing the hard drive.

 

In this lab, you will assume the role of a digital forensics specialist who has been assigned to a case involving intellectual property theft. After obtaining a search warrant, the local authorities have seized multiple computers from the suspects and transferred images of their hard drives to the digital forensics team. So far, no incriminating evidence has been found on the drive images, but your boss, the lead investigator, believes the suspects may have deleted incriminating evidence. As a digital forensics specialist, you will use professional data recovery tools and techniques to recover deleted data from different operating systems and file systems.



Lab Overview

SECTION 1 of this lab has two parts, which should be completed in the order specified.

 

    In the first part of the lab, you will recover data from a Windows NTFS drive image using E3.

    In the second part of the lab, you will recover data from a Linux Ext4 drive image using Autopsy.

SECTION 2 of this lab allows you to apply what you learned in SECTION 1 with less guidance and different deliverables, as well as some expanded tasks and alternative methods. You will pause your investigation to learn more about recovering deleted data directly from live Windows and Linux systems. You will also learn how partially deleted data can be recovered using data carving techniques.

 

Finally, you will explore the virtual environment on your own in SECTION 3 of this lab to answer a set of questions and challenges that allow you to use the skills you learned in the lab to conduct independent, unguided work - similar to what you will encounter in a real-world situation.



Learning Objectives

Upon completing this lab, you will be able to:

 

    Understand how files are deleted and recovered.

    Recover deleted files from NTFS, Ext4, FAT, and APFS drive images.

    Recover deleted files using data carving techniques.

    Recover deleted files from a live Windows system.

    Recover deleted files from a live Linux system.



Topology

This lab contains the following virtual machines. Please refer to the network topology diagram below.

 

    vWorkstation (Windows: Server 2019)
    TargetLinux01 (Linux: Ubuntu)

 

<img src="https://i.imgur.com/jhURZyJ.png" height="20%" width="20%" alt="daubert standard"/>
</p>



Tools and Software

The following software and/or utilities are required to complete this lab. Students are encouraged to explore the Internet to learn more about the products and tools used in this lab.

 

    E3
    Autopsy
    DiskDigger
    PhotoRec



Deliverables

Upon completion of this lab, you are required to provide the following deliverables to your instructor:

 

SECTION 1

 

    Lab Report file, including screen captures of the following:

 

    List of recovered files in the E3 Trash folder
    Patent file in the File Viewer
    Recovered files in the File Explorer
    Contents of the list of deleted files in Autopsy
    Recovered patent file

 

    Any additional information as directed by the lab:

 

    None

 

SECTION 2

 

    Lab Report file, including screen captures of the following:

 

    Deleted patent file in DiskDigger
    Recovered patent file
    Contents of the RAR archive in the /mnt/media/home/ash directory
    Failed mount attempt on the /dev/sdb5 device.
    Compressed files recovered by PhotoRec
    Backup files recovered from the RAR archive

 

    Any additional information as directed by the lab:

 

    None

 

SECTION 3

 

    Lab Report file, including screen captures of the following:

 

    Patent file recovered from the FAT32 drive image within E3
    Patent file recovered from the APFS drive image within Autopsy

 

    Any additional information as directed by the lab:

 

    None

<br />
<p align="center">
<img src="https://i.imgur.com/2dplsDk.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/L2lMLlp.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/xj5Aagj.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/xFni7LY.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/K6s7Tgq.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/cVRAlKF.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/ag5CHAT.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/DTv8pnf.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/gTUMOhg.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/eYo17kl.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/3RdRXAa.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/jWavYAV.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
<img src="https://i.imgur.com/Hzo7XjQ.jpeg" height="80%" width="80%" alt="forensics"/>
<br />
<br />
</p>

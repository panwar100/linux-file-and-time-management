# Linux Date, Time, Compression, and File Transfer Commands Guide
This repository provides examples and explanations for basic Linux commands related to date and time settings, file compression, extraction, and transfer.


## Table of Contents
1.[Set Date and Time](#1-set-date-and-time)

2.[File Compression and Extraction](#2-file-compression-and-extraction)

3.[Transfer Files Between Systems](#3-transfer-files-between-system)

4.[Using Rsync for Synchronization](#4-using-rsync-for-synchronization)

5.[Hard Link and Soft Link](#5-hard-link-and-soft-link)

6.[Disk Usage and Search Commands](#6-disk-usage-and-search-commands)

# 1. Set Date and Time
## View Current Date and Time

![Screenshot from 2024-12-02 22-04-16](https://github.com/user-attachments/assets/0bf583b9-fa18-4389-b120-962bfaf2805c)

Explain:

- timedatectl is a powerful command-line utility in Linux, particularly useful for managing and configuring the system's date, time, and timezone settings

- System clock synchronized: yes – The system time is being kept accurate by an external time source (NTP).

- NTP service: active – The service that keeps time in sync is currently running.

- RTC in local TZ: no – The hardware clock is using UTC instead of your local timezone, which is typical for most systems to avoid confusion when daylight saving time changes or timezones shift.

## List Available Timezones

![Screenshot from 2024-12-02 22-05-08](https://github.com/user-attachments/assets/0a1c8578-6add-4f29-9329-2d3d1571166d)

OR 

![Screenshot from 2024-12-02 22-06-57](https://github.com/user-attachments/assets/0f318cb2-1ccf-4bce-8a8a-428d134279b9)


## Set a Specific Timezone

![Screenshot from 2024-12-02 22-08-35](https://github.com/user-attachments/assets/cf761eca-1f16-4c07-a3bd-83fa86d7cf22)


## Enable/Disable Automatic Time Sync

- disable NTP

![Screenshot from 2024-12-02 22-09-35](https://github.com/user-attachments/assets/5bd96677-7233-439f-bb94-89a21c1fc7d2)

- Enable NTP

![Screenshot from 2024-12-02 22-11-24](https://github.com/user-attachments/assets/60d9edb5-f6bb-4a4f-9c33-cf028a9953a1)


# 2. File Compression and Extraction

## Create and Extract .tar Archives

a) Create a .tar Archive

![Screenshot from 2024-12-02 22-15-02](https://github.com/user-attachments/assets/737ef397-ed0c-4bc6-8080-d2d9cdebae74)


b) Extract a .tar Archive

![Screenshot from 2024-12-02 22-18-43](https://github.com/user-attachments/assets/a8d182d6-7a8e-45ad-820f-146ae9a6a1da)


c) Display Contents of a .tar Archive Without Extracting

![Screenshot from 2024-12-02 22-19-17](https://github.com/user-attachments/assets/80237b00-9634-47a7-b879-227b637a15da)


## Compress Files
a) Gzip Compression

tar -czf t2.tar.gz f1 f2 f3

b)Bzip Compression

tar -cjf t2.tar.bz2 f1 f2 f3

c) Xz Compression

tar -cJf t2.tar.xz f1 f2 f3

![Screenshot from 2024-12-02 22-30-51](https://github.com/user-attachments/assets/9b2f657a-df9f-49d8-9bbd-70f062c6429a)


## 3. Transfer Files Between Systems

### Using scp

The scp (secure copy) command in Linux is used to securely transfer files and directories between two systems over a network. It uses SSH (Secure Shell) for data transfer, ensuring that the communication is encrypted.

a) Send a File to Another System

![Screenshot from 2024-12-02 22-37-20](https://github.com/user-attachments/assets/384ffcb3-38e5-42c8-8b69-166549eb3be6)

![Screenshot from 2024-12-02 22-38-02](https://github.com/user-attachments/assets/e5bea147-4374-49c3-b78f-dab5c36bd370)


b) Retrieve a File from Another System

![Screenshot from 2024-12-02 22-40-01](https://github.com/user-attachments/assets/27c3dd9e-5afa-4c8b-81f7-21e2fadab808)


![Screenshot from 2024-12-02 22-41-37](https://github.com/user-attachments/assets/b9d7ac78-1217-495e-9fcd-0494e1bc3ebc)


### Using sftp

The sftp (Secure File Transfer Protocol) command in Linux is used for transferring files securely over a network. It operates over SSH (Secure Shell), ensuring encrypted communication between the client and the remote server.

a) Connect to Another System

sftp 192.168.1.13

b) Send a File

![Screenshot from 2024-12-02 22-49-03](https://github.com/user-attachments/assets/07b10a10-7ff6-4ec3-a8c3-e9fa754547f9)

c) Retrieve a File

![Screenshot from 2024-12-02 22-56-27](https://github.com/user-attachments/assets/e265a362-f045-48b5-9444-23f8f078b1bc)


## 4. Using Rsync for Synchronization

a) Create Directories and Files

![Screenshot from 2024-12-02 23-09-58](https://github.com/user-attachments/assets/52aab908-85d2-4ede-9682-feba4027ed5b)


b) Synchronize Directories

![Screenshot from 2024-12-02 23-08-59](https://github.com/user-attachments/assets/fc03e1ba-eac5-41e7-9a31-25fabe59a383)

c)Copy Only New/Updated Files

![Screenshot from 2024-12-02 23-12-07](https://github.com/user-attachments/assets/653e82fc-f60b-46c0-a89e-f61fd49f8f4e)


# 5. Hard Link and Soft Link
## Hard Link

a) Create and Verify Hard Link

![Screenshot from 2024-12-02 23-16-03](https://github.com/user-attachments/assets/13949cce-9dfe-4e36-8c00-1012c215d40e)

cat x  # View content

cat y  # Should match x

b) Delete Original File

![Screenshot from 2024-12-02 23-19-26](https://github.com/user-attachments/assets/25625e6e-d9fc-4be3-8951-fe09bff69d74)

remove x

- cat y  # Content remains accessible 
      
- After permission, number is given is change 1 to 2
       
## Soft Link

a) Create and Verify Soft Link

![Screenshot from 2024-12-02 23-21-17](https://github.com/user-attachments/assets/16e47ee0-5a43-427c-b1f7-30df4df56043)

- ls -l  # Verify symlink with arrow symbol
- Permission change 

b) Delete Original File

![Screenshot from 2024-12-02 23-22-35](https://github.com/user-attachments/assets/640e0ec8-7f3e-4e25-b575-6ada835e3f75)

remove x

cat u  # Error: No such file or directory

# 6. Disk Usage and Search Commands

## Disk Usage

![Screenshot from 2024-12-02 23-26-32](https://github.com/user-attachments/assets/85d6f55f-c7a1-4aed-ad19-34619c727f56)



## Locate Files by Name

The locate command in Linux is a fast way to search for files by name on the system. It uses a pre-built database (usually updated periodically) to quickly find files, making it faster than commands like find because it doesn’t have to search the filesystem in real time.

locate in -> iT find 'in' present file

![Screenshot from 2024-12-02 23-40-26](https://github.com/user-attachments/assets/110db8e5-d47a-465e-aff6-75f35d3803f9)


## Search with find

The find command in Linux is used to search for files and directories in a directory hierarchy based on various criteria. It’s a powerful tool for searching and managing files, offering flexibility in searching based on file names, types, permissions, sizes, and more.
 
![Screenshot from 2024-12-02 23-51-12](https://github.com/user-attachments/assets/36e4357e-c241-4185-bb6f-cf6c538fb927)


a) Find files:

find / -name ln

b) Find directories:

find / -type d 

find / -tpye d -name "dirname"

c) Find files only:

find / -type f

d) Find symbolic links:

find / -type l

e)Find files by size:

find / -size 10M  # Exactly 10MB

find / -size -10M # Less than 10MB

find / -size +10M # Greater than 10MB

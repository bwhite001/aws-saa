[[EFS]] is for POSIX Linux systems
FSx is for windows file system shared drive
supports SMB protocol and Windows NTFS, AD, ACL
Multi AZ
Data backed up daily to s3

*Lustre* - linux

parallel distributed file system, for large scale computing, HPC
can read s3 as a file system through Fsx
can be used on premise servers

File System deployment options
1. Scratch File System
	1. Temp storage
	2. Data is not replicated
	3. short term processing, optimize costs
2. Persistent file system
	1. Long term storage
	2. Data replicated within the same [[Availabilty Zone]]
	3. sensitive data
	
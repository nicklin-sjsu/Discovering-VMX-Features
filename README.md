# Discovering-VMX-Features
CMPE283 Assignment 1
In this assignment you will learn how to discover VMX features present in your processor by writing a Linux kernel module that queries these features.

Team Members: Hongru Lin

Team Members: Hongru Lin

Details:
For this assignment, my pc is Windows 10 running Intel CPU. So I started by researching how to set up VM on Win 10 and found VirtualBox to be the most accessible tool for VM. I downloaded both the VirtualBox and a Linux system. After installing VirtualBox, I created a new VM using the downloaded Linux system as image. Next, I enabled a shared folder between the host machine and VM so I could pass files to the VM. To setup the environment, I installed kernel headers using “sudo apt install linux-headers-$(uname -r)”, and installed gcc using “sudo apt install build-essential”.

After setting up the correct environment, I passed the sample files to the machine and start testings. I ran “make” to compile the file, and ran “sudo insmod cmpe283-1.ko” to install the module. Then run “dmesg” to print out the results. However, the %lxx prints out 0 as a result which makes all set “No” and all clear “Yes”. I asked Professor Larkin and he said VirtualBox does not support nested virtualization and suggested switching to VMWare. I went over the same steps to set up environments using VMWare, and everything ran correctly.

Next, I started implementing the code. I used the same format in the sample code, and locate the correct tables for control definitions in the Intel SDM. I copied all the bit positions and names to each array and specify the length of each array when printing. I skipped Tertiary Procbased controls since my CPU does not support that. After testing everything is working correctly. I pushed all the documents to Github and concluded this assignment.

Steps:
Clone the repository by running 
`git clone https://github.com/nicklin-sjsu/Discovering-VMX-Features.git`
Go into the repository
`cd Discovering-VMX-Features`
Install linux headers
`sudo apt install linux-headers-$(uname -r)`
Install gcc
`sudo apt install build-essential`
Compile files
`make`
Install Module
	`sudo insmod cmpe283-1.ko`
Print result
	`sudo dmesg`
Remove Module
`sudo rmmod cmpe283-1`

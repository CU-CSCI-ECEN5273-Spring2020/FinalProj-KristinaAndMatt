# Kristina And Matt's Final Project
_Description:_ Our main areas of focus are to modify the way traffic is routed for different applications (video streaming, FTP, HTTP, VoIP, etc.) and to create routing “tiers” for hosts. For example, we want to see if selecting different paths for different application types or user tiers can increase throughput and decrease latency for certain applications/hosts. Since video traffic is more sensitive to both throughput and latency as opposed to HTTP traffic, we wish to speed up its performance without severely impacting the performance of other application types. Similarly, high tier hosts will be given shorter routes and more available bandwidth to increase their performance.


To Run:

Install a VM image that includes the necessary tools pre-installed:
1. Download [VM Image](https://drive.google.com/uc?id=1lYF4NgFkYoRqtskdGTMxy3sXUV0jkMxo&export=download)
2. Import the virtual machine into VirtualBox. Open VirtualBox, select “File > Import Appliance”, and navigate to the downloaded file.
3. Pull git repository
4. Type make to run file

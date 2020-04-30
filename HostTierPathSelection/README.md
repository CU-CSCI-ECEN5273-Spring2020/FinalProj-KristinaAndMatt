# Final Project Kristina & Matt

## Host-Tier Path Selection

### Setup

Running the code requires a VM with specific packages installed.

There are two easy ways to do this...

**Option 1**

- Download the VM image [here](https://drive.google.com/uc?id=1lYF4NgFkYoRqtskdGTMxy3sXUV0jkMxo&export=download)
- Import the image into VirtualBox as a new appliance

**Option 2**

- Install vagrant
- `$cd vm/`
- `$vagrant up`

### Run the code

- From the VM, clone the repo
- Navigate to the HostTierPathSelection directory
- In either of the folders (Static or Dyn Switch Config), type `make run` from your terminal
- You should see a mininet prompt after the network is configured
- Use tools such as ping and iperf to test connections between each host
- From the mininet prompt, type `exit` to quit
- After exiting, type `make stop` or `sudo mn -c` to clean up the network

**For all testing, I recommend using DynSwitchConfig because it is easier to see the differences between the tiers.**

### Notes on Host Tiers and Promotion

For this implementation, Host 2 is "low-tier", while H1 and H3 are high-tier.
Since H1 and H2 are connected to the same switch, testing the differences in path selection 
between low and high tier hosts is accomplished by sending traffic to H3 on either H1 or H2. 

You will notice that pings between H2 and H3 take significantly longer than between H1 and H3 
because H2 is given sub-optimal paths with higher latency.

While testing using DynSwitchConfig, you will notice exiting mininet is different. 
This is due to a controller modification which allows for H2 to be promoted to high-tier. 
Upon exiting, you will be asked whether or not you wish to promote H2. Type 'y' and the controller 
will reconfigure the switches in the network to give H2 optimal paths. This can be verified with ping and iperf, 
similar to before.

### Topology

![alt text](https://github.com/CU-CSCI-ECEN5273-Spring2020/FinalProj-KristinaAndMatt/blob/master/HostTierPathSelection/topo.png "Topology")
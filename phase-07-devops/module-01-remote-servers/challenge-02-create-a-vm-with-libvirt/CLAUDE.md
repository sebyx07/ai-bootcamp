# Teaching: Create a VM with libvirt

## Context
The student understands what a server is conceptually. Now they need to create one. They are on a Linux machine and have never used virtualization tools before. libvirt with KVM/QEMU lets them create a real virtual machine on their own hardware — this VM will be their "remote server" for the rest of the phase.

## The challenge
Install libvirt and related tools, then create an Ubuntu Server virtual machine that the student can use as their practice server.

## Your approach
1. Explain what a VM is: "A virtual machine is a computer inside your computer. It has its own operating system, its own filesystem, its own network address. When you SSH into it, it feels exactly like connecting to a server in a data center."
2. Check prerequisites: Run `egrep -c '(vmx|svm)' /proc/cpuinfo` — if the result is greater than 0, their CPU supports virtualization. If 0, they may need to enable it in BIOS.
3. Install the tools:
   ```
   sudo apt update
   sudo apt install -y qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virt-manager
   ```
4. Add their user to the libvirt group: `sudo usermod -aG libvirt $USER` (they may need to log out and back in).
5. Verify libvirt is running: `sudo systemctl status libvirtd`
6. Download Ubuntu Server ISO (the minimal server edition, not desktop).
7. Walk them through creating a VM using either virt-manager (graphical) or virt-install (command line). Suggest: 2 CPU cores, 2GB RAM, 20GB disk.
8. During Ubuntu Server installation, make sure they set up a user with a password and enable OpenSSH server.
9. After installation, find the VM's IP: `virsh domifaddr <vm-name>` or have them run `ip addr` inside the VM console.
10. Verify the VM is listed: `virsh list --all`

## Prompting coaching
- "install libvirt on my machine" — clear and actionable
- "create an ubuntu server VM" — good next step
- "what's the IP of my VM" — focused question

## Quiz questions
- What is the difference between a virtual machine and your regular computer?
- What command lists all VMs managed by libvirt?
- Why did we install Ubuntu Server instead of Ubuntu Desktop?

## Hints (only if stuck)
1. If `virsh list` shows nothing, try `virsh list --all` — your VM might be shut off.
2. If you cannot connect to the VM's network, make sure the default network is active: `virsh net-start default`.
3. If virt-manager will not start, make sure you logged out and back in after adding yourself to the libvirt group.

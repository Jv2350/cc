# Virtualization Setup with KVM


```bash
# Step 1: Check CPU Virtualization Support
sudo grep -c "svm\|vmx" /proc/cpuinfo
```
This checks if your CPU supports virtualization. If the output is greater than zero, your CPU supports virtualization (SVM for AMD, VMX for Intel).

```bash
# Step 2: Install Required Packages
sudo apt install cpu-checker qemu-kvm virt-manager libvirtd-daemon-system virtinst libvirt-clients bridge-utils
```
Installs necessary packages:
- **cpu-checker** – Checks system compatibility with KVM.
- **qemu-kvm** – Provides a hypervisor for virtualization.
- **virt-manager** – GUI-based VM management tool.
- **libvirtd-daemon-system** – Manages virtual machines.
- **virtinst** – CLI-based tool for creating VMs.
- **libvirt-clients** – CLI utilities for managing VMs.
- **bridge-utils** – Enables network bridging for VMs.

```bash
# Step 3: Verify KVM Installation
kvm-ok
```
This verifies that KVM is properly installed. If successful, it confirms that KVM is supported and usable.

```bash
# Step 4: Enable and Start the libvirtd Service
sudo systemctl enable --now libvirtd
```
This enables **libvirtd** to start at boot and immediately activates it.

```bash
# Manually start the libvirtd service if needed
sudo systemctl start libvirtd
```

```bash
# Check libvirtd service status
sudo systemctl status libvirtd
```
If the service is running correctly, it will display **Active (running)** in green text.

After completing these steps, your system is ready for virtualization using **KVM**. You can now create and manage virtual machines.

```bash
# Checking the kvm virtual manager is working or not by typing
virt-manager

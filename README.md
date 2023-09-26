# udevadm-naming-conv
Nic naming convention using udevadm

```bash
udevadm test-builtin net_id /sys/class/net/eno1 2>/dev/null
```

```bash
udevadm test-builtin net_id /sys/class/net/ens1f0 2>/dev/null
```

![image](https://github.com/AdityaKoranga/udevadm-naming-conv/assets/95766110/7753cd7e-c79a-49b9-ac2e-23f2732ac9d4)

![image](https://github.com/AdityaKoranga/udevadm-naming-conv/assets/95766110/63afecfc-f7f2-4e70-9ec8-78f500219900)

The output of the udevadm command you've provided shows the deterministic names that udev has derived for the network interfaces on two different systems. Let's break down what each of these outputs mean:

`For ens1f0`:

`ID_NET_NAMING_SCHEME`=rhel-8.0: Indicates the naming scheme used is based on the conventions introduced in Red Hat Enterprise Linux 8.0.

`ID_NET_NAME_MAC`=enx40a6b720c814: This is a name based on the MAC address of the network interface. The format "enx" followed by MAC address ensures this name is unique.

`ID_OUI_FROM_DATABASE`=Intel Corporate: This indicates that the OUI (Organizationally Unique Identifier) from the MAC address belongs to Intel Corporate.

`ID_NET_NAME_PATH`=enp24s0f0: This name is derived from the device's path with respect to the PCI bus. "enp24s0f0" means the device is connected to PCI bus 24, slot 0, and function 0.

`ID_NET_NAME_SLOT`=ens1f0: This name is derived from the physical hotplug slot information. "ens1f0" indicates the device is in slot 1, function 0.

For `eno1`:

`ID_NET_NAMING_SCHEME`=v249: Indicates the naming scheme version used is "v249".

`ID_NET_NAME_MAC`=enx3cecef0fd34e: Similar to above, this is a name based on the MAC address.

`ID_OUI_FROM_DATABASE`=Super Micro Computer, Inc.: The OUI from the MAC address belongs to Super Micro Computer, Inc.

`ID_NET_NAME_ONBOARD=eno1`: This indicates that the network interface is an onboard device. "eno1" means it's the first onboard network interface.

`ID_NET_LABEL_ONBOARD`=Intel Ethernet X550 #1: This is the label for the onboard network interface.

`ID_NET_NAME_PATH=enp1s0f0`: As before, this name is derived from the device's path on the PCI bus.

In summary, udev uses several methods to derive consistent and predictable names for network interfaces. The naming schemes include names based on MAC addresses, PCI bus positions, and physical hotplug slot positions, among others. The goal is to ensure network interface names remain consistent across reboots and hardware changes.


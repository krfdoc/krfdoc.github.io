---
title: XCP-ng PCI Passthrough
date: 2023-04-25 10:00:00 -0500
categories: [XCP-ng]
tags: [linux,XCP-ng,Passthrough]
---

## XCP-ng PCI Passthrough

> Note the pci bus addresses listed below are accurate for the intel 4port nic on Marty XCP-ng hypervisor
{: .prompt-warning }

### How To:

* List PCI bus devices
```terminal
lspci
```
* Tell XCP-ng not to use this device ID for Dom0:
```terminal
/opt/xensource/libexec/xen-cmdline --set-dom0 "xen-pciback.hide=(0000:02:00.0)(0000:02:00.1)(0000:02:00.2)(0000.02:00.3)"
```
* To remove any passthrough devices from dom0
```terminal
/opt/xensource/libexec/xen-cmdline --delete-dom0 xen-pciback.hide
```
* Reboot system
* Check PCI assignable list w/:
```terminal
xl pci-assignable-list
```

### Next...etc...whatever

```terminal
sudo cp -r /path/to/directory /path/to/location/new-name
```

> -r means recursive and should be used to perform action on all sub folders and files
{: .prompt-tip }

### Remove

```terminal
sudo rm -r /path/to/dir
```

> This is a "info box"
{: .prompt-info }



> This is a "danger box"
{: .prompt-danger }
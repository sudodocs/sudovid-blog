---
title: "Nutanix: A Whitepaper!"
date: 2020-06-02
categories: 
  - "tech"
tags: 
  - "acropolis"
  - "cluster"
  - "hci"
  - "hypervisor"
  - "lun"
  - "nas"
  - "node"
  - "nutanix"
  - "nutanix-prism"
  - "raid"
  - "san"
  - "server"
coverImage: "/sudovid-blog/images/nutanix.png"
---

In the era of enterprise cloud, modern enterprise datacenter must support virtualization with high availability and live **VM** migration. The traditional storage area networks (**SAN**) or network attached storage (**NAS**) doesn’t suit. Instead, they are ideal to manage a logical unit number (**LUN**). A **LUN** can be a single disk, an entire redundant array of independent disks (**RAID**), or disk partitions. The setup requires an entire infrastructure and adds additional costs. Additionally, legacy hypervisors are required to be bought, deployed, and managed as a standalone product with their complex licenses. A hypervisor management tool also needs to be installed separately. This adds additional dependency on software. The face of enterprise class virtualization hasn’t changed over a decade until _**Nutanix**_.

_**Nutanix Acropolis Hypervisor**_ (**AHV**) offers a hyper-converged infrastructure (**HCI**) for enterprise-class virtualization, storage, and computation. Enterprise-class virtualization includes live migration, VM high availability, network management, one-click hypervisor upgrade, one-click hypervisor conversion, cross-hypervisor backup, and cross-hypervisor disaster recovery. _**Nutanix**_ distributed file system removes the additional layer of centralized storage cost and integrates its own local flash drives (for faster execution) and hard drives (for high capacity storage) to act as a single storage pool for integrated four nodes. The storage pool can be partitioned into one or more data stores. These data stores are presented to the hypervisor by using the standard **NFS** protocol for all hosted VMs. Each node in a _**Nutanix**_ cluster has a controller **VM** that takes care of resilience. _**Nutanix**_ enterprise level virtual stack includes _**Nutanix Prism**_ that provides a centralized web-based solution. It takes care of everything from storage to virtual machine. It is also scalable without the need of an additional hypervisor.

When a **VM** requests a write operation, the local controller **VM** writes data in the local flash storage. To ensure fault tolerance, data is written synchronously in flash storage across all other nodes. For a read operation, controller **VM** fetches data from the local flash storage. The stored data never traverses over a network. This helps in minimizing latency and ensures data security. The local hard drive stores data only when the data becomes cold. But if controller **VM** gets data requests more frequently, the data is promoted again to the flash storage.

In case of a node failure, high availability is supported ensuring that the **VM** is started automatically over another node. When a **VM** requests read-write operation, the local controller **VM** checks for the availability of data on other nodes if it’s not stored locally. The control is passed on to the node where data resides. The data is then sent back to the local controller **VM** over a standard Ethernet network. The local controller **VM** passes the data to the **VM** through the hypervisor and stores the data in the local flash storage for future data requests. Additionally, _**Nutanix**_ synchronizes the data again over other nodes restoring the fault tolerance state. Each node in the _**Nutanix**_ cluster runs independently and all is packaged under a **2U** rackmount server. _**Nutanix**_ is perfect for any virtual workload and deployment, private cloud projects, and big data applications. With _**Nutanix**_, possibilities are endless.

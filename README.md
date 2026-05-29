# 3-Node Proxmox Virtualization Cluster

Designed and deployed a highly available 3-node Proxmox virtualization cluster using Intel-based mini PCs with dedicated backend networking, ZFS storage, firewall segmentation, and cluster management.

The project focused on:
- virtualization infrastructure
- network segmentation
- secure cluster communications
- ZFS storage architecture
- Linux systems administration
- homelab/private cloud engineering
- resilience and disaster recovery
## Hardware Specifications

| Component | Specification |
|---|---|
| Nodes | 3x MINISFORUM NAB8 Plus |
| CPU | Intel Core i7-12800H |
| RAM | 32GB DDR4 per node |
| Storage | 512GB NVMe SSD per node |
| Backend Network | Dedicated 2.5GbE |
| Management Network | 1GbE |
| Power | UPS backup power supply |
| Filesystem | ZFS |
| Hypervisor | Proxmox VE 8.x |
## Network Architecture

| Network | Purpose | Subnet |
|---|---|---|
| Management | Proxmox UI / SSH | 192.x.x.0/24 |
| Backend Cluster | Corosync / Migration | 10.x.x.0/24 |
## Node Addressing

| Node | Management IP | Backend IP |
|---|---|---|
| pve1 | 192.x.x.xa | 10.x.x.xa |
| pve2 | 192.x.x.xb | 10.x.x.xb |
| pve3 | 192.x.x.xc | 10.x.x.xc |
## Bridge Configuration

| Bridge | Interface | Purpose |
|---|---|---|
| vmbr0 | enp1s0 | Management / VM traffic |
| vmbr1 | enp2s0 | Cluster backend |
## Firewall Policies

| Layer | Policy |
|---|---|
| Datacenter Input | DROP |
| Datacenter Output | ACCEPT |
| Node Input | DROP |
| Node Output | ACCEPT |

# MAC Address

A MAC (Media Access Control) address is a physical and unique identifier assigned to a Network Interface Card (NIC). It is used for communication between devices within a local network (LAN).

Devices inside a LAN use MAC addresses to deliver data frames to the correct physical device.

---

## Structure of MAC Address

A MAC address is 48 bits long and is written as 12 hexadecimal characters separated by colons or hyphens.

Example:
00:1A:2B:3C:4D:5E

- The first 24 bits represent the OUI (Organizationally Unique Identifier), which identifies the manufacturer of the network card.
- The last 24 bits are assigned by the manufacturer to uniquely identify the device.

MAC addresses are embedded by the manufacturer, although they can sometimes be changed (MAC spoofing).

---

## Types of MAC Communication

### Unicast
Communication between one device and one specific device within the local network.

### Multicast
Communication from one device to a group of devices within the LAN.

### Broadcast
Communication from one device to all devices within the local network.  
Example: ARP request messages are broadcast.

---

## Role in Data Transmission

MAC addresses are used at the Data Link Layer (Layer 2) of the OSI model. They are responsible for frame delivery within a local network.

When a device wants to send data:
- It uses the destination IP address to identify the target.
- It uses ARP to resolve that IP address into a MAC address.
- The frame is then delivered using MAC addressing.

- Without MAC addresses, a switch inside a LAN would have no way to deliver that frame to the correct physical device — it forwards based on MAC address, not IP.

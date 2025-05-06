Optiplex Small Form Factor 2.5GbE
---------------------------------

This provides a guide to adding a second ethernet (in this case 2.5GbE)
to a Dell Optiplex Small Form Factor via the M2 slot. The involves
replacing the M2 wireless card if it is installed.

Having a second network interface allows the Optiplex to be used as a gateway
using opnsense or similar. If the Optiplex has a vPro enabled CPU it can be
remotely managed using IME on the onboard 1GbE interface.

License
-------

CC BY-SA: https://creativecommons.org/licenses/by-sa/4.0/

Fund me here: https://ko-fi.com/richardatlateralblast

Requirements
------------

This requires a M.2 A and E Intel i225V B3 i226V 2.5G Ethernet, e.g:

https://www.aliexpress.com/item/1005007273213520.html

Procedure
---------

As mentioned this involves removing the existing M2 2230 card if it exists.
This is often a wireless chipset. If the chipstet is vPro enabled with IME,
this will remove the ability to connect to the IME interface via wireless.
The spare slot on the back will be used to mount the RJ45 interface connector.

![Rear View Beforehand](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/rear_before.jpeg)

If a 2.5in drive is installed, the drive will need to be removed to get to the slot.

![Top View With Drive](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/top_view_with_drive.jpeg)

Once the drive is removed, the slot can be accessed. If there is a card in the M2
slot it will need to be removed.

![Top View Without Drive](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/top_view_without_drive.jpeg)

Now the M2 card, the slot cover, and antenna needs to be removed:

![Top View Without M2](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/top_view_without_m2.jpeg)

You will need to remove the connector to install the M2 card:

![Top View With M2](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/top_view_with_m2.jpeg)

Once the M2 card is intalled the RJ45 connector can be attached and the cable routed:

![Top View With M2](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/top_view_with_m2_and_cable.jpeg)

Once complete we can put the case back on and use the new interface:

![Rear View With UTP](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/rear_view_with_utp.jpeg)

Tools like ethtool may report the interface as 1GbE, but as we can see from
dmesg, the kernel driver sees it as 2.5GbE:

![Kernel Output](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/dmesg_output.jpeg)

Depending on the age of the Optiplex, you should be able to get 2Gb or better throughput:

![Kernel Output](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/iperf3_output.jpeg)

This was achieved on a Intel i5 based Optiplex:

![Neofetch Output](https://raw.githubusercontent.com/lateralblast/OptiplexSmallFormFactor2.5GbE/master/neofetch_output.jpeg)

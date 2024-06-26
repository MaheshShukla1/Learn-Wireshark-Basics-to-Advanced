# Learn-Wireshark-Basics-to-Advanced

## Default Columns In a Packet Capture Output

| **NAME**              | **DESCRIPTION**                                               |
| --------------------- | ------------------------------------------------------------- |
| **No**.               | Frame number from the beginning of the packet capture         |
| **Time**              | Seconds from the first frame                                  |
| **Source (src)**      | Source address, commonly an IPv4, IPv6 or Ethernet address    |
| **Destination (dst)** | Destination address                                           |
| **Protocol**          | Protocol used in the Ethernet frame, IP packet, or TC segment |
| **Length**            | Length of the frame in bytes                                  |

## Logical Operators

| **OPERATOR**    | **DESCRIPTION**    | **EXAMPLE**                                                                  |
| --------------- | ------------------ | ---------------------------------------------------------------------------- |
| **and or &&**   | Logical AND        | All the conditions should match                                              |
| **or or \|**    | Logical OR         | Either all or one of the conditions should match                             |
| **xor or ^^**   | Logical XOR        | Exclusive alterations - only one of the two conditions should match not both |
| **not or !**    | Not (Negation)     | Not equal to                                                                 |
| **[ n ] [ … ]** | Substring operator | Filter a specific word or text                                               |

## Filtering Packets (Display Filters)

| ****OPERATOR**** | ****DESCRIPTION****   | **EXAMPLE**               |
| ---------------- | --------------------- | ------------------------- |
| **eq or ==**     | Equal                 | ip.dest  ==  192.168.1.1  |
| **ne or !=**     | Not equal             | ip.dest  !=   192.168.1.1 |
| **gt or >**      | Greater than          | frame.len   >   10        |
| **it or <**      | less than             | frame.len  <   10         |
| **ge or >=**     | Greater than or equal | frame.len  >=   10        |
| **le or <=**     | Less than or equal    | frame.len  <=   10        |

## Filter Types

| **NAME**           | **DESCRIPTION**                     |
| ------------------ | ----------------------------------- |
| **Capture filter** | Filter packets during capture       |
| **Display filter** | Hide packets from a capture display |

## Wireshark Capturing Modes

| **NAME**             | **DESCRIPTION**                                                                         |
| -------------------- | --------------------------------------------------------------------------------------- |
| **Promiscuous mode** | Sets interface to capture all packets on a network segment to which it is associated to |
| **Monitor mode**     | Setup the wireless interface to capture all traffic it can receive (Unix/ Linux only)   |

## Miscellaneous

| **NAME**                | **DESCRIPTION**         |
| ----------------------- | ----------------------- |
| **Slice Operator**      | [ … ] - Range of values |
| **Membership Operator** | {} - In                 |
| **CTRL+E**              | Start/Stop Capturing    |

## Capture Filter Syntax

| **SYNTAX** | **PROTOCOL** | **DIRECTION** | **HOSTS**   | **VALUE** | **LOGICAL OPERATOR** | ****EXPRESSIONS****  |
| ---------- | ------------ | ------------- | ----------- | --------- | -------------------- | -------------------- |
| Example    | tcp          | src           | 192.168.1.1 | 80        | and                  | tcp dst 202.164.30.1 |

## Display Filter Syntax

|**SYNTAX**|**PROTOCOL**|**STRING 1**|**STRING 2**|**COMPARISON OPERATOR**|**VALUE**|**LOGICAL OPERATOR**|**EXPRESSIONS**|
|---|---|---|---|---|---|---|---|
|Example|http|dest|ip|==|192.168.1.1|and|tcp port|

## Keyboard Shortcuts - Main Display Window

| **ACCELERATOR**      | **DESCRIPTION**                                                                               | **ACCELERATOR**      | **DESCRIPTION**                                                              |
| -------------------- | --------------------------------------------------------------------------------------------- | -------------------- | ---------------------------------------------------------------------------- |
| **Tab or Shift+Tab** | Move between screen elements, e.g. from the toolbars to the packet list to the packet detail. | **Alt+→ or Option→** | Move to the next packet in the selection history.                            |
| **↓**                | Move to the next packet or detail item.                                                       | **→**                | In the packet detail, opens the selected tree item.                          |
| **↑**                | Move to the previous packet or detail item.                                                   | **Shift+→**          | In the packet detail, opens the selected tree items and all of its subtrees. |
| **Ctrl+ ↓ or F8**    | Move to the next packet, even if the packet list isn't focused.                               | **Ctrl+→**           | In the packet detail, opens all tree items.                                  |
| **Ctrl+ ↑ Or F7**    | Move to the previous packet, even if the packet list isn't focused                            | **Ctrl+←**           | In the packet detail, closes all the tree                                    |
| **Ctrl+.**           | Move to the next packet of the conversation (TCP, UDP or IP).                                 | **Backspace**        | In the packet detail, jumps to the parent node.                              |
| **Ctrl+,**           | Move to the previous packet of the conversation (TCP, UDP or IP).                             | **Return or Enter**  | In the packet detail, toggles the selected tree item.                        |

## Protocols - Values

ether,  fddi,  ip,  arp,  rarp,  decnet,  lat, sca,  moprc,  mopdl,  tcp  and  udp

## Common Filtering Commands

| **USAGE**                        | **FILTER SYNTAX**                                 |
| -------------------------------- | ------------------------------------------------- |
| **Wireshark Filter by IP**       | ip.add == 10.10.50.1                              |
| **Filter by Destination IP**     | ip.dest == 10.10.50.1                             |
| **Filter by Source IP**          | ip.src == 10.10.50.1                              |
| **Filter by IP range**           | ip.addr >= 10.10.50.1 and ip.addr <=10.10.50.100  |
| **Filter by Multiple Ips**       | ip.addr == 10.10.50.1 and ip.addr == 10.10.50.100 |
| **Filter out IP adress**         | ! (ip.addr == 10.10.50.1)                         |
| **Filter subnet**                | ip.addr == 10.10.50.1/24                          |
| **Filter by port**               | tcp.port == 25                                    |
| **Filter by destination port**   | tcp.dstport == 23                                 |
| **Filter by ip adress and port** | ip.addr == 10.10.50.1 and Tcp.port == 25          |
| **Filter by URL**                | http.host == "host name"                          |
| **Filter by time stamp**         | frame.time >= "June 02, 2019 18:04:00"            |
| **Filter SYN flag**              | Tcp.flags.syn == 1 and tcp.flags.ack ==0          |
| **Wireshark Beacon Filter**      | wlan.fc.type_subtype = 0x08                       |
| **Wireshark broadcast filter**   | eth.dst == ff:ff:ff:ff:ff:ff                      |
| **Wireshark multicast filter**   | (eth.dst[0] & 1)                                  |
| **Host name filter**             | ip.host = hostname                                |
| **MAC address filter**           | eth.addr == 00:70:f4:23:18:c4                     |
| **RST flag filter**              | tcp.flag.reset == 1                               |

## Wireshark Command Generator

Say goodbye to the hassle of trying to remember the exact syntax for your Wireshark commands! With our Wireshark Command Generator, you can simply say what you need Wireshark to do, and we will generate the command for you.

Generate

## Main Toolbar Items

| **TOOLBAR ICON**                                                                                                                     | **TOOLBAR ITEM**                | **MENU ITEM**                      | **DESCRIPTION**                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------- |
| ![](https://www.stationx.net/wp-content/uploads/2020/07/Start-1.png)                                                                 | **Start**                       | Capture → Start                    | Uses the same packet capturing options as the previous session, or uses defaults if no options were set |
| ![](https://www.stationx.net/wp-content/uploads/2020/07/Stop.png)                                                                    | **Stop**                        | Capture → Stop                     | Stops currently active capture                                                                          |
| ![](https://www.stationx.net/wp-content/uploads/2020/07/Restart.png)                                                                 | **Restart**                     | Capture → Restart                  | Restart active capture session                                                                          |
| ![](https://www.stationx.net/wp-content/uploads/2020/07/options.png)                                                                 | **Options...**                  | Capture → Options…                 | Opens "Capture Options" dialog box                                                                      |
| ![](https://www.stationx.net/wp-content/uploads/2020/07/open.png)                                                                    | **Open...**                     | File →open…                        | Opens "File open" dialog box to load a capture for viewing                                              |
| ![](https://www.stationx.net/wp-content/uploads/2020/07/save-as.png)                                                                 | **Save As...**                  | File → Save As…                    | Save current capture file                                                                               |
| ![](h![](https://www.stationx.net/wp-content/uploads/2020/07/close.png)ttps://www.stationx.net/wp-content/uploads/2020/07/close.png) | **Close**                       | File →Close                        | Close current capture file                                                                              |
| ![reload](https://www.stationx.net/wp-content/uploads/2020/07/reload.png)                                                            | **Reload**                      | View → Reload                      | Reload current capture file                                                                             |
| ![find packet](https://www.stationx.net/wp-content/uploads/2020/07/find-packet.png)                                                  | **Find Packet...**              | Edit →Find Packet…                 | Find packet based on different criteria                                                                 |
| ![go back](https://www.stationx.net/wp-content/uploads/2020/07/go-back.png)                                                          | **Go Back**                     | Go → Go back                       | Jump back in the packet history                                                                         |
| ![go forwards](https://www.stationx.net/wp-content/uploads/2020/07/go-forwards.png)                                                  | **Go Forward**                  | Go → Go Forward                    | Jump forward in the packet history                                                                      |
| ![go to packet](https://www.stationx.net/wp-content/uploads/2020/07/go-to-packet.png)                                                | **Go to Packet...**             | Go → Go to Packet…                 | Go to specific packet                                                                                   |
| ![go to first packet](https://www.stationx.net/wp-content/uploads/2020/07/go-to-first-packet.png)                                    | **Go to First Packet**          | Go → Go to First Packet            | Jump to first packet of the capture file                                                                |
| ![go to last packet](https://www.stationx.net/wp-content/uploads/2020/07/go-to-last-packet.png)                                      | **Go to last Packet**           | Go → Go to last Packet             | Jump to last packet of the capture file                                                                 |
| ![](https://www.stationx.net/wp-content/uploads/2020/07/Auto-scroll.png)                                                             | **Auto Scroll in Live Capture** | View → Auto Scroll in Live Capture | Auto scroll packet list during live capture                                                             |
| ![colorize](https://www.stationx.net/wp-content/uploads/2020/07/colorize.png)                                                        | **Colorize**                    | View → Colorize                    | Colorize the packet list (or not)                                                                       |
| ![zoom in](https://www.stationx.net/wp-content/uploads/2020/07/zoom-in.png)                                                          | **Zoom In**                     | View → Zoom In                     | Zoom into the packet data (increase the font size)                                                      |
| ![zoom out](https://www.stationx.net/wp-content/uploads/2020/07/zoom-out.png)                                                        | **Zoom Out**                    | View → Zoom Out                    | Zoom out of the packet data (decrease the font size)                                                    |
| ![normal size](https://www.stationx.net/wp-content/uploads/2020/07/normal-size.png)                                                  | **Normal Size**                 | View → Normal Size                 | Set zoom level back to 100%                                                                             |
| ![resize column](https://www.stationx.net/wp-content/uploads/2020/07/resize-column.png)                                              | **Resize Columns**              | View → Resize Columns              | Resize columns, so the content fits the width                                                           |

# PcapPoisoning Writeup

## Challenge Description
The challenge name is PcapPoisoning and the description states "How about some hide and seek heh?"

## Solution
1. Download the `trace.pcap` file provided for the challenge.
2. Open the `trace.pcap` file in Wireshark, a widely-used network protocol analyzer.
3. Upon opening the file in Wireshark, it may appear overwhelming due to the amount of data available. Therefore, we need to filter the data to locate the flag. 
4. To filter the data, we use a display filter. In this case, we use the display filter `tcp contains "pico"`. This filter will only display the packets that contain the string "pico" in the TCP segment of the packet.
5. Once the filter is applied, we are able to see the flag in one of the packets. The flag for this challenge is `picoCTF{P64P_4N4L7S1S_SU55355FUL_31010c46}`.

## Flag
The flag for the PcapPoisoning challenge is `picoCTF{P64P_4N4L7S1S_SU55355FUL_31010c46}`.

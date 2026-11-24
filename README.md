# Packet Detective

## TryHackMe Wireshark Traffic Analysis

## My walkthrough

I opened each supplied capture and worked through it one question at a time. I used display filters to narrow the traffic, then checked packet details for context. These notes follow the screenshots from my room.

## I started with connection traffic

I began with TCP SYN requests, port eighty traffic, UDP packets and ICMP errors. Then I checked ARP requests and duplicate address warnings to understand how devices were appearing on the local network.

## I followed web activity

I filtered HTTP requests by host, address and method. I inspected form submissions, response data and exported objects. I also reviewed HTTP two traffic and TLS handshakes. The captures showed me how much unencrypted traffic can reveal and why HTTPS needs the matching session keys before its contents can be inspected.

## I checked host and service clues

I looked at DHCP, NetBIOS, DNS and Kerberos fields to connect device names with network activity. I used display filters to narrow the results and CyberChef to decode or safely defang values when needed.

## I reviewed file transfer traffic

I followed FTP logins, uploads, downloads, permission changes and failed requests. The packet details showed how plain text FTP can expose passwords and file activity.

## What I learned

I got better results by starting with one useful filter, inspecting the matching packet and following its related traffic. I learned to separate a useful clue from the surrounding noise and to treat exposed credentials carefully.

## My screenshots

<img src="1.png" alt="Screenshot 1" width="760">

<img src="2.png" alt="Screenshot 2" width="760">

<img src="3.png" alt="Screenshot 3" width="760">

<img src="4.png" alt="Screenshot 4" width="760">

<img src="5.png" alt="Screenshot 5" width="760">

<img src="6.png" alt="Screenshot 6" width="760">

<img src="7.png" alt="Screenshot 7" width="760">

<img src="8.png" alt="Screenshot 8" width="760">

<img src="9.png" alt="Screenshot 9" width="760">

<img src="10.png" alt="Screenshot 10" width="760">

<img src="11.png" alt="Screenshot 11" width="760">

<img src="12.png" alt="Screenshot 12" width="760">

<img src="13.png" alt="Screenshot 13" width="760">

<img src="14.png" alt="Screenshot 14" width="760">

<img src="15.png" alt="Screenshot 15" width="760">

<img src="16.png" alt="Screenshot 16" width="760">

<img src="17.png" alt="Screenshot 17" width="760">

<img src="18.png" alt="Screenshot 18" width="760">

<img src="19.png" alt="Screenshot 19" width="760">

<img src="20.png" alt="Screenshot 20" width="760">

<img src="21.png" alt="Screenshot 21" width="760">

<img src="22.png" alt="Screenshot 22" width="760">

<img src="23.png" alt="Screenshot 23" width="760">

<img src="24.png" alt="Screenshot 24" width="760">

<img src="25.png" alt="Screenshot 25" width="760">

<img src="26.png" alt="Screenshot 26" width="760">

<img src="27.png" alt="Screenshot 27" width="760">

<img src="28.png" alt="Screenshot 28" width="760">

<img src="29.png" alt="Screenshot 29" width="760">

<img src="30.png" alt="Screenshot 30" width="760">

<img src="31.png" alt="Screenshot 31" width="760">

<img src="32.png" alt="Screenshot 32" width="760">

<img src="34.png" alt="Screenshot 34" width="760">

<img src="35.png" alt="Screenshot 35" width="760">

<img src="36.png" alt="Screenshot 36" width="760">

<img src="37.png" alt="Screenshot 37" width="760">

<img src="38.png" alt="Screenshot 38" width="760">

<img src="39.png" alt="Screenshot 39" width="760">

<img src="40.png" alt="Screenshot 40" width="760">

<img src="41.png" alt="Screenshot 41" width="760">

<img src="42.png" alt="Screenshot 42" width="760">

<img src="43.png" alt="Screenshot 43" width="760">

<img src="44.png" alt="Screenshot 44" width="760">

<img src="45.png" alt="Screenshot 45" width="760">

<img src="46.png" alt="Screenshot 46" width="760">

<img src="47.png" alt="Screenshot 47" width="760">

<img src="48.png" alt="Screenshot 48" width="760">

<img src="49.png" alt="Screenshot 49" width="760">

<img src="50.png" alt="Screenshot 50" width="760">

<img src="51.png" alt="Screenshot 51" width="760">

<img src="52.png" alt="Screenshot 52" width="760">

<img src="53.png" alt="Screenshot 53" width="760">

<img src="54.png" alt="Screenshot 54" width="760">

<img src="55.png" alt="Screenshot 55" width="760">

<img src="56.png" alt="Screenshot 56" width="760">

## A final note
I used Snipping Tool so much that by the end it asked me for a packet break and a very long nap.

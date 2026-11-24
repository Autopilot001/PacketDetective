# Packet Detective

## TryHackMe Wireshark Traffic Analysis

The walkthrough follows the room from basic filters to deeper packet checks. Display filters narrow the traffic, then packet details help explain what each result means. Every screenshot has a short note describing the step shown.

The captures show how arp, dns, dhcp, netbios, kerberos, http, tls, icmp and ftp traffic reveal different parts of a network. Plain text protocols can expose account data, so private values are covered in the screenshots.

## Screenshot notes

Use a tcp syn filter to find the initial connection attempts.

<img src="1.png" alt="Screenshot 1" width="760">

Compare tcp port 80 handshakes with reset connections.

<img src="2.png" alt="Screenshot 2" width="760">

Filter icmp traffic to isolate destination unreachable errors.

<img src="3.png" alt="Screenshot 3" width="760">

Narrow udp traffic to ports 50 through 70 and review related network errors.

<img src="4.png" alt="Screenshot 4" width="760">

Inspect an arp duplicate address warning and its related device entry.

<img src="5.png" alt="Screenshot 5" width="760">

Review arp who has requests and broadcast address activity.

<img src="6.png" alt="Screenshot 6" width="760">

Combine http and ethernet address filters to focus the packet list.

<img src="7.png" alt="Screenshot 7" width="760">

Check a destination host filter and confirm that no packets match.

<img src="8.png" alt="Screenshot 8" width="760">

Filter http traffic by destination address to focus on matching responses.

<img src="9.png" alt="Screenshot 9" width="760">

Apply a host field as a display filter from the packet details.

<img src="10.png" alt="Screenshot 10" width="760">

Inspect the host header in a web request.

<img src="11.png" alt="Screenshot 11" width="760">

Combine host and post filters to narrow down form submissions.

<img src="12.png" alt="Screenshot 12" width="760">

Review a form submission with personal values covered.

<img src="13.png" alt="Screenshot 13" width="760">

Inspect login form fields with account values masked.

<img src="14.png" alt="Screenshot 14" width="760">

Check a comment form submission and its encoded fields.

<img src="15.png" alt="Screenshot 15" width="760">

Filter a dhcp request by device hostname while masking identifying details.

<img src="16.png" alt="Screenshot 16" width="760">

Use a netbios opcode filter to isolate registration packets.

<img src="17.png" alt="Screenshot 17" width="760">

Build a display filter that matches a netbios name.

<img src="18.png" alt="Screenshot 18" width="760">

Review netbios name registration traffic.

<img src="19.png" alt="Screenshot 19" width="760">

Filter a dhcp request by requested address and keep device details private.

<img src="20.png" alt="Screenshot 20" width="760">

Inspect dhcp options including the host name field with personal details covered.

<img src="21.png" alt="Screenshot 21" width="760">

Filter kerberos traffic by a client name.

<img src="22.png" alt="Screenshot 22" width="760">

Defang a private network address with cyberchef.

<img src="23.png" alt="Screenshot 23" width="760">

Inspect a kerberos ticket response and its principal fields.

<img src="24.png" alt="Screenshot 24" width="760">

Review the data inside an icmp echo request.

<img src="25.png" alt="Screenshot 25" width="760">

Use a data length filter to identify icmp tunnel traffic.

<img src="26.png" alt="Screenshot 26" width="760">

Inspect packet bytes containing secure shell algorithm names.

<img src="27.png" alt="Screenshot 27" width="760">

Filter dns queries by name length to find unusually long lookups.

<img src="28.png" alt="Screenshot 28" width="760">

Follow a dns response that contains a long canonical name.

<img src="29.png" alt="Screenshot 29" width="760">

Filter ftp responses to find failed login attempts.

<img src="30.png" alt="Screenshot 30" width="760">

Read an ftp size response to understand the returned file status.

<img src="31.png" alt="Screenshot 31" width="760">

Inspect an ftp retrieve command for a requested file.

<img src="32.png" alt="Screenshot 32" width="760">

Inspect an ftp store command used to upload a file.

<img src="34.png" alt="Screenshot 34" width="760">

Find an ftp permission change request.

<img src="35.png" alt="Screenshot 35" width="760">

Filter the capture by http user agent and compare browser requests.

<img src="36.png" alt="Screenshot 36" width="760">

Compare browser and scanning tool user agent entries.

<img src="37.png" alt="Screenshot 37" width="760">

Search http user agent values for unusual characters.

<img src="38.png" alt="Screenshot 38" width="760">

Review an LDAP style value in an http user agent while keeping the address masked.

<img src="39.png" alt="Screenshot 39" width="760">

Decode a base64 value and safely defang the address in the resulting command.

<img src="40.png" alt="Screenshot 40" width="760">

Filter tls client hellos and inspect the server name field.

<img src="41.png" alt="Screenshot 41" width="760">

Set a key log file in Wireshark to inspect eligible tls sessions.

<img src="42.png" alt="Screenshot 42" width="760">

Review the decrypted tls traffic after loading the session keys.

<img src="43.png" alt="Screenshot 43" width="760">

Confirm the same tls exchange in the decrypted capture view.

<img src="44.png" alt="Screenshot 44" width="760">

Inspect an HTTP two request header and its authority value.

<img src="45.png" alt="Screenshot 45" width="760">

Defang a safe browsing domain with cyberchef.

<img src="46.png" alt="Screenshot 46" width="760">

Export the HTTP object list and review the recovered files.

<img src="47.png" alt="Screenshot 47" width="760">

Inspect an HTTP response body that contains the room flag.

<img src="48.png" alt="Screenshot 48" width="760">

Open the Wireshark credentials tool from the tools menu.

<img src="49.png" alt="Screenshot 49" width="760">

Review credentials Wireshark extracted from the capture.

<img src="50.png" alt="Screenshot 50" width="760">

Compare ftp usernames found in the credential results.

<img src="51.png" alt="Screenshot 51" width="760">

Trace a selected ftp credential entry back to its packet.

<img src="52.png" alt="Screenshot 52" width="760">

Check ftp responses after a login attempt.

<img src="53.png" alt="Screenshot 53" width="760">

Filter ftp password commands to review the request sequence.

<img src="54.png" alt="Screenshot 54" width="760">

Review firewall deny rules for inbound traffic.

<img src="55.png" alt="Screenshot 55" width="760">

Review firewall allow rules and their matching address and port entries.

<img src="56.png" alt="Screenshot 56" width="760">

## What stood out

The most useful approach was to start with one filter, inspect a matching packet, then follow the related traffic. The captures also showed why exposed credentials need careful handling and why tls decryption depends on the matching session keys.

## A final note

Snipping Tool saw so many packets that by the end it asked for a packet break and a very long nap.

# Packet Detective

## TryHackMe Wireshark Traffic Analysis

The walkthrough follows the room from basic filters to deeper packet checks. Display filters narrow the traffic, then packet details help explain what each result means. Screenshots are stored in the screenshots folder and each note describes the step shown

The captures show how arp, dns, dhcp, netbios, kerberos, http, tls, icmp and ftp traffic reveal different parts of a network. Plain text protocols can expose account data, so private values are covered in the screenshots.

## Screenshot notes

Initiated the review with a tcp syn filter to find the first connection attempts.


Compared tcp port 80 handshakes with reset connections.


Filtered icmp traffic to isolate destination unreachable errors.


Narrowed udp traffic to ports 50 through 70 and reviewed related network errors.


Inspected an arp duplicate address warning and its related device entry.


Reviewed arp who has requests and broadcast address activity.


Combined http and ethernet address filters to focus the packet list.


Checked a destination host filter and confirmed that no packets matched.


Filtered http traffic by destination address to focus on matching responses.


Applied a host field as a display filter from the packet details.


Inspected the host header in a web request.


Combined host and post filters to narrow down form submissions.


Reviewed a form submission with personal values covered.


Inspected login form fields with account values masked.


Checked a comment form submission and its encoded fields.


Filtered a dhcp request by device hostname while masking identifying details.


Used a netbios opcode filter to isolate registration packets.


Built a display filter that matched a netbios name.


Reviewed netbios name registration traffic.


Filtered a dhcp request by requested address and kept device details private.


Inspected dhcp options including the host name field with personal details covered.


Filtered kerberos traffic by a client name.


Defanged a private network address with cyberchef.


Inspected a kerberos ticket response and its principal fields.


Reviewed the data inside an icmp echo request.


Used a data length filter to identify icmp tunnel traffic.


Inspected packet bytes containing secure shell algorithm names.


Filtered dns queries by name length to find unusually long lookups.


Followed a dns response that contained a long canonical name.


Filtered ftp responses to find failed login attempts.


Read an ftp size response to understand the returned file status.


Inspected an ftp retrieve command for a requested file.


Inspected an ftp store command used to upload a file.


Found an ftp permission change request.


Filtered the capture by http user agent and compared browser requests.


Compared browser and scanning tool user agent entries.


Searched http user agent values for unusual characters.


Reviewed an ldap style value in an http user agent while keeping the address masked.


Decoded a base64 value and safely defanged the address in the resulting command.


Filtered tls client hellos and inspected the server name field.


Configured a key log file in Wireshark to inspect eligible tls sessions.


Reviewed the decrypted tls traffic after loading the session keys.


Confirmed the same tls exchange in the decrypted capture view.


Inspected an http two request header and its authority value.


Defanged a safe browsing domain with cyberchef.


Exported the HTTP object list and reviewed the recovered files.


Inspected an http response body that contained the room flag.


Opened the Wireshark credentials tool from the tools menu.


Reviewed credentials Wireshark extracted from the capture.


Compared ftp usernames found in the credential results.


Traced a selected ftp credential entry back to its packet.


Checked ftp responses after a login attempt.


Filtered ftp password commands to review the request sequence.


Reviewed firewall deny rules for inbound traffic.


Reviewed firewall allow rules and their matching address and port entries.


## Findings

Also, plain text ftp exposed login attempts and file activity. One failed login returned a 530 response. That was a useful clue!

On the other hand, a filter for the wrong destination returned no packets. The empty result was a reminder to check the host before drawing a conclusion.

Did the HTTP response contain the room flag? It did!

The tls traffic became readable after the matching key log file was loaded. Filters for dns and netbios also helped connect traffic with host names.

## A final note

Snipping Tool saw so many packets that by the end it asked for a packet break and a very long nap.

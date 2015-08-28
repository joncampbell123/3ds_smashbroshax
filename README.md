This is haxx for Super Smash Bros for 3DS, via local-WLAN beacon haxx. The haxx triggers while the application is scanning for local multiplayer sessions, when the beacon is being broadcasted.
In certain cases the application may somewhat hang instead of crashing. Note that in certain cases the haxx may take longer to trigger with the full-game than the demo.

Remember to always broadcast the beacon on the same channel as specified in the beacon itself.

This supports regular 3DS. On New3DS the moved stack gets corrupted, hence this haxx doesn't work right on New3DS.

Supported application builds:
* demo: USA+EUR supported and tested.
* v1.0.0. USA: supported+tested.
* v1.0.2. USA: supported, not tested.
* v1.0.4. USA: supported+tested. "gameother": supported, not tested.
* v1.0.5. USA: "supported". The target heap address for overwriting the target object varies, hence this hax doesn't actually work right with this version(this might not matter?).

Last version tested with this vuln was v1.1.0, vuln still isn't fixed with that version.

EUR and JPN full-game .code binaries addresses-wise are basically the same, for v1.0.4 at least. Hence, the filenames for these two regions include "gameother".

ctr-wlanbeacontool from here is required: https://github.com/yellows8/ctr-wlanbeacontool

One way to send the beacon is with aireplay-ng, however that requires a patch, see aireplay-ng.patch. For example, to send the beacon with aireplay-ng: aireplay-ng --interactive -r {beaconpcap_path} -h {host mac from pcap} -x 10 {wifi interface}

Note that the smashbrosfullgame_beaconseqX.pcap beacons aren't actually needed.
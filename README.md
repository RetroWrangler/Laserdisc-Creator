# Laserdisc-Creator
A script that takes any uncompressed video source and applies visuals that make it look like laserdiscs

LaserDisc-Style DVD Pipeline (FFmpeg → TMPGEnc → Pioneer DVL-919)

Give modern sources a convincing LaserDisc vibe — fine analog-style grain, a touch of extra color, and subtle chroma misalignment — then author high-bitrate, DVD-spec discs that play nicely on picky late-’90s hardware like the Pioneer DVL-919.

What you get
	•	Analog-style grain (time-varying, non-blocky)
	•	Slight color boost for LD punch
	•	Subtle chroma shift to mimic LD color handling
	•	Ready-to-author DVD streams or uncompressed/lossless intermediates
	•	Optional 45-minute splits to emulate LD “sides”

⸻

🔧 Requirements
	•	FFmpeg (recent build in your PATH)
	•	(Optional) TMPGEnc Authoring Works for DVD authoring
	•	(Optional) VirtualDub2 if you want a GUI route (not required here)

⸻

🎛 “LaserDisc Look” filter stack

These FFmpeg filters are applied in the examples below:
	•	noise=alls=10:allf=t+u → fine, time-varying grain
	•	eq=saturation=1.04 → +4% saturation (tweak to taste)
	•	chromashift=1:0 → shift chroma +1 px horizontally (subtle LD-like bleed)

⸻

🚀 Quick start — DVD-ready (NTSC 16:9, soft-telecine for film)

Encode directly to a DVD-compliant stream with 3:2 pulldown flags (smooth film cadence, no duplicated frames spam).
For 16:9 anamorphic DVDs use setsar=8/9. For 4:3, use setsar=10/11.

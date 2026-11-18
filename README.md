NFSplit 0.1.0 — split-screen for Need for Speed: Most Wanted (2012)
=======================================================================

WHAT THIS IS
------------
Runs two copies of NFS13.exe on one PC, side by side or stacked, each with
its own controller or keyboard, joined through a local server.

No game files are modified. NFSplit adds two proxy DLLs that the game loads
from its own folder, plus this launcher folder.

REQUIREMENTS
------------
- Your own legitimate PC copy of Need for Speed: Most Wanted (2012),
  version 1.5.0.0 (NFS13.exe). Tested build sha256:
     9571280bb8868cd254e95442181d7bf1d6eafb2156a95d0c38337c7470762c0f
  Other versions may work but are untested; the launcher warns and asks.
- Windows 10 or 11, 64-bit.
- Two input devices, for example:
    * an Xbox/XInput controller and a keyboard, or
    * an Xbox controller and a DualShock 4 (DS4), or
    * two controllers in XInput mode.
- No internet connection is needed or used.

INSTALL
-------
1. Find the game folder: the one containing NFS13.exe
   (for example ...\Need for Speed Most Wanted\ or your Origin/EA App
   install folder).
2. Unzip this archive INTO that folder, keeping the folder structure.
   You get:
       NFS13.exe                 (already there, untouched)
       xinput1_3.dll             (added)
       dinput8.dll               (added)
       NFSplit\                  (added: launcher, servers, docs)
   If Windows asks to replace an existing xinput1_3.dll or dinput8.dll,
   say yes (the game does not ship those files; older NFSplit builds did).
3. Start NFSplit\NFSplit.exe.

USAGE
-----
1. Turn the controller(s) on. For a DualShock 4, press the PS button, then
   click "Turn on DS4" if the launcher does not list it.
2. Pick the layout (side by side / stacked).
3. Player 1 / Player 2 pad menus: Auto assigns one device per window; you
   can pin a specific pad or "None (keyboard only)".
4. Start Servers, then Launch 2 Games.

Each window accepts its own player's input at the same time; you do not
need to click a window to give it "focus". Keyboard keys pressed for the
keyboard player do not steer the controller player's car.

CONTROLS
--------
- XInput pads: the game's built-in Xbox 360 bindings are used as-is.
- DualShock 4: bridged to an Xbox pad, so the game's default Xbox bindings
  apply with no in-game setup. Square -> X, Cross -> A, Circle -> B,
  Triangle -> Y, L1/R1 -> LB/RB, Share -> BACK, Options -> START,
  L3/R3 -> stick clicks, dpad = dpad, left/right stick as usual.
- Keyboard: the game's default keyboard bindings.

TROUBLESHOOTING
---------------
- Windows SmartScreen / antivirus: the launcher and proxy DLLs are unsigned
  and built for this project, so you may need "More info -> Run anyway" and
  an antivirus exclusion for the game folder. The proxies only redirect the
  game's own traffic to 127.0.0.1 and adjust input handling in memory.
- Nothing happens / one window ignores input: make sure both windows were
  started by the launcher, and check NFSplit\logs\ for error lines.
- A controller shows as "not detected": turn it on, then "Refresh pads" or
  "Turn on DS4".
- Game version warning: only 1.5.0.0 is tested.
- Kill switch: click STOP EVERYTHING, or create an empty file named
  couchlink.off in the game folder. Delete it to re-enable.
- Logs are written to NFSplit\logs\. They are plain text and stay on your PC.

UNINSTALL
---------
Delete from the game folder:
    xinput1_3.dll
    dinput8.dll
    NFSplit\
Nothing is written to the registry and the game's own files/saves are not
changed. (If the game later fails to start on another machine, make sure
those two DLLs are not left behind.)

LEGAL AND PRIVACY
-----------------
- This package contains no game files, game assets or EA code. You must own
  the game. It is not a crack and does not bypass DRM, licensing or
  entitlement checks.
- All network traffic stays on 127.0.0.1 (your own PC). NFSplit never
  contacts, probes or interferes with EA's servers.
- The local TLS certificate in NFSplit\certs\ was generated for this
  project; it is only used by the local server.
- The proxy DLLs redirect the game's own server lookups to the local server
  in memory (NFS13.exe on disk is unchanged), bridge controllers, and keep
  both windows active at once.

SOURCE / SUPPORT
----------------
NFSplit is a personal local-co-op project. No warranty; use at your own
risk with your own copy of the game.

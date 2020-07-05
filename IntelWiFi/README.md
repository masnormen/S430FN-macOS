#IntelWifi plugin for ASUS S430FN

## How to use

1. Drag HeliPort.app to Applications folder
2. Go to terminal and do `sudo chown -R root:wheel itlwm.kext` on this directory
3. Run `sudo kextload -v itlwm.kext`
4. After successful kext load, run HeliPort
5. Enjoy!

Be careful on enabling and disabling itlwm. Save all your work first because sometimes it can cause system freeze and kernel panic! (Of course, because this driver is still on heavy development)
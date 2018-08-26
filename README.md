These are configs, wine prefixes, and binaries nessesary to run C&C 95 (Gold Edition) under wine, with additional configs to make it run well under i3wm.

The general idea is to install C&C 95 (http://nyerguds.arsaneus-design.com/cnc95upd/cc95p106/) in wine and run it in a nested X session, which should resolve some of the limited and tempermental graphics rendering issues. The end result works well and doesn't require any winecfg or heavy CCConfig tweaks.

It also works well under Valve's Proton!

C&C 95 Quirks

CnC-DDraw doesn't seem to work properly and causes the game to hang quite frequently, so I disable it. 


i3wm Quirks

Probably to i3wm not being a compositing WM, the game screen window will typically go black and refuse to redraw properly, if the host switches application focus or modifies the resolution. The best solution I've found for this is to create a nested X session with Xephyr (xnest should work as well), and run wine within that. This way you should be able to move and manipulate the game window around as much as you'd like, and it should keep rendering normally.

If you seem to keep running into rendering issues due to compositing, and you do not want to run a nested X session, I've found some positive behavior enabling "Emulate a virtual desktop" under the "Graphics" tab in winecfg.
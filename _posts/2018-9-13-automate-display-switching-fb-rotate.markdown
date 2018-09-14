---
layout: post
title: "Automate your display-switching with fb-rotate"
---

I do a lot of technical screensharing sessions, and showing off the strange assortment of files and mysterious folders that live on my desktop is non-ideal.

Some searching revealed two command-line tools that can switch the primary display for users of multiple displays—"primary" in this case meaning, the one that shows my desktop directory structure.

The first, [cscreen](http://pyehouse.com/cscreen), was developed by Pyhouse back in the PowerPC Mac days; however, it has been updated occasionally and still works quite well on new Intel Macs. The following command is all you need to switch your primary display:

```cscreen -i $DISPLAY_ID -p```

However, for whatever reason, `cscreen` has the unfortunate side-effect of also switching your display _arrangement_, i.e., if your secondary monitor is on your right, after the switch, you will have to scroll off the right edge of the secondary monitory (which now houses your "primary display") to reach your primary monitor (now housing your "secondary display").

This is, unfortunately, a deal-breaker for me, as I need something I can quickly run before starting a screensharing session, and then quickly run after it ends so I can get back to my normal workflow.

The second, [fb-rotate](https://github.com/CdLbB/fb-rotate), is under even less active development, but still seems to work just fine. Its syntax is a bit less clear; however, it seems to run more quickly, and has no side effects to speak of. The equivalent switching command is as follows:

```fb-rotate -d $DISPLAY_ID -m```

I've taken this a step further and written two very simple AppleScripts, containing the identical command but one with my primary display ID and the other with my seocondary display ID:

```do shell script "/usr/local/bin/fb-rotate -d $DISPLAY_ID -m"```

I can now almost instantaneously switch my displays from my menu bar—mission accomplished!
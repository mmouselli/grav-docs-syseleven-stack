---
title: 'LoadBalancer as a Service'
published: true
date: '08-08-2018 11:40'
taxonomy:
    category:
        - docu
---

Der SysEleven Stack LBaaS ist ein einfacher TCP-basierter Lastverteiler. Er verteilt Anfragen nach dem Round-Robin Prinzip (der Reihe nach).
Ebenfalls ist ein einfacher Health-Check nutzbar.

Leider kann die Client-IP zur Zeit nicht an die Systeme hinter dem LBaaS durchgereicht werden. Die IP des Lastverteilers wird als Ausgangsadresse angezeigt.

Wir haben ein Tutorial zur [Nutzung des LBaaS](/tutorials/lbaas/) vorbereitet.
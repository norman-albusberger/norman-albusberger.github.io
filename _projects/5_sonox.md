---
layout: page
title: SonoX
description: Von Open Source zum Hardware-Produkt, Sonos-Integration für Loxone als Plugin und als Audio-Server-Appliance
img: assets/img/projects/sonox.svg
importance: 1
category: Product Engineering
---

**Problem.** Sonos-Lautsprecher (insbesondere die S1-Generation) lassen sich nicht ohne Weiteres in professionelle Gebäudeautomation wie Loxone einbinden: Playback, Gruppen, Ansagen und Events fehlen als steuerbare Schnittstelle, und cloudbasierte Umwege sind im professionellen Einsatz unerwünscht.

**Architektur & Innovation.** SonoX begann als Open-Source-Loxberry-Plugin, das Sonos nahtlos mit Loxone verbindet: Playback- und Lautstärkesteuerung, raumübergreifende Gruppen, Text-to-Speech-Ansagen, Audio-Clips und eine ereignisorientierte Integration über MQTT. Daraus ist mit dem **Sonox Audio Server** ein eigenständiges Hardware-Produkt entstanden: eine hutschienenmontierbare (DIN-Rail) Appliance, die Sonos vollständig lokal ohne Cloud-Bridge an Loxone anbindet, inklusive KI-gestützter Sprachansagen (ElevenLabs), Sound-Bibliothek und vorkonfigurierter Loxone-Integration.

**Business Impact.** Der Weg vom Open-Source-Projekt zum kommerziellen Produkt: Der Sonox Audio Server (sonox.net) richtet sich an Loxone-Integratoren, Elektrofachbetriebe und gewerbliche Umgebungen wie Hotels, Büros und Praxen. Öffentlich distribuiert und mit realer Nutzerbasis.

**Technologien:** Node.js, MQTT, Text-to-Speech (ElevenLabs), REST, Loxberry, DIN-Rail-Hardware-Appliance.

[Zum Produkt: sonox.net](https://sonox.net/){:target="_blank"} · [Open-Source-Repository](https://github.com/norman-albusberger/sonox){:target="_blank"}

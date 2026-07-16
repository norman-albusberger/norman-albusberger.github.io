---
layout: page
title: SonoX
description: Sonos-Integration für das Loxone-Smart-Home — als öffentlich distribuiertes Plugin
img: assets/img/projects/sonox.svg
importance: 2
category: Product Engineering
---

**Problem.** Sonos-Lautsprecher (insbesondere die S1-Generation) lassen sich nicht ohne Weiteres in professionelle Smart-Home-Systeme wie Loxone einbinden — Playback, Gruppen, Ansagen und Events fehlen als steuerbare Schnittstelle.

**Architektur & Innovation.** SonoX ist ein **Loxberry-Plugin**, das Sonos nahtlos mit Loxone verbindet: Playback- und Lautstärkesteuerung, raumübergreifende Gruppen, **Text-to-Speech-Ansagen**, Audio-Clips für Alarme/Türklingel und eine Web-Oberfläche zum Testen und Kopieren von Loxone-URLs. Sonos-Events werden auf **MQTT-Topics** publiziert und damit für die weitere Heim-Automatisierung nutzbar — eine saubere, ereignisorientierte Integrationsschicht auf Node.js.

**Business Impact.** **Öffentlich über den Loxberry-Plugin-Store distribuiert** und von einer realen Community genutzt — kein Prototyp, sondern ein gepflegtes Produkt mit Nutzerbasis.

**Warum das für einen Technology Executive zählt.** Produktdenken über den reinen Code hinaus: Ökosystem-Integration, Distribution, Dokumentation und Betrieb eines Open-Source-Produkts mit echten Anwendern — Platform- und Product-Ownership im Kleinen.

**Technologien:** Node.js, MQTT, Text-to-Speech, REST, Loxberry.

[🔗 Zum Repository](https://github.com/norman-albusberger/sonox){:target="_blank"}

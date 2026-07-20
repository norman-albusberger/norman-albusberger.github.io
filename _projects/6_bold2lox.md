---
layout: page
title: bold2lox
description: Sichere Anbindung einer proprietären Cloud-API an die Gebäudeautomation, mit Fokus auf Betriebsfestigkeit
img: assets/img/projects/bold2lox.svg
importance: 3
category: Product Engineering
---

**Problem.** Ein Bold Smart Lock lässt sich ausschließlich über die Hersteller-App und deren Cloud auslösen; eine offene Schnittstelle für die Gebäudeautomation gibt es nicht. Ältere Loxone Miniserver der ersten Generation beherrschen zudem kein TLS und können eine solche Cloud gar nicht direkt ansprechen.

**Architektur.** bold2lox setzt einen LoxBerry als Vermittler dazwischen. Der Miniserver sendet nur einen einfachen lokalen HTTP-Aufruf; die eigentliche TLS- und OAuth2-Kommunikation mit der Hersteller-Cloud übernimmt das Plugin, das den Befehl an die Bridge im Haus weiterreicht. Ein systemd-Dienst meldet den Zustand per UDP an den Miniserver zurück, sodass der Schaltzustand auch in der Loxone-App sichtbar wird.

**Authentifizierung und Nebenläufigkeit.** Die Anbindung nutzt den OAuth2-Authorization-Code-Flow mit automatischer Erneuerung des kurzlebigen Access-Tokens, sodass die Einrichtung einmalig bleibt. Da der Anbieter Refresh-Tokens bei jeder Erneuerung rotiert, entwerten konkurrierende Erneuerungen sonst gegenseitig die Sitzung. Gelöst über eine exklusive Dateisperre: Erneuerungen lesen den Stand innerhalb der Sperre neu und übernehmen ein frisch geholtes Token. Gegen einen rotationsstrengen Mock mit parallelen Prozessen verifiziert.

**Betriebsfestigkeit.** Der LoxBerry-Installer löscht bei jedem Update das komplette Datenverzeichnis eines Plugins, eine mitgelieferte Standarddatei genügt also nicht. bold2lox sichert die Konfiguration vor dem Update außerhalb des betroffenen Pfades, stellt sie danach wieder her und ergänzt neu hinzugekommene Standardwerte, ohne bestehende Werte zu überschreiben. Lässt sich die Sicherung nicht schreiben, bricht das Update ab, statt die Einrichtung zu verlieren.

**Technologien:** Python, PHP, OAuth2, systemd, REST, UDP, LoxBerry.

[Repository ansehen](https://github.com/norman-albusberger/bold2lox){:target="_blank"}

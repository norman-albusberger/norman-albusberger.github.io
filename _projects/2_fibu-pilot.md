---
layout: page
title: FiBu-Pilot
description: KI-gestützte, lokal laufende Automation der Buchhaltungsvorbereitung bis zum DATEV-Export
img: assets/img/projects/fibu-pilot.svg
importance: 2
category: Artificial Intelligence
---

**Problem.** Die Vorbereitung der Buchhaltung — Belege sammeln, Zahlungen zuordnen, steuerlich klassifizieren, exportieren — kostet im Mittelstand und E-Commerce enorm viel manuelle Zeit. Cloud-Buchhaltungstools scheiden aus, wo Belegdaten das eigene System nicht verlassen sollen.

**Architektur & Innovation.** FiBu-Pilot verarbeitet Rechnungen, Kontoauszüge und Payment-Exporte (PayPal, Stripe) — PDF mit OCR-Fallback, Bild, CSV — und extrahiert Felder heuristisch. Ein **Matching-Algorithmus** bewertet offene Rechnungen gegen unzugeordnete Zahlungen über Referenz, Betrag, Datum und Zahlweg, inklusive Provider-Filter und Erstattungslogik. **Lernende Lieferantenprofile** erkennen Partner über USt-ID, IBAN, E-Mail-Domain und Aliase — manuelle Korrekturen fließen in künftige Importe ein. Steuerliche Klassifizierung (Reverse-Charge, innergemeinschaftlich, nicht steuerbar) und ein **DATEV-Buchungsstapel (SKR03/04)** bilden den Abschluss. Sauber geschnitten in Domain-Modelle, Service-Layer und Qt-UI.

**Business Impact.** Vollständig local-first (Python, SQLite, Tesseract) — bereits **produktiv im realen E-Commerce-Buchhaltungsbetrieb** im Einsatz. Reduziert manuelle Zuordnungsarbeit drastisch, ohne Datenschutz aufzugeben.

**Warum das für einen Technology Executive zählt.** Ich verbinde hier Domänenverständnis (Steuer/Buchhaltung), pragmatische KI/Heuristik und saubere Softwarearchitektur zu einem Produkt, das echten Geschäftsnutzen liefert — genau die Business-zu-Technologie-Übersetzung, die einen CTO ausmacht.

**Technologien:** Python 3.11, PyQt, SQLite, Tesseract OCR, Domain-Driven Design.

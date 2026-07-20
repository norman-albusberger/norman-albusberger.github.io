---
layout: page
title: SUSA · Immobilien-Analyse
description: Steuer- und Cashflow-Analyse für Vermietungsimmobilien als moderne Desktop-App
img: assets/img/projects/susa.svg
importance: 2
category: Product Engineering
---

**Problem.** Die steuerliche und wirtschaftliche Bewertung von Vermietungsimmobilien ist komplex: Einkünfte nach § 21 EStG, Einkommensteuer inkl. Splitting, Soli-Milderungszone, Cashflow vor und nach Steuern, Verlustvortrag. Tabellenkalkulationen sind fehleranfällig und intransparent.

**Architektur & Innovation.** SUSA rechnet all das interaktiv und visualisiert per Sensitivitätsdiagramm drei Break-even-Punkte über die Mietspanne. Die Rechenlogik ist als reine, UI-freie TypeScript-Funktionen implementiert und mit 27 Unit-Tests gegen offizielle Steuertabellen abgesichert. Ausgeliefert als plattformübergreifende Desktop-App auf Basis von Tauri statt Electron, wodurch das Installer-Bundle von rund 150 MB auf rund 3 MB schrumpft.

**Business Impact.** Verwandelt eine fehleranfällige Excel-Aufgabe in ein verlässliches, testgestütztes Werkzeug für fundierte Investitionsentscheidungen.

**Technologien:** React 19, TypeScript, Vite, Tailwind CSS, Chart.js, Tauri 2 (Rust), Vitest.

[Repository ansehen](https://github.com/norman-albusberger/immobilien-rechner){:target="_blank"}

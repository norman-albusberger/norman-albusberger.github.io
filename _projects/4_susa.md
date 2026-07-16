---
layout: page
title: SUSA — Immobilien-Analyse
description: Steuer- und Cashflow-Analyse für Vermietungsimmobilien als moderne Desktop-App
img: assets/img/projects/susa.svg
importance: 1
category: Product Engineering
---

**Problem.** Die steuerliche und wirtschaftliche Bewertung von Vermietungsimmobilien ist komplex — Einkünfte nach § 21 EStG, Einkommensteuer inkl. Splitting, Soli-Milderungszone, Cashflow vor/nach Steuern, Verlustvortrag. Tabellenkalkulationen sind fehleranfällig und intransparent.

**Architektur & Innovation.** SUSA rechnet all das interaktiv und visualisiert per Sensitivitätsdiagramm drei Break-even-Punkte über die Mietspanne. Die **Rechenlogik ist als reine, UI-freie TypeScript-Funktionen** implementiert und mit **27 Unit-Tests gegen offizielle Steuertabellen** abgesichert. Ausgeliefert als plattformübergreifende Desktop-App — bewusste Architektur­entscheidung für **Tauri statt Electron**: das Installer-Bundle schrumpft von ~150 MB auf ~3 MB.

**Business Impact.** Verwandelt eine fehleranfällige Excel-Aufgabe in ein verlässliches, testgestütztes Werkzeug für fundierte Investitionsentscheidungen.

**Warum das für einen Technology Executive zählt.** Zeigt **Architektur-Urteilsvermögen** (Tauri vs. Electron, Trennung von Logik und UI), **Qualitätsdisziplin** (Testabdeckung gegen offizielle Referenzen) und moderne Product-Engineering-Standards.

**Technologien:** React 19, TypeScript, Vite, Tailwind CSS, Chart.js, Tauri 2 (Rust), Vitest.

[🔗 Zum Repository](https://github.com/norman-albusberger/immobilien-rechner){:target="_blank"}

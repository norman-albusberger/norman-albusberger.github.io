---
layout: page
title: FaceStream.AI
description: Real-time Face Recognition in Live Video — selbst-hostbare Computer-Vision-Plattform mit Anti-Spoofing
img: assets/img/projects/facestream.svg
importance: 1
category: Artificial Intelligence
---

**Problem.** Gesichtserkennung in Live-Videoströmen ist rechenintensiv, latenzkritisch und — sobald sie sicherheitsrelevant wird — anfällig für Täuschung (Fotos, Videos, Masken). Cloud-Dienste scheiden aus, wenn Daten das eigene Netz nicht verlassen dürfen.

**Architektur & Innovation.** FaceStream.AI erkennt Gesichter in Echtzeit und liefert einen annotierten Videostream. Der Kern ist eine dockerisierte, konsequent mit Threading parallelisierte Pipeline: hochperformante Face-Detection (RetinaFace), Recognition und eine **Silent-Face-Anti-Spoofing/Liveness-Stufe**, ergänzt um Event-Log mit gespeicherten Treffern und einen konfigurierbaren **UDP/HTTP-Notification-Service** zur Integration in Fremdsysteme. Das Erkennungsintervall ist einstellbar — bewusstes Trade-off-Design zwischen Genauigkeit und Ressourcenverbrauch.

**Business Impact.** Leichtgewichtig, edge-deploybar und vollständig self-hosted — nutzbar für Zutritt, Sicherheit und Automatisierung, ohne personenbezogene Daten in die Cloud zu geben.

**Warum das für einen Technology Executive zählt.** Das Projekt zeigt, dass ich KI-Systeme nicht nur beauftrage, sondern **selbst architektiere**: Modellauswahl, Latenz- und Ressourcen-Trade-offs, Event-getriebene Integration und produktionsnahe Bereitstellung.

**Technologien:** Python, Docker, RetinaFace, Silent-Face-Anti-Spoofing, Multithreading, HTTP/UDP-Notifications.

[🔗 Zum Repository](https://github.com/norman-albusberger/FaceStream.AI){:target="_blank"}

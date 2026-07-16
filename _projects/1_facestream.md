---
layout: page
title: FaceStream.AI
description: Real-time Face Recognition in Live Video, selbst-hostbare Computer-Vision-Plattform mit Anti-Spoofing
img: assets/img/projects/facestream.svg
importance: 1
category: Artificial Intelligence
---

**Problem.** Gesichtserkennung in Live-Videoströmen ist rechenintensiv, latenzkritisch und, sobald sie sicherheitsrelevant wird, anfällig für Täuschung (Fotos, Videos, Masken). Cloud-Dienste scheiden aus, wenn Daten das eigene Netz nicht verlassen dürfen.

**Architektur & Innovation.** FaceStream.AI erkennt Gesichter in Echtzeit und liefert einen annotierten Videostream. Der Kern ist eine dockerisierte, konsequent mit Threading parallelisierte Pipeline: hochperformante Face-Detection (RetinaFace), Recognition und eine Silent-Face-Anti-Spoofing/Liveness-Stufe, ergänzt um einen Event-Log mit gespeicherten Treffern und einen konfigurierbaren UDP/HTTP-Notification-Service zur Integration in Fremdsysteme. Das Erkennungsintervall ist einstellbar, ein bewusstes Trade-off zwischen Genauigkeit und Ressourcenverbrauch.

**Business Impact.** Leichtgewichtig, edge-deploybar und vollständig self-hosted, nutzbar für Zutritt, Sicherheit und Automatisierung, ohne personenbezogene Daten in die Cloud zu geben.

**Technologien:** Python, Docker, RetinaFace, Silent-Face-Anti-Spoofing, Multithreading, HTTP/UDP-Notifications.

[Repository ansehen](https://github.com/norman-albusberger/FaceStream.AI){:target="_blank"}

---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# Anleitung

**Hinweis: Diese Seite (oder eine beliebige Seite &quot;Bitte lesen&quot;) wird nicht in der Kundendokumentation veröffentlicht**

## Inhaltsverzeichnis

+ `TOC.md` im Stammverzeichnis des Benutzerhandbuchs finden Sie die Organisation der Themen, die im Handbuch für diese Lösung enthalten sind.
+ Jedes Benutzerhandbuch hat seine eigene eindeutige `TOC.md`, in der Sie alle Seiten/Themen nach Bedarf bestellen können.
+ Die erste Seite aller Benutzerhandbücher ist `overview.md`.

## Benutzerhandbuch

+ Die Einführung in das Benutzerhandbuch heißt `overview.md`
+ Jedes Thema im Benutzerhandbuch hat einen eigenen Ordner.
   + Wenn ein Thema im Handbuch *Implementierung* aufgeführt ist, ist der entsprechende Ordner `/implementation`
+ Alle Bild-Assets werden in `/assets` im Stammverzeichnis des Benutzerhandbuchs gespeichert.
   + Alle Bilder im Ordner `/assets` werden lokalisiert.
   + Bilder im Ordner `/no-localize` werden nicht lokalisiert (es gibt eine Überraschung!). Auf diese Weise kann sichergestellt werden, dass bestimmte Assets in lokalen Versionen nicht unnötig reproduziert werden.

## Metrikdaten auf Benutzerhandbuchebene

+ Metadaten, die das Benutzerhandbuch beschreiben, werden im Ordner `TOC.md` gespeichert. Dazu gehören:
   + product - Name des Produkts/der Funktion.
   + Cloud - Cloud, zu der dieses Produkt gehört.
   + audience - Audience oder Archetyp, auf den der Guide abzielt.
   + user-guide - Name des Benutzerhandbuchs.

## Metadaten auf Seitenniveau

+ Metadaten, die zur Beschreibung eines Dokuments erforderlich sind, werden als Teil jeder einzelnen Seite gespeichert. Dazu gehören:
   + title - Titel der Seite.
   + description - Beschreibung der Seite.
   + seo-title - seo alternative title.
   + seo-description - alternativer Titel für SEO Zwecke.
   + short-title - (optionales Feld).
   + index - ja/nein - wird die Seite nach der Suchplattform der Adobe indiziert.
   + translate - ja / nein - wird diese Seite lokalisiert.
   + version - wird hauptsächlich für AEM und Kampagne verwendet, um die Produktversion zu kennzeichnen.
   + private-feature-pack - wird primär für AEM verwendet.
   + beta - ist dieses Produkt in der Beta?
   + redirect - kann verwendet werden, um eine Referenz zu einer neuen Seite zu erstellen, falls dies erforderlich ist.
   + doc-type: reference (Standard) / troubleshooting / developer / tutorial / kb / whitepaper.

## Weitere Informationen

Weitere Veröffentlichungsanweisungen, Stilhandbücher, Beispiele und andere Ressourcen finden Sie im Bericht [Kooperative Dokumentation](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)

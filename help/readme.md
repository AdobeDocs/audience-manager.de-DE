---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Anleitung

**Hinweis: Diese Seite (oder eine beliebige Seite "Bitte lesen") wird nicht in der Kundendokumentation veröffentlicht**

## Inhaltsverzeichnis

+ `TOC.md` im Stammverzeichnis des Benutzerhandbuchs finden Sie die Organisation der Themen, die im Handbuch für diese Lösung enthalten sind.
+ Jedes Benutzerhandbuch verfügt über eine eigene, einzigartige Benutzeroberfläche `TOC.md`und kann bei Bedarf alle Seiten/Themen bestellen.
+ Die erste Seite aller Benutzerhandbücher ist `overview.md`.

## Benutzerhandbuch

+ Die Einführung in das Benutzerhandbuch heißt `overview.md`
+ Jedes Thema im Benutzerhandbuch hat einen eigenen Ordner.
   + Wenn ein Thema im Handbuch *Implementierung* aufgeführt ist, ist der entsprechende Ordner `/implementation`
+ Alle Bild-Assets werden im Stammverzeichnis `/assets` des Benutzerhandbuchs gespeichert.
   + Alle Bilder im `/assets` Ordner werden lokalisiert.
   + Alle Bilder im `/no-localize` Verzeichnis werden nicht lokalisiert (es gibt eine Überraschung!). Auf diese Weise kann sichergestellt werden, dass bestimmte Assets in lokalen Versionen nicht unnötig reproduziert werden.

## Metrikdaten auf Benutzerhandbuchebene

+ Metadaten, die das Benutzerhandbuch beschreiben, werden im `TOC.md`. Dazu gehören:
   + product - Name des Produkts/der Funktion.
   + Cloud - Cloud, zu der dieses Produkt gehört.
   + Zielgruppe - Zielgruppe oder Archetyp, auf den der Leitfaden ausgerichtet ist.
   + user-guide - Name des Benutzerhandbuchs.

## Metadaten auf Seitenebene

+ Metadaten, die zur Beschreibung eines Dokuments erforderlich sind, werden als Teil jeder einzelnen Seite gespeichert. Dazu gehören:
   + title - Titel der Seite.
   + description - Beschreibung der Seite.
   + seo-title - seo alternative title.
   + seo-description - alternativer Titel für SEO Zwecke.
   + short-title - (optionales Feld).
   + index - ja/nein - wird die Seite von der Suchplattform von Adobe indiziert.
   + translate - ja / nein - wird diese Seite lokalisiert.
   + Version - wird hauptsächlich für AEM und Campaign verwendet, um die Version des Produkts zu kennzeichnen.
   + private-feature-pack - wird primär für AEM verwendet.
   + beta - ist dieses Produkt in der Beta?
   + redirect - kann verwendet werden, um bei Bedarf eine Referenz zu einer neuen Seite zu erstellen.
   + doc-type: reference (Standard) / troubleshooting / developer / tutorial / kb / whitepaper.

## Weitere Info

Weitere Veröffentlichungsanweisungen, Stilhandbücher, Beispiele und andere Ressourcen finden Sie im [kollaborativen Dokumentationsbericht](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)

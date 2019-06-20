---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Anleitung

**Hinweis: Diese Seite (oder beliebige Readme. md-Seite) wird nicht in der Kundenbezogenen Dokumentation veröffentlicht.**

## Inhaltsverzeichnis

+ `TOC.md` im Stamm des Benutzerhandbuchs finden Sie die Organisation der Themen, die im Handbuch für diese Lösung enthalten sind.
+ Jedes Benutzerhandbuch verfügt über eine eigene, in `TOC.md`der Sie alle Seiten/Themen nach Bedarf sortieren können.
+ Die erste Seite aller Benutzerhandbücher `overview.md`ist.

## Benutzerhandbuch

+ Die Einführung in das Benutzerhandbuch heißt `overview.md`
+ Jedes Thema im Benutzerhandbuch hat seinen eigenen eigenen Ordner.
   + Wenn im Guide ein Thema namens *Implementierung vorhanden ist*, lautet der entsprechende Ordner `/implementation`
+ Alle Bild-Assets werden im `/assets` Stamm des Benutzerhandbuchs gespeichert.
   + Alle Bilder im `/assets` Ordner werden lokalisiert.
   + Alle Bilder im `/no-localize` Ordner werden nicht lokalisiert (es gibt eine Überraschung!). Dies kann verwendet werden, um in den loc-Versionen sicherzustellen, dass bestimmte Assets nicht unnötig reproduziert werden.

## Meta-Daten für Benutzerführungsebene

+ Metadaten, die das Benutzerhandbuch beschreibt, werden im Abschnitt `TOC.md`gespeichert. Dazu gehören:
   + product - Name des Produkts/der Funktion.
   + Cloud - Cloud, zu der dieses Produkt gehört.
   + Zielgruppe - Zielgruppe oder Archetype, auf dem das Handbuch ausgerichtet ist.
   + user-guide - Name des Benutzerhandbuchs.

## Metadaten auf Seitenebene

+ Die zur Beschreibung eines Dokuments erforderlichen Metadaten werden als Teil jeder einzelnen Seite gespeichert. Dazu gehören:
   + title - Titel der Seite.
   + description - description of page.
   + seo-title - Seo-alternative Titel.
   + seo-description - alternative Titel für SEO-Zwecke.
   + short-title - (optionales Feld).
   + index - ja/nein - wird die Seite durch die Suchplattform von Adobe indexiert.
   + übersetzen - ja/nein - wird diese Seite lokalisiert.
   + Version - hauptsächlich für AEM und Campaign verwendet, um die Produktversion zu kennzeichnen.
   + private-feature-pack - hauptsächlich für AEM verwendet.
   + beta - ist dieses Produkt in der Beta-Phase?
   + Umleitung - Kann verwendet werden, um eine ref zu einer neuen Seite zu erstellen, die erforderlich ist.
   + doc-type: reference (Standard)/troubleshooting/developer/tutorial/kb/whitepaper.

## Weitere Info

Weitere Veröffentlichungsanweisungen, Stilhandbücher, Beispiele und andere Ressourcen finden Sie in [der Replizierung der Dokumentation.](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)

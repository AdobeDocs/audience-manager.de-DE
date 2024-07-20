---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---
# Anleitung

**Hinweis: Diese Seite (oder jede andere &quot;readme.md&quot;-Seite) wird nicht in der Kundendokumentation veröffentlicht**

## TOC

+ `TOC.md` im Stammverzeichnis des Benutzerhandbuchs bietet die Organisation der Themen, die im Handbuch für diese Lösung enthalten sind.
+ Jedes Benutzerhandbuch verfügt über sein eigenes &quot;`TOC.md`&quot;, in dem Sie alle Seiten/Themen nach Bedarf sortieren können.
+ Die erste Seite aller Benutzerhandbücher ist `overview.md`.

## Benutzerhandbuch

+ Die Einführung in das Benutzerhandbuch heißt `overview.md`
+ Jedes Thema im Benutzerhandbuch verfügt über ein eigenes Verzeichnis.
   + Wenn im Handbuch ein Thema namens *Implementierung* enthalten ist, lautet der entsprechende Ordner `/implementation`
+ Alle Bild-Assets werden in `/assets` im Stammverzeichnis des Benutzerhandbuchs gespeichert.
   + Alle Bilder im Verzeichnis `/assets` werden lokalisiert.
   + Bilder im Verzeichnis `/no-localize` werden nicht lokalisiert (es gibt eine Überraschung!). Dies kann verwendet werden, um in lokalen Versionen sicherzustellen, dass bestimmte Assets nicht unnötig reproduziert werden.

## Metadaten auf Benutzerhandbuchebene

+ Metadaten, die das Benutzerhandbuch beschreiben, werden im `TOC.md` gespeichert. Dazu gehören:
   + product - Name des Produkts/der Funktion.
   + cloud - Cloud, zu der dieses Produkt gehört.
   + audience - Zielgruppe oder Archetyp, auf den das Handbuch ausgerichtet ist.
   + user-guide - Name des Benutzerhandbuchs.

## Metadaten auf Seitenebene

+ Metadaten, die zur Beschreibung eines Dokuments erforderlich sind, werden als Teil jeder einzelnen Seite gespeichert. Dazu gehören:
   + title - Titel der Seite.
   + description - Beschreibung der Seite.
   + seo-title - Seo Alternative Titel.
   + seo-description - Alternativtitel für SEO-Zwecke.
   + short-title - (optionales Feld)
   + index - ja/nein - wird die Seite von der Adobe-Suchplattform indexiert.
   + translate - ja/nein - wird diese Seite lokalisiert.
   + version - wird hauptsächlich für AEM und Campaign verwendet, um die Produktversion zu kennzeichnen.
   + private-feature-pack - wird hauptsächlich für AEM verwendet.
   + beta - Ist dieses Produkt in der Beta-Phase?
   + redirect - kann verwendet werden, um bei Bedarf eine Referenz zu einer neuen Seite zu erstellen.
   + doc-type: reference (Standard)/troubleshooting/developer/tutorial/kb/whitepaper.

## Weitere Info

Weitere Veröffentlichungsanweisungen, Stilhandbücher, Beispiele und andere Ressourcen finden Sie im [Kollaboratives Dokumentationsverzeichnis](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)

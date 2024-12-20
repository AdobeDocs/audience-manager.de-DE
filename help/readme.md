---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 2%

---
# Anleitung

**Hinweis: Diese Seite (oder eine beliebige Readme.md-Seite) wird nicht in der Dokumentation für Kunden veröffentlicht**

## INHALT

+ `TOC.md` im Stammverzeichnis des Benutzerhandbuchs enthält die Organisation der Themen, die im Handbuch für diese Lösung enthalten sind.
+ Jedes Benutzerhandbuch verfügt über eine eigene `TOC.md`, in der Sie alle Seiten/Themen nach Bedarf sortieren können.
+ Die erste Seite aller Benutzerhandbücher ist `overview.md`.

## Benutzerhandbuch

+ Die Einführung in das Benutzerhandbuch heißt `overview.md`
+ Jedes Thema im Benutzerhandbuch hat ein eigenes Verzeichnis.
   + Wenn es ein Thema im Handbuch namens *Implementierung* gibt, wird das entsprechende Verzeichnis `/implementation`
+ Alle Bild-Assets werden in `/assets` im Stamm des Benutzerhandbuchs gespeichert.
   + Alle Bilder im `/assets` werden lokalisiert.
   + Bilder im `/no-localize` werden nicht lokalisiert (Überraschung!). Dies kann verwendet werden, um in Sperrversionen sicherzustellen, dass bestimmte Assets nicht unnötig reproduziert werden.

## Metadaten auf Benutzeranleitungsebene

+ In der `TOC.md` werden Metadaten gespeichert, die das Benutzerhandbuch beschreiben. Dazu gehören:
   + Produkt - Name des Produkts/der Funktion.
   + Cloud - Cloud, zu der dieses Produkt gehört.
   + Zielgruppe : Zielgruppe oder Archetyp, an die sich der Guide richtet.
   + Benutzerhandbuch - Name des Benutzerhandbuchs.

## Metadaten auf Seitenebene

+ Metadaten, die ein Dokument beschreiben, werden als Teil jeder einzelnen Seite gespeichert. Dazu gehören:
   + Titel - Titel der Seite.
   + Beschreibung - Beschreibung der Seite.
   + SEO-Titel - SEO Alternativtitel.
   + seo-description - Alternativer Titel für SEO-Zwecke.
   + short-title - (optionales Feld).
   + Index - Ja/Nein - wird die Seite von der Suchplattform Adobe auf indiziert.
   + Übersetzen - Ja/Nein - wird diese Seite lokalisiert.
   + version : wird hauptsächlich für AEM und Campaign verwendet, um die Produktversion anzugeben.
   + private-feature-pack - wird hauptsächlich für AEM verwendet.
   + Beta - Ist dieses Produkt in der Beta-Phase?
   + Umleiten : Kann verwendet werden, um bei Bedarf eine Referenz auf eine neue Seite zu erstellen.
   + Dokumenttyp: Referenz (Standard) / Fehlerbehebung / Entwickler / Tutorial / KB / Whitepaper.

## Weitere Info

Weitere Veröffentlichungsanweisungen, Style Guides, Beispiele und andere Ressourcen finden Sie unter [Partizipatives Dokumentationsverzeichnis](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)

---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Anleitung

**Hinweis: Diese Seite (oder beliebige Readme. md-Seite) wird nicht in der Kundenbezogenen Dokumentation veröffentlicht.**

## Inhaltsverzeichnis

+ `TOC.md` im Stamm des Benutzerhandbuchs finden Sie die Organisation der Themen, die im Handbuch für diese Lösung enthalten sind.
+ Each user guide will have its own unique `TOC.md`, in which you can order all the pages/topics as necessary.
+ The first page of all user guides is `overview.md`.

## Benutzerhandbuch

+ The introduction to the user guide is called `overview.md`
+ Jedes Thema im Benutzerhandbuch hat seinen eigenen eigenen Ordner.
   + If there is a topic in the guide called *Implementation*, the corresponding directory is `/implementation`
+ All image assets are stored in `/assets` at the root of the user guide.
   + All images in the `/assets` directory will be localized.
   + Any images in the `/no-localize` directory will not be localized (there's a surprise!). Dies kann verwendet werden, um in den loc-Versionen sicherzustellen, dass bestimmte Assets nicht unnötig reproduziert werden.

## Meta-Daten für Benutzerführungsebene

+ Meta data which describes the user guide is stored in the `TOC.md`. Dazu gehören:
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

For more publishing instructions, style guides, samples and other resources, please visit the [Collaborative Documentation Repo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)

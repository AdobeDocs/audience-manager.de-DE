---
description: Benennen Sie Ihre Metadatendatei für Zielgruppenoptimierungen gemäß diesen Spezifikationen.
seo-description: Benennen Sie Ihre Metadatendatei für Zielgruppenoptimierungen gemäß diesen Spezifikationen.
seo-title: Namenskonventionen für Metadatendateien
solution: Audience Manager
title: Namenskonventionen für Metadatendateien
uuid: cab 55 b 2 a -2 e 54-45 f 6-aeea -3735 b 911 f 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Naming Conventions for Metadata Files{#naming-conventions-for-metadata-files}

Benennen Sie Ihre Metadatendatei für Zielgruppenoptimierungen gemäß diesen Spezifikationen.

## Syntax and ID Categories {#syntax}

Die folgende Syntax definiert die Struktur eines gut formatierten Metadatendateinamens. Note, *italics* indicates a variable placeholder. Die anderen Elemente sind Konstanten und ändern sich nicht.

**Syntax:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Verwenden* Sie keine Dateierweiterungen in Ihren Metadatendateien (.txt oder anderen).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* The middle component **0** is technically the Parent ID, which is a legacy field. The value should always be set as **0**.
* Je nach Dimension kann die untergeordnete ID einen Wert zwischen 1 und 10 aufweisen. Das sieht dann so aus:

## Child ID dimensions {#child-dimension}

Im Metadatendateinamen ist die untergeordnete ID ein Bezeichner, der den Datentyp in einer Datei klassifiziert und in eine Hierarchie legt. Sie können die untergeordnete ID im Dateinamen mit den folgenden Kategorien-IDs versehen:

1. Kampagne
1. Kreativ
1. Platzierung
1. Exchange-
1. Site
1. Advertiser (if using integration codes in a [data source](../../../features/manage-datasources.md#details))
1. Einfügereihenfolge (IO)
1. Vertikal (d. h. eine bestimmte Branche oder Geschäftskategorie wie "Computer" ," Automobile" , "Liegenschaften" usw.)
1. Taktik
1. Geschäftseinheit oder Marke

## Beispiel {#example}

Bei einer Creative-Metadatendatei könnte der Dateiname 20190115_ 0_ 2 lauten.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->

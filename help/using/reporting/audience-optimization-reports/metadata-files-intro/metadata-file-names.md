---
description: Benennen Sie Ihre Audience Optimization-Metadatendatei gemäß diesen Spezifikationen.
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: Benennungskonventionen für Metadatendateien
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 2%

---

# Benennungskonventionen für Metadatendateien{#naming-conventions-for-metadata-files}

Benennen Sie Ihre Audience Optimization-Metadatendatei gemäß diesen Spezifikationen.

## Syntax- und ID-Kategorien {#syntax}

Die folgende Syntax definiert die Struktur eines wohlgeformten Metadatendateinamens. Hinweis: *Kursiv* gibt einen Variablenplatzhalter an. Die anderen Elemente sind Konstanten und ändern sich nicht.

**Syntax:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Verwenden Sie* Dateierweiterungen in Ihren Metadatendateien (.txt oder andere).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* Die mittlere Komponente **0** ist technisch gesehen die übergeordnete ID, ein älteres Feld. Der Wert sollte immer als **0** festgelegt werden.
* Die untergeordnete ID kann je nach Dimension einen Wert zwischen 1 und 10 aufweisen. Das sieht dann so aus:

## Dimensionen der untergeordneten ID {#child-dimension}

Im Namen der Metadatendatei ist die untergeordnete ID ein Bezeichner, der den Datentyp in einer Datei klassifiziert und in einer Hierarchie platziert. Sie können die untergeordnete ID im Dateinamen mit den folgenden Kategorie-IDs taggen:

1. Kampagne
1. Kreativ
1. Platzierung
1. Exchange-
1. Site
1. Advertiser (bei Verwendung von Integrations-Codes in einer [Datenquelle](../../../features/manage-datasources.md#details))
1. Einfügungsreihenfolge (IO)
1. Vertikal (d. h. eine bestimmte Branche oder Geschäftskategorie wie „Computer“, „Automobile“, „Immobilien“ usw.)
1. Taktik
1. Geschäftseinheit oder Marke

## Beispiel {#example}

Für eine Creative-Metadatendatei könnte der Dateiname 20190115_0_2 lauten.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->

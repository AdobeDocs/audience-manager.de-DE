---
description: Benennen Sie Ihre Metadatendatei für die Optimierung der Audience entsprechend diesen Spezifikationen.
seo-description: Benennen Sie Ihre Metadatendatei für die Optimierung der Audience entsprechend diesen Spezifikationen.
seo-title: Benennungskonventionen für Metadatendateien
solution: Audience Manager
title: Benennungskonventionen für Metadatendateien
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 3%

---


# Benennungskonventionen für Metadatendateien{#naming-conventions-for-metadata-files}

Benennen Sie Ihre Metadatendatei für die Optimierung der Audience entsprechend diesen Spezifikationen.

## Syntax- und ID-Kategorien {#syntax}

Die folgende Syntax definiert die Struktur eines gut formatierten Metadatendateinamens. Note, *italics* indicates a variable placeholder. Die anderen Elemente sind Konstanten und bleiben unverändert.

**Syntax:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Verwenden Sie keine* Dateierweiterungen in Ihren Metadatendateien (.txt oder andere).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* Die mittlere Komponente **0** ist technisch gesehen die übergeordnete ID, bei der es sich um ein veraltetes Feld handelt. Der Wert sollte immer auf **0** gesetzt werden.
* Die untergeordnete ID kann je nach Dimension einen Wert zwischen 1 und 10 aufweisen. Das sieht dann so aus:

## Untergeordnete ID-Dimensionen {#child-dimension}

Im Metadaten-Dateinamen ist die untergeordnete ID ein Bezeichner, der den Datentyp in einer Datei klassifiziert und in einer Hierarchie ablegt. Sie können die untergeordnete ID im Dateinamen mit den folgenden Kategorien-IDs taggen:

1. Kampagne
1. Kreativ
1. Platzierung
1. Exchange-
1. Site
1. Advertiser (bei Verwendung von Integrationscodes in einer [Datenquelle](../../../features/manage-datasources.md#details))
1. Einfügereihenfolge (IO)
1. Vertikal (d. h. eine bestimmte Industrie- oder Geschäftswelt wie &quot;Computer&quot;, &quot;Automobile&quot;, &quot;Immobilien&quot;usw.)
1. Taktik
1. Geschäftseinheit oder Marke

## Beispiel {#example}

Bei einer Creative-Metadatendatei könnte der Dateiname 20190115_0_2 lauten.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->

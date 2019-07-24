---
description: Diese Zuordnung enthält die wichtigsten Audience Manager-Systeme. Sie stellt visuell dar, wie Daten in, aus und zwischen Audience Manager-Komponenten fließen.
seo-description: Diese Zuordnung enthält die wichtigsten Audience Manager-Systeme. Sie stellt visuell dar, wie Daten in, aus und zwischen Audience Manager-Komponenten fließen.
seo-title: Plattformarchitektur für Plattformarchitektur
solution: Audience Manager
title: Plattformarchitektur für Plattformarchitektur
uuid: d 845 af 1 d-f 448-4 f 4 c -948 e-b 2 c 89 f 125086
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Platform Architecture: Data Flow Map{#platform-architecture-data-flow-map}

Diese Zuordnung enthält die wichtigsten Audience Manager-Systeme. Sie stellt visuell dar, wie Daten in, aus und zwischen Audience Manager-Komponenten fließen.

## How to read this map {#compmap}

<!-- 

c_compmap.xml

 -->

In the map, the gray box contains [!DNL Audience Manager] systems. Some components are completely internal and others sit on the boundary between [!DNL Audience Manager] and the outside world. As an [!DNL Audience Manager] customer, internal components are often transparent or inaccessible. Manchmal können Sie mit diesen Systemen jedoch auch über die Benutzeroberfläche oder Datenintegrationen interagieren. Systems on the edge of the box collect and send data between [!DNL Audience Manager] and the outside world.

Colors define the type of data that flows in and out of [!DNL Audience Manager]. Grün sind Client-Daten, Blau sind Kundendaten (Besucher, die Ihre Site besuchen), orange sind Daten, die für die Berichterstellung verwendet werden.

For system descriptions and summaries see the data [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md), and [tag management](../../reference/system-components/components-tag-management.md) sections.

![](assets/flowmap.png)


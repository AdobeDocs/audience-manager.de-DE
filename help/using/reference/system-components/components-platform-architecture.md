---
description: Diese Karte enthält die wichtigsten Audience Manager-Systeme. Sie visualisiert den Datenfluss in, aus und zwischen Audience Manager-Komponenten.
seo-description: Diese Karte enthält die wichtigsten Audience Manager-Systeme. Sie visualisiert den Datenfluss in, aus und zwischen Audience Manager-Komponenten.
seo-title: Datenflusskarte für die Plattformarchitektur
solution: Audience Manager
title: Datenflusskarte für die Plattformarchitektur
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: 'Systemkomponenten '
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# Plattformarchitektur: Datenflusskarte{#platform-architecture-data-flow-map}

Diese Karte enthält die wichtigsten Audience Manager-Systeme. Sie visualisiert den Datenfluss in, aus und zwischen Audience Manager-Komponenten.

## Lesen dieser Karte {#compmap}

<!-- 

c_compmap.xml

 -->

In der Karte enthält der graue Kasten [!DNL Audience Manager] Systeme. Einige Komponenten sind vollständig intern und andere liegen an der Grenze zwischen [!DNL Audience Manager] und der Außenwelt. Als [!DNL Audience Manager]-Kunde sind interne Komponenten häufig transparent oder nicht zugänglich. Manchmal können Sie jedoch über die Benutzeroberfläche oder Datenintegrationen mit diesen Systemen interagieren. Systeme am Rand der Box sammeln und senden Daten zwischen [!DNL Audience Manager] und der Außenwelt.

Farben definieren den Datentyp, der in [!DNL Audience Manager] fließt. Grün sind Kundendaten, Blau Kundendaten (Besucher Ihrer Site) und Orange Daten, die für die Berichterstellung verwendet werden.

Systembeschreibungen und Zusammenfassungen finden Sie in den Abschnitten [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) und [Tag Management](../../reference/system-components/components-tag-management.md) .

![](assets/flowmap.png)

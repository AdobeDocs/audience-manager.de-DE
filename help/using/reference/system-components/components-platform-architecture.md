---
description: Diese Karte enthält die wichtigsten Audience Manager-Systeme. Es stellt visuell dar, wie Daten in Audience Manager-, Aus- und zwischen den Komponenten fließen.
seo-description: Diese Karte enthält die wichtigsten Audience Manager-Systeme. Es stellt visuell dar, wie Daten in Audience Manager-, Aus- und zwischen den Komponenten fließen.
seo-title: Plattform-Architektur-Datenflusszuordnung
solution: Audience Manager
title: Plattform-Architektur-Datenflusszuordnung
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: 'Systemkomponenten '
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# Plattformarchitektur: Datenflusskarte{#platform-architecture-data-flow-map}

Diese Karte enthält die wichtigsten Audience Manager-Systeme. Es stellt visuell dar, wie Daten in Audience Manager-, Aus- und zwischen den Komponenten fließen.

## Lesen dieser Map {#compmap}

<!-- 

c_compmap.xml

 -->

In der Map enthält das graue Feld [!DNL Audience Manager] Systeme. Einige Komponenten sind komplett intern und andere liegen an der Grenze zwischen [!DNL Audience Manager] und der Außenwelt. Als [!DNL Audience Manager]-Kunde sind interne Komponenten häufig transparent oder nicht zugänglich. Manchmal können Sie jedoch über die Benutzeroberfläche oder Datenintegrationen mit diesen Systemen interagieren. Systeme am Rand der Box sammeln und senden Daten zwischen [!DNL Audience Manager] und der Außenwelt.

Farben definieren den Datentyp, der von [!DNL Audience Manager] in- und abfließt. Grün sind Kundendaten, blau sind Kundendaten (Personen, die Ihre Site besuchen) und orange sind Daten, die zum Berichte verwendet werden.

Systembeschreibungen und Zusammenfassungen finden Sie in den Abschnitten [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md) und [tag management](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)

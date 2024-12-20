---
description: Diese Karte zeigt die wichtigsten Audience Manager. Es stellt visuell dar, wie Daten in Audience Manager-Komponenten gelangen, aus ihnen hervorgehen und zwischen ihnen fließen.
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Datenflusszuordnung der Platform-Architektur
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 0%

---

# Platform-Architektur: Datenflusszuordnung{#platform-architecture-data-flow-map}

Diese Karte zeigt die wichtigsten Audience Manager. Es stellt visuell dar, wie Daten in Audience Manager-Komponenten gelangen, aus ihnen hervorgehen und zwischen ihnen fließen.

## Wie man diese Karte liest {#compmap}

<!-- 

c_compmap.xml

 -->

In der Karte enthält das graue Feld [!DNL Audience Manager]. Einige Komponenten sind vollständig intern und andere befinden sich an der Grenze zwischen [!DNL Audience Manager] und Außenwelt. Als [!DNL Audience Manager]-Kunde sind interne Komponenten oft transparent oder unzugänglich. Manchmal können Sie jedoch über die Benutzeroberfläche oder Datenintegrationen mit diesen Systemen interagieren. Systeme am Rand der Box erfassen und senden Daten zwischen [!DNL Audience Manager] und der Außenwelt.

Farben definieren den Typ der Daten, die in und aus [!DNL Audience Manager] fließen. Grün sind die Kundendaten, blau sind die Kundendaten (Personen, die Ihre Site besuchen) und orange sind die Daten, die für das Reporting verwendet werden.

Systembeschreibungen und Zusammenfassungen finden Sie in den Abschnitten [Aktion](../../reference/system-components/components-data-action.md), [Sammlung](../../reference/system-components/components-data-collection.md), [Verarbeitung](../../reference/system-components/components-data-processing.md) und [Tag-Management](../../reference/system-components/components-tag-management.md) .

![](assets/flowmap.png)

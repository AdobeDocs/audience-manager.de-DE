---
description: Audience Manager nutzt verteilte, modernste Computing-Topologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-description: Audience Manager nutzt verteilte, modernste Computing-Topologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-title: Grundlegendes zum Edge-Datenzentrum
solution: Audience Manager
title: Grundlegendes zum Edge-Datenzentrum
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: 'Systemkomponenten '
exl-id: 28958b49-3075-4601-9271-ef2913721a66
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Grundlegendes zum Edge-Datenzentrum{#understanding-the-edge-data-center}

Audience Manager nutzt verteilte, modernste Computing-Topologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.

## Grundlagen zum Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge-Computing bietet eine verbesserte Leistung als Reaktion auf eine diffuse, internetweite Nachfrage, da die &quot;Kante&quot;selbst eine globale Grenze ist. Das bedeutet, dass [!DNL Audience Manager] die Verarbeitung dynamisch den Nachfragequellen am nächsten kommt und Daten über den schnellstmöglichen Pfad zurückgibt. Edge-Computing hilft bei der Aufrechterhaltung der Site-Performance, wodurch wiederum das Benutzererlebnis auf Ihrer Website erhalten bleibt. Das Edge-Rechenzentrum ist ein wichtiges Gateway zum Verschieben von Daten in und aus [!DNL Audience Manager].

Das Edge-Rechenzentrum umfasst:[!DNL Audience Manager]

* **Core-Server:** Dies sind die wichtigsten  [!DNL Audience Manager] Systeme. Sie aktualisieren und stellen Daten für die Edge-Server bereit.

* **Edge-Server:** Normalerweise handelt es sich um Anwendungs- und/oder Webserver. Sie sitzen an der Grenze zwischen [!DNL Audience Manager] und dem Internet. Edge-Server, wie z. B. die [!DNL DCS]- oder Akamai-Systeme, behandeln in der Regel Daten und Anforderungen, die von [!DNL Audience Manager] in- und abfließen.

* **Lastenausgleich:** Verwalten Sie ungleiche Computing-/Verarbeitungsanforderungen, die mit Internetanwendungen verbunden sind. Diese Ausgleiche verhindern, dass Cluster von Servern überladen werden, während andere untätig bleiben.

Die folgende Abbildung zeigt die Umgebung des Rechenzentrums am Audience Manager.

![](assets/edge_data_center.png)

## Geografische Verteilung und Lastenausgleich {#geo-dist-balance}

Siehe Abschnitt [!DNL DCS] in [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

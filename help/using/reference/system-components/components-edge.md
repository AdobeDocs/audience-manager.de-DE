---
description: Audience Manager verwendet verteilte Edge-Computing-Topologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Grundlegendes zum Edge-Rechenzentrum
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
TQID: https://experienceleague.adobe.com/S1eOQwB9eoOlLbnbXtqjArrSEa2cTXjWwvJfwNbAtXc
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 0%

---

# Grundlegendes zum Edge-Rechenzentrum{#understanding-the-edge-data-center}

Audience Manager verwendet verteilte Edge-Computing-Topologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.

## Grundlagen zum Edge-Rechenzentrum {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge Computing bietet eine verbesserte Leistung als Reaktion auf diffuse, Internet-weite Anforderungen, da der „Edge“ selbst eine globale Grenze darstellt. Das bedeutet, [!DNL Audience Manager] die Verarbeitung dynamisch den Nachfragequellen am nächsten platziert und Daten auf dem kürzestmöglichen Pfad zurückgibt. Edge Computing trägt zur Aufrechterhaltung der Site-Performance bei, wodurch wiederum das Benutzererlebnis auf Ihrer Website erhalten bleibt. Das Edge-Rechenzentrum ist ein wichtiges Gateway zum Verschieben von Daten in und aus [!DNL Audience Manager].

Das [!DNL Audience Manager] Edge-Rechenzentrum umfasst:

* **Core-Server** Dies sind die wichtigsten [!DNL Audience Manager]. Sie aktualisieren und stellen den Edge-Servern Daten bereit.

* **Edge-Server:** Normalerweise handelt es sich um Anwendungs- und/oder Webserver. Sie befinden sich an der Grenze zwischen [!DNL Audience Manager] und Internet. Edge-Server, wie z. B. die [!DNL DCS]- oder Akamai-Systeme, verarbeiten in der Regel Daten und Anfragen, die in und aus [!DNL Audience Manager] fließen.

* **Lastenausgleich:** Verwaltung unregelmäßiger Rechen-/Verarbeitungsanforderungen, die mit Internet-Anwendungen verbunden sind. Diese Balancer verhindern, dass Server-Cluster überlastet werden, während andere inaktiv bleiben.

Die folgende Abbildung zeigt die Audience Manager Edge-Rechenzentrumsumgebung.

![](assets/edge_data_center.png)

## Geografische Verteilung und Lastenausgleich {#geo-dist-balance}

Siehe den [!DNL DCS] Abschnitt in [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

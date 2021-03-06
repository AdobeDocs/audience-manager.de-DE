---
description: Audience Manager verwendet verteilte, ausgereifte Computertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-description: Audience Manager verwendet verteilte, ausgereifte Computertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-title: Grundlegendes zum Edge-Datenzentrum
solution: Audience Manager
title: Grundlegendes zum Edge-Datenzentrum
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: 'Systemkomponenten '
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Grundlegendes zum Edge-Datenzentrum{#understanding-the-edge-data-center}

Audience Manager verwendet verteilte, ausgereifte Computertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.

## Grundlagen zum Edge-Rechenzentrum {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge-Computing bietet eine verbesserte Leistung als Reaktion auf die diffuse, internetweite Nachfrage, da der &quot;Edge&quot;selbst eine globale Grenze darstellt. Das bedeutet, dass [!DNL Audience Manager] die Verarbeitung dynamisch den Nachfragequellen am nächsten platziert und Daten über den kürzestmöglichen Pfad zurückgibt. Mit Edge Computing können Sie die Site-Leistung aufrechterhalten, wodurch wiederum das Benutzererlebnis auf Ihrer Website erhalten bleibt. Das Edge-Rechenzentrum ist ein wichtiges Gateway zum Verschieben von Daten in und aus [!DNL Audience Manager].

Das Edge-Rechenzentrum [!DNL Audience Manager] umfasst:

* **Kernserver:** Dies sind die wichtigsten  [!DNL Audience Manager] Systeme. Sie aktualisieren und stellen Daten für die Edge-Server bereit.

* **Edge-Server:** Normalerweise handelt es sich hierbei um Anwendungs- und/oder Webserver. Sie sitzen an der Grenze zwischen [!DNL Audience Manager] und dem Internet. Edge-Server wie die [!DNL DCS]- oder Akamai-Systeme handhaben normalerweise Daten und Anforderungen, die von [!DNL Audience Manager] in- und abwandern.

* **Lastenausgleich:** Verwalten Sie unausgewogene Computer-/Verarbeitungsanforderungen, die mit Internetanwendungen verbunden sind. Diese Ausgleichssysteme verhindern, dass Servercluster überlastet werden, während andere inaktiv bleiben.

Die folgende Abbildung zeigt die Audience Manager Edge-Rechenzentrumsumgebung.

![](assets/edge_data_center.png)

## Geografische Verteilung und Lastenausgleich {#geo-dist-balance}

Siehe Abschnitt [!DNL DCS] in [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

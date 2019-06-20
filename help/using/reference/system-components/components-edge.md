---
description: Audience Manager verwendet verteilte Edge-Rechnertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-description: Audience Manager verwendet verteilte Edge-Rechnertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-title: Das Edge Data Center
solution: Audience Manager
title: Das Edge Data Center
uuid: 4177 e 666-99 f 4-453 d -94 dd -58 c 6182 c 8 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Das Edge Data Center{#understanding-the-edge-data-center}

Audience Manager verwendet verteilte Edge-Rechnertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.

## Grundlagen der Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Die Leistung von Edge-Rechnern bietet eine verbesserte Leistung als Reaktion auf eine diffuse Internetbreite, da die &quot;edge&quot; selbst eine globale Grenze ist. Dies bedeutet, dass die Verarbeitung [!DNL Audience Manager] dynamisch verarbeitet wird, die den Quellen der Nachfrage am nächsten ist, und Daten durch den kürzesten Pfad zurückgibt. Mit der Edge-Datenbank bleibt die Site-Performance erhalten, die wiederum die Benutzererfahrung auf Ihrer Website beibehält. Das Edge Data Center ist ein wichtiges Gateway [!DNL Audience Manager]zum Verschieben von Daten in und aus.

Das [!DNL Audience Manager] Edge Data Center umfasst:

* **Core-Server:** Dies sind die [!DNL Audience Manager] Hauptsysteme. Sie aktualisieren und liefern Daten an die Edge-Server.

* **Edge Server:** Normalerweise sind dies Anwendungen und/oder Webserver. Sie befinden sich an der Grenze zwischen und [!DNL Audience Manager] im Internet. Edge-Server wie das [!UICONTROL DCS] oder Akamai-System verarbeiten normalerweise Daten und Anforderungen, [!DNL Audience Manager]die in- und ablaufen.

* **Lastenausgleich:** Ungleichmäßige Verarbeitungs-/Verarbeitungsanforderungen in Internetanwendungen verwalten. Diese Balken verhindern, dass Servercluster überlastet werden, während andere inaktiv bleiben.

Das folgende Diagramm veranschaulicht die Edge Manager-Edge-Datencenter-Umgebung.

![](assets/edge_data_center.png)

## Geografischer Verteilung und Lastenausgleich {#geo-dist-balance}

Siehe [!UICONTROL DCS] Abschnitt in [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).

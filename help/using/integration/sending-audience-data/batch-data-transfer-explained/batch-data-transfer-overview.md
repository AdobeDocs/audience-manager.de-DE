---
description: Eine Übersicht für technische und nicht-technische Kunden, die Daten von anderen Systemen (offline) in Audience Manager importieren möchten.
keywords: Eingehend, Batch, Batch-Upload, Batch-Daten
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Senden von Batch-Daten an Audience Manager - Übersicht
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 4%

---

# Senden von Batch-Daten an [!DNL Audience Manager] Übersicht {#send-batch-data-to-audience-manager-overview}

Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in [!DNL Audience Manager] integrieren möchten.

## Vorteile

Sie können Daten aus anderen Systemen in [!DNL Audience Manager] verfügbar machen. Unser System kann Ihnen dabei helfen, den Wert Ihrer zuvor erfassten Benutzerdaten zu erschließen und zu nutzen. Dazu gehören Informationen zu Käufen, Kundenbefragungen, Registrierungsdaten, [!DNL CRM] usw. Zwar stellt jede Integration ihre eigenen Herausforderungen, doch teilen sie alle diese gemeinsamen Schritte. Lesen Sie dieses Material, um den Aufwand für das Online-Stellen Ihrer Offline-Daten zu reduzieren.

## Schritt 1: Benutzer-IDs synchronisieren

Während der Synchronisierung weist [!DNL Audience Manager] Clients und deren Benutzern eindeutige IDs zu. Diese IDs werden als [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) bzw. [!UICONTROL Unique User ID] ([!UICONTROL UUID]) bezeichnet. [!DNL Audience Manager] verwendet die [!UICONTROL DPID] und [!UICONTROL UUID], um Benutzer zu identifizieren und sie für [!UICONTROL traits], [!UICONTROL segments], Zielgruppengruppen und für das Reporting zu qualifizieren. Zusätzlich sucht unser Datenerfassungs-Code ([!UICONTROL DIL]) nach diesen IDs, um Besucherdaten von Ihrer Website zu erfassen. Wenn dieser Schritt abgeschlossen ist, sollten [!DNL Audience Manager] und Ihr Offline-Repository die entsprechenden IDs für jeden Benutzerdatensatz enthalten.

Wichtige Überlegungen zu diesem Schritt:

* **Platzierung der Client-ID:** [!DNL Audience Manager] muss wissen, wo Ihre Client-ID auf Ihrer Website erscheint (z. B. ob sie in einem Cookie, einer Analytics-Variablen, im Seiten-Code usw. gespeichert ist).
* **[!DNL PII] ausschließen:** Benutzer-IDs dürfen keine persönlich identifizierbaren Informationen ([!DNL PII]) enthalten.
* **Groß- und Kleinschreibung:** Während einer Echtzeit-Datensynchronisation müssen die von Ihrer Site erfassten Benutzer-IDs [!DNL Audience Manager] den IDs entsprechen, die von Ihrem Offline-Repository übergeben werden. Wenn beispielsweise Offline-Datensätze Informationen über [!DNL User123] enthalten, Ihre Site diese ID jedoch als [!DNL USER123] rendert, sieht [!DNL Audience Manager] diese als unterschiedliche Besucher. Daher können Online-Informationen für diesen Besucher nicht mit den entsprechenden Datensätzen in Ihrer Offline-Datenbank verknüpft werden. IDs müssen genau übereinstimmen.

Siehe [ID-Synchronisierung für eingehende Datenübertragungen](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Schritt 2: Datendateiformat

Dateinamen und Inhalte folgen strengen Richtlinien. Sie *müssen* Datendateien gemäß diesen Spezifikationen in diesem Handbuch benennen und organisieren. Siehe:

* [Anforderungen an Namen der über Amazon S3 eingehenden Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhalte eingehender Datendateien: Syntax, Variablen und Beispiele](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online-Daten sind für Offline-Marketing-Maßnahmen verfügbar

Wenn Sie Offline-Daten online schalten, können Sie diese Informationen weiterhin für Offline-Kampagnen verwenden. Dazu exportiert [!DNL Audience Manager] Trait- und Segmentinformationen an einen [!DNL FTP] oder [!DNL Amazon S3] Speicherort Ihrer Wahl. Wenden Sie sich an Ihren Partner Solutions Manager, um weitere Informationen oder Hilfe zu erhalten.

## Umgebungen

[!DNL Audience Manager] bietet die folgenden Umgebungen für die Ablage von Dateien:

| Umgebung | Service | Position |
|---------|----------|---------|
| Produktion | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Beta-Umgebung | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## Weitere technische Informationen

Systemingenieure, Entwickler oder technische/Implementierungs-Teams sollten [Batch-Datenübertragungsprozess beschrieben](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) und die anderen Artikel in diesem Abschnitt lesen. Diese Artikel enthalten Details zu Übertragungsprotokollen, Dateiinhalten und Dateinamenanforderungen.

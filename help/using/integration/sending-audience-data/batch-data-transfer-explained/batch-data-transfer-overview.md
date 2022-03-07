---
description: Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in den Audience Manager bringen möchten.
keywords: Eingehend, Batch, Batch-Upload, Batch-Daten
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Senden von Batch-Daten an Audience Manager – Überblick
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 6%

---

# Senden von Batch-Daten an [!DNL Audience Manager] Übersicht {#send-batch-data-to-audience-manager-overview}

Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in [!DNL Audience Manager].

## Vorteile

Sie können Daten aus anderen Systemen in [!DNL Audience Manager]. Unser System kann Ihnen dabei helfen, Werte zu entsperren und die Benutzerdaten zu nutzen, die Sie zuvor erfasst haben. Dazu gehören Informationen zu Käufen, Kundenumfragen, Registrierungsdaten, [!DNL CRM] Datenbanken usw. Zwar stellt jede Integration ihre eigenen Herausforderungen dar, doch teilen sie alle diese gemeinsamen Schritte. Lesen Sie dieses Material, um den Aufwand zu reduzieren, der für die Online-Bereitstellung Ihrer Offline-Daten erforderlich ist.

## Schritt 1: Benutzer-IDs synchronisieren

Während der Synchronisierung [!DNL Audience Manager] weist Clients und ihren Benutzern eindeutige IDs zu. Diese IDs werden als [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) und [!UICONTROL Unique User ID] ([!UICONTROL UUID]). [!DNL Audience Manager] verwendet die [!UICONTROL DPID] und [!UICONTROL UUID] , um Benutzer zu identifizieren und sie zu qualifizieren für [!UICONTROL traits], [!UICONTROL segments], Zielgruppen und für die Berichterstellung. Zusätzlich wird unser Datenerfassungscode ([!UICONTROL DIL]) sucht nach diesen IDs, um Besucherdaten von Ihrer Website zu erfassen. Wenn dieser Schritt abgeschlossen ist, [!DNL Audience Manager] und Ihr Offline-Repository sollte für jeden Benutzerdatensatz entsprechende IDs enthalten.

Wichtige Überlegungen zu diesem Schritt:

* **Client-ID-Platzierung:** [!DNL Audience Manager] muss wissen, wo Ihre Client-ID auf Ihrer Website erscheint (z. B. ob sie in einem Cookie, einer Analytics-Variablen, im Seiten-Code usw. gespeichert ist).
* **Ausschließen [!DNL PII]:** Benutzer-IDs dürfen keine personenbezogenen Daten enthalten ([!DNL PII]).
* **Groß-/Kleinschreibung und Inhaltssensitivität:** Bei einer Echtzeit-Datensynchronisation werden Benutzer-IDs, die von Ihrer Site erfasst werden, von [!DNL Audience Manager] muss den IDs entsprechen, die von Ihrem Offline-Repository übergeben werden. Wenn beispielsweise Offline-Datensätze Informationen zu [!DNL User123], aber Ihre Site rendert diese ID als [!DNL USER123], [!DNL Audience Manager] sieht diese als verschiedene Besucher an. Daher können Online-Informationen für diesen Besucher nicht mit den entsprechenden Datensätzen in Ihrer Offline-Datenbank verknüpft werden. IDs müssen exakt übereinstimmen.

Siehe [ID-Synchronisierung für eingehende Datenübertragungen](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Schritt 2: Datendateiformat

Dateinamen und Inhalt folgen strengen Richtlinien. You *must* Benennen und organisieren Sie Datendateien gemäß diesen Spezifikationen in diesem Handbuch. Siehe:

* [Anforderungen an Namen der über Amazon S3 eingehenden Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhalt der eingehenden Datendatei: Syntax, Variablen und Beispiele](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online-Daten sind für Offline-Marketing-Bemühungen verfügbar

Wenn Sie Offline-Daten online stellen, können Sie diese Informationen weiterhin für Offline-Kampagnen verwenden. Gehen Sie dazu folgendermaßen vor: [!DNL Audience Manager] Exportiert Eigenschaften- und Segmentinformationen in eine [!DNL FTP] oder [!DNL Amazon S3] Speicherort Ihrer Wahl. Wenden Sie sich für weitere Informationen oder Unterstützung an Ihren Partner Solutions Manager.

## Umgebungen

[!DNL Audience Manager] stellt die folgenden Umgebungen für das Ablegen von Dateien bereit:

| Umgebung | Diensleistung | Standort |
|---------|----------|---------|
| Produktion | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Beta-Umgebung | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients-sandbox-us-east-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Weitere technische Lesungen

Systemtechniker, Entwickler oder technische/Implementierungsteams sollten [Beschreibung des Batch-Datenübertragungsprozesses](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) und die anderen Artikel in diesem Abschnitt. Diese Artikel enthalten Details zu Übertragungsprotokollen, Dateiinhalten und Anforderungen an Dateinamen.

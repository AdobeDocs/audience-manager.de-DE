---
description: Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in den Audience Manager bringen möchten.
keywords: Eingehend, Batch, Batch-Upload, Batch-Daten
seo-description: Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in den Audience Manager bringen möchten. Verwenden Sie dazu die Option Batch-Upload in Audience Manager.
seo-title: Senden von Batch-Daten an Audience Manager – Überblick
solution: Audience Manager
title: Senden von Batch-Daten an Audience Manager – Überblick
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Übertragungen von Inbound-Daten
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# Senden von Batch-Daten an [!DNL Audience Manager] Übersicht {#send-batch-data-to-audience-manager-overview}

Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in [!DNL Audience Manager] übertragen möchten.

## Vorteile

Sie können Daten aus anderen Systemen in [!DNL Audience Manager] verfügbar machen. Unser System kann Ihnen dabei helfen, Werte zu entsperren und die Benutzerdaten zu nutzen, die Sie zuvor erfasst haben. Dazu gehören Informationen zu Käufen, Kundenumfragen, Registrierungsdaten, [!DNL CRM]-Datenbanken usw. Zwar stellt jede Integration ihre eigenen Herausforderungen dar, doch teilen sie alle diese gemeinsamen Schritte. Lesen Sie dieses Material, um den Aufwand zu reduzieren, der für die Online-Bereitstellung Ihrer Offline-Daten erforderlich ist.

## Schritt 1: Benutzer-IDs synchronisieren

Während der Synchronisierung weist [!DNL Audience Manager] Clients und ihren Benutzern eindeutige IDs zu. Diese IDs werden als [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) bzw. [!UICONTROL Unique User ID] ([!UICONTROL UUID]) bezeichnet. [!DNL Audience Manager] verwendet  [!UICONTROL DPID] und  [!UICONTROL UUID] , um Benutzer zu identifizieren und sie für  [!UICONTROL traits],  [!UICONTROL segments], Zielgruppen und Berichte zu qualifizieren. Darüber hinaus sucht unser Datenerfassungscode ([!UICONTROL DIL]) nach diesen IDs, um Besucherdaten von Ihrer Website zu erfassen. Wenn dieser Schritt abgeschlossen ist, sollten [!DNL Audience Manager] und Ihr Offline-Repository entsprechende IDs für jeden Benutzerdatensatz enthalten.

Wichtige Überlegungen zu diesem Schritt:

* **Platzierung der Client-ID:** [!DNL Audience Manager] muss wissen, wo Ihre Client-ID auf Ihrer Website erscheint (z. B. ob sie in einem Cookie, einer Analytics-Variablen, im Seiten-Code usw. gespeichert ist).
* **Ausschließen  [!DNL PII]:** Benutzer-IDs dürfen keine persönlich identifizierbaren Informationen enthalten ([!DNL PII]).
* **Groß- und Kleinschreibung:** Bei einer Echtzeit-Datensynchronisation  [!DNL Audience Manager] müssen die von Ihrer Site erfassten Benutzer-IDs den IDs entsprechen, die von Ihrem Offline-Repository übergeben werden. Wenn beispielsweise Offline-Datensätze Informationen zu [!DNL User123] enthalten, diese ID jedoch von Ihrer Site als [!DNL USER123] gerendert wird, werden sie von [!DNL Audience Manager] als unterschiedliche Besucher betrachtet. Daher können Online-Informationen für diesen Besucher nicht mit den entsprechenden Datensätzen in Ihrer Offline-Datenbank verknüpft werden. IDs müssen exakt übereinstimmen.

Siehe [ID-Synchronisierung für eingehende Datenübertragungen](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Schritt 2: Datendateiformat

Dateinamen und Inhalt folgen strengen Richtlinien. Sie *müssen* die Datendateien gemäß diesen Spezifikationen in diesem Handbuch benennen und organisieren. Siehe:

* [Anforderungen an Namen der über Amazon S3 eingehenden Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhalt der eingehenden Datendatei: Syntax, Variablen und Beispiele](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online-Daten sind für Offline-Marketing-Bemühungen verfügbar

Wenn Sie Offline-Daten online stellen, können Sie diese Informationen weiterhin für Offline-Kampagnen verwenden. Dazu exportiert [!DNL Audience Manager] Eigenschaften- und Segmentinformationen an einen [!DNL FTP]- oder [!DNL Amazon S3]-Speicherort Ihrer Wahl. Wenden Sie sich für weitere Informationen oder Unterstützung an Ihren Partner Solutions Manager.

## Umgebungen

[!DNL Audience Manager] stellt die folgenden Umgebungen für das Ablegen von Dateien bereit:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Umgebung </th> 
   <th colname="col02" class="entry"> Diensleistung </th> 
   <th colname="col2" class="entry"> Standort </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Produktion</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Beta-Umgebung</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Weitere technische Lesungen

Systemtechniker, Entwickler oder technische/Implementierungsteams sollten den Abschnitt [Batch-Datenübertragungsprozess, beschrieben](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) und die anderen Artikel in diesem Abschnitt lesen. Diese Artikel enthalten Details zu Übertragungsprotokollen, Dateiinhalten und Anforderungen an Dateinamen.

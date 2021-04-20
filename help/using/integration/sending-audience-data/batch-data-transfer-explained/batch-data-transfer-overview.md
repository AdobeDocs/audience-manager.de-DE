---
description: Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in den Audience Manager bringen möchten.
keywords: Inbound, Batch, Batch-Upload, Stapeldaten
seo-description: Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in den Audience Manager bringen möchten. Verwenden Sie dazu die Option zum Hochladen von Stapeln in Audience Manager.
seo-title: Senden von Batch-Daten an Audience Manager – Überblick
solution: Audience Manager
title: Senden von Batch-Daten an Audience Manager – Überblick
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 7%

---

# Stapeldaten an [!DNL Audience Manager] Übersicht {#send-batch-data-to-audience-manager-overview} senden

Eine Übersicht für technische und nicht-technische Kunden, die Daten von anderen Systemen (offline) in [!DNL Audience Manager] bringen möchten.

## Vorteile

Sie können Daten von anderen Systemen in [!DNL Audience Manager] verfügbar machen. Unser System kann Ihnen helfen, Werte zu entsperren und Benutzerdaten zu nutzen, die Sie zuvor gesammelt haben. Dazu gehören Informationen zu Käufen, Umfragen von Kunden, Registrierungsdaten, [!DNL CRM]-Datenbanken usw. Obwohl jede Integration ihre eigenen Herausforderungen darstellt, teilen sie alle diese gemeinsamen Schritte. Lesen Sie sich dieses Material durch, um den Aufwand für die Online-Nutzung Ihrer Offlinedaten zu reduzieren.

## Schritt 1: Benutzer-IDs synchronisieren

Bei der Synchronisierung weist [!DNL Audience Manager] Kunden und ihren Benutzern eindeutige IDs zu. Diese IDs werden als [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) bzw. [!UICONTROL Unique User ID] ([!UICONTROL UUID]) bezeichnet. [!DNL Audience Manager] verwendet das  [!UICONTROL DPID] und  [!UICONTROL UUID] um Benutzer zu identifizieren und sie für  [!UICONTROL traits]-,  [!UICONTROL segments]-, Audiencen- und Berichte-Gruppen zu qualifizieren. Darüber hinaus sucht unser Datenerfassungscode ([!UICONTROL DIL]) nach diesen IDs, um Besucher-Daten von Ihrer Website zu erfassen. Wenn dieser Schritt abgeschlossen ist, sollten [!DNL Audience Manager] und Ihr Offline-Repository für jeden Benutzerdatensatz entsprechende IDs enthalten.

Wichtige Überlegungen zu diesem Schritt:

* **Platzierung der Client-ID:** [!DNL Audience Manager] Sie müssen wissen, wo Ihre Client-ID auf Ihrer Website angezeigt wird (z. B. in einem Cookie, einer Analytics-Variablen, im Seiten-Code usw.).
* **Ausschließen  [!DNL PII]:** Benutzer-IDs dürfen keine personenbezogenen Informationen enthalten ([!DNL PII]).
* **Groß- und Kleinschreibung und Inhaltsempfindlichkeit:** Bei einer Echtzeit-Datensynchronisierung  [!DNL Audience Manager] müssen Benutzer-IDs, die von Ihrer Site erfasst werden, den von Ihrem Offline-Repository weitergeleiteten IDs entsprechen. Wenn z. B. Offline-Datensätze Informationen über [!DNL User123] enthalten, diese ID jedoch von Ihrer Site als [!DNL USER123] gerendert wird, sieht [!DNL Audience Manager] diese Besucher als unterschiedliche. Daher können Online-Informationen für diesen Besucher nicht mit den entsprechenden Datensätzen in Ihrer Offlinedatenbank verknüpft werden. IDs müssen exakt übereinstimmen.

Siehe [ID-Synchronisierung für eingehende Datenübertragungen](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Schritt 2: Datendateiformat

Dateinamen und Inhalte folgen strikten Richtlinien. Sie müssen *den Namen* eingeben und die Datendateien gemäß diesen Spezifikationen in diesem Handbuch organisieren. Siehe:

* [Anforderungen an Namen der über Amazon S3 eingehenden Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhalt der eingehenden Datendatei: Syntax, Variablen und Beispiele](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online-Daten stehen für Offline-Marketingbemühungen zur Verfügung

Wenn Sie Offlinedaten online stellen, können Sie diese Informationen weiterhin für Offline-Kampagnen verwenden. Dazu exportiert [!DNL Audience Manager] Eigenschaften- und Segmentinformationen an einen [!DNL FTP]- oder [!DNL Amazon S3]-Speicherort Ihrer Wahl. Wenden Sie sich für weitere Informationen oder Unterstützung an Ihren Partner Solutions Manager.

## Umgebung

[!DNL Audience Manager] stellt die folgenden Umgebung für das Ablegen von Dateien bereit:

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

## Weitere technische Lesung

Systemingenieure, Entwickler oder technische/Implementierungsteams sollten den [Stapeldatenübermittlungsprozess, beschrieben](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) und die anderen Artikel in diesem Abschnitt überprüfen. Diese Artikel enthalten Details zu Übertragungsprotokollen, Dateiinhalten und Dateinamenanforderungen.

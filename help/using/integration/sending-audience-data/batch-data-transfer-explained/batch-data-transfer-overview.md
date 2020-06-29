---
description: Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in den Audience Manager bringen möchten.
keywords: inbound, batch, batch upload, batch data
seo-description: Eine Übersicht für technische und nicht-technische Kunden, die Daten aus anderen Systemen (offline) in den Audience Manager bringen möchten. Verwenden Sie dazu die Option zum Hochladen von Stapeln in Audience Manager.
seo-title: Stapeldaten an Audience Manager senden - Übersicht
solution: Audience Manager
title: Stapeldaten an Audience Manager senden - Übersicht
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 3%

---


# Stapeldaten an [!DNL Audience Manager] Übersicht senden {#send-batch-data-to-audience-manager-overview}

Eine Übersicht für technische und nicht-technische Kunden, die Daten von anderen Systemen (offline) in [!DNL Audience Manager]einbringen möchten.

## Vorteile

Sie können Daten aus anderen Systemen in bereitstellen [!DNL Audience Manager]. Unser System kann Ihnen helfen, Werte zu entsperren und Benutzerdaten zu nutzen, die Sie zuvor gesammelt haben. Dazu gehören Informationen zu Käufen, Umfragen von Kunden, Registrierungsdaten, [!DNL CRM] Datenbanken usw. Obwohl jede Integration ihre eigenen Herausforderungen darstellt, teilen sie alle diese gemeinsamen Schritte. Lesen Sie sich dieses Material durch, um den Aufwand für die Online-Nutzung Ihrer Offlinedaten zu reduzieren.

## Schritt 1: Benutzer-IDs synchronisieren

Weist während der Synchronisierung Kunden und ihren Benutzern eindeutige IDs zu. [!DNL Audience Manager] Diese IDs werden als [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) bzw. [!UICONTROL Unique User ID] ([!UICONTROL UUID]) bezeichnet. [!DNL Audience Manager] verwendet das [!UICONTROL DPID] und [!UICONTROL UUID] , um Benutzer zu identifizieren und sie für [!UICONTROL traits], [!UICONTROL segments], Audiencen und Berichte zu qualifizieren. Darüber hinaus sucht unser Datenerfassungscode ([!UICONTROL DIL]) nach diesen IDs, um Besucher-Daten von Ihrer Website zu erfassen. Wenn dieser Schritt abgeschlossen ist [!DNL Audience Manager] und Ihr Offline-Repository für jeden Benutzerdatensatz entsprechende IDs enthalten sollte.

Wichtige Überlegungen zu diesem Schritt:

* **Platzierung der Client-ID:** [!DNL Audience Manager] muss wissen, wo Ihre Client-ID auf Ihrer Website angezeigt wird (z. B. in einem Cookie, einer Analytics-Variablen, im Seitencode usw.).
* **Ausschließen[!DNL PII]:** Benutzer-IDs dürfen keine personenbezogenen Informationen enthalten ([!DNL PII]).
* **Groß- und Kleinschreibung und Inhaltsempfindlichkeit:** Während einer Echtzeit-Datensynchronisierung müssen Benutzer-IDs, die von Ihrer Site erfasst werden, den IDs entsprechen, die von Ihrem Offline-Repository weitergegeben werden. [!DNL Audience Manager] Wenn z. B. Offlinedokumente Informationen über [!DNL User123]die ID enthalten, diese aber von Ihrer Site als [!DNL USER123]dargestellt wird, werden sie als unterschiedliche Besucher [!DNL Audience Manager] betrachtet. Daher können Online-Informationen für diesen Besucher nicht mit den entsprechenden Datensätzen in Ihrer Offlinedatenbank verknüpft werden. IDs müssen exakt übereinstimmen.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Schritt 2: Datendateiformat

Dateinamen und Inhalte folgen strikten Richtlinien. Sie *müssen* Datendateien entsprechend den Spezifikationen in diesem Handbuch benennen und organisieren. Siehe:

* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhalt der eingehenden Datendatei: Syntax, Variablen und Beispiele](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online-Daten stehen für Offline-Marketingbemühungen zur Verfügung

Wenn Sie Offlinedaten online stellen, können Sie diese Informationen weiterhin für Offline-Kampagnen verwenden. Exportiert dazu Eigenschaften- und Segmentinformationen [!DNL Audience Manager] an einen [!DNL FTP] oder [!DNL Amazon S3] einen Ort Ihrer Wahl. Wenden Sie sich für weitere Informationen oder Unterstützung an Ihren Partner Solutions Manager.

## Umgebung

[!DNL Audience Manager] stellt die folgenden Umgebung für das Ablegen von Dateien bereit:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Umgebung </th> 
   <th colname="col02" class="entry"> Diensleistung </th> 
   <th colname="col2" class="entry"> Position </th> 
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

Systemingenieure, Entwickler oder technische/Implementierungsteams sollten den beschriebenen [Batch-Datenübertragungsprozess und die anderen Artikel in diesem Abschnitt lesen](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) . Diese Artikel enthalten Details zu Übertragungsprotokollen, Dateiinhalten und Dateinamenanforderungen.

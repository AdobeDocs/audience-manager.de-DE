---
description: Eine Übersicht für technische und nicht technische Kunden, die Daten von anderen Systemen (offline) in Audience Manager einfügen möchten.
keywords: Inbound, Batch, Batch-Upload, Batch-Daten
seo-description: Eine Übersicht für technische und nicht technische Kunden, die Daten von anderen Systemen (offline) in Audience Manager einfügen möchten. Verwenden Sie dazu die Option Batch-Upload in Audience Manager.
seo-title: Stapeldaten an den Audience Manager-Überblick senden
solution: Audience Manager
title: Stapeldaten an den Audience Manager-Überblick senden
uuid: 472583 b 1-5057-4 add -8 e 3 c -5 e 50762 c 88 e 0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# Stapeldaten an den Audience Manager-Überblick senden{#send-batch-data-to-audience-manager-overview}

Eine Übersicht für technische und nicht technische Kunden, die Daten von anderen Systemen (offline) in Audience Manager einfügen möchten.

## Vorteile

<!-- c_offline_to_online.xml -->

Sie können Daten von anderen Systemen in Audience Manager bereitstellen. Unser System kann Ihnen dabei helfen, den Wert zu entsperren und Benutzerdaten zu nutzen, die Sie zuvor gesammelt haben. Dazu gehören Informationen über Käufe, Kundenumfragen, Registrierungsdaten, [!DNL CRM] Datenbanken usw. Während jede Integration ihre eigenen Herausforderungen darstellt, geben sie diese allgemeinen Schritte frei. Lesen Sie dieses Material, um den Aufwand zu verringern, der für die Online-Nutzung Ihrer Offline-Daten erforderlich ist.

## Schritt 1: Benutzer-IDs synchronisieren

Während der Synchronisierung weist Audience Manager Kunden und ihren Benutzern eindeutige IDs zu. Diese IDs werden als [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) bzw. [!UICONTROL Unique User ID] ([!UICONTROL UUID]) bezeichnet. Audience Manager verwendet das und [!UICONTROL DPID][!UICONTROL UUID] zur Identifizierung von Benutzern und qualifiziert sie für Eigenschaften, Segmente, Zielgruppen und Berichte. Darüber hinaus sucht unser Datenerfassungscode ([!UICONTROL DIL]) nach diesen IDs, um Besucherdaten von Ihrer Website zu erfassen. Wenn dieser Schritt abgeschlossen ist, sollten Audience Manager und Ihr Offline-Repository für jeden Benutzerdatensatz entsprechende IDs enthalten.

Wichtige Überlegungen zu diesem Schritt:

* **Client-ID-Platzierung:** Audience Manager muss wissen, wo Ihre Client-ID auf Ihrer Website angezeigt wird (z. B. in einem Cookie, einer Analytics-Variablen, in Seiten-Code usw.).
* **Ausschließen[!DNL PII]:** Benutzer-IDs dürfen keine personenbezogenen identifizierbaren Informationen enthalten ([!DNL PII]).
* **Groß- und Kleinschreibung und Inhaltssensibilität:** Während einer Echtzeit-Datensynchronisierung müssen Benutzer-IDs, die von Audience Manager aus Ihrer Site erfasst wurden, mit IDs übereinstimmen, die aus Ihrem Offline-Repository übergeben werden. Wenn z. B. Offline-Datensätze Informationen enthalten, [!DNL User123]Ihre Site aber diese ID rendert, [!DNL USER123]sieht der Audience Manager diese als unterschiedliche Besucher. Somit können Online-Informationen für diesen Besucher nicht mit den entsprechenden Datensätzen in Ihrer Offline-Datenbank verknüpft werden. IDs müssen exakt übereinstimmen.

See [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## Schritt 2: Datendateiformat

Dateinamen und Inhalte folgen den strengen Richtlinien. Sie *müssen* Datendateien gemäß diesen Spezifikationen in diesem Handbuch benennen und organisieren. Siehe:

* [Namensanforderungen von Amazon S3 für Inbound-Datendateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhalt der eingehenden Datendatei: Syntax, Variablen und Beispiele](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online-Daten stehen für Offline-Marketingbemühungen zur Verfügung.

Wenn Sie Offline-Daten online einbinden, können Sie diese Informationen weiterhin für Offline-Kampagnen verwenden. Dazu exportiert Audience Manager Eigenschaften und Segmentinformationen an einen [!DNL FTP] oder an [!DNL Amazon S3] einen Ort Ihrer Wahl. Wenden Sie sich an Ihren Partner Solutions Manager, um weitere Informationen oder Hilfe zu erhalten.

## Umgebungen

Audience Manager bietet die folgenden Umgebungen für die Dateidropdown-Funktion:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Umgebung </th> 
   <th colname="col02" class="entry"> Dienst </th> 
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
   <td colname="col2"> <p> <code> demdex-s 2 s-client-sandbox-us-east -1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Weitere technische Informationen

Systemaktualisierer, Entwickler oder technische/Implementierungsteams sollten [die Batch-Datenübertragungsprozesse und die](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) anderen Artikel in diesem Abschnitt überprüfen. Diese Artikel enthalten Details zu Übertragungsprotokollen, Dateiinhalten und Dateinamensanforderungen.
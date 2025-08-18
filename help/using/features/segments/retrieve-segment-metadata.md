---
description: Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, werden diese Objekte mit numerischen IDs identifiziert. Wenn Sie als Datenpartner diese Informationen mit Ihren Kunden teilen (oder selbst damit arbeiten), bieten ein tatsächlicher Name und eine Beschreibung ein besseres Erlebnis für Kunden in Berichten, Dashboards oder anderen Benutzeroberflächen (UI). Datenpartner können diese benutzerfreundlichen Namen ihren Kunden entweder mit den in diesem Abschnitt beschriebenen manuellen oder automatisierten Methoden zur Verfügung stellen.
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: Abrufen von Segmentmetadaten
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# Abrufen von Segmentmetadaten {#retrieving-segment-metadata}

Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, werden diese Objekte mit numerischen IDs identifiziert. Wenn Sie als Datenpartner diese Informationen mit Ihren Kunden teilen (oder selbst damit arbeiten), bieten ein tatsächlicher Name und eine Beschreibung ein besseres Erlebnis für Kunden in Berichten, Dashboards oder anderen Benutzeroberflächen ([!DNL UI]). Datenpartner können diese benutzerfreundlichen Namen ihren Kunden entweder mit den in diesem Abschnitt beschriebenen manuellen oder automatisierten Methoden zur Verfügung stellen.

## Manuelle Methode {#manual-method}

Als Datenpartner sind Sie wahrscheinlich daran gewöhnt, Zielgruppen-Metadaten von Ihren Kunden durch manuelle Prozesse zu erhalten. Dazu können Dateien gehören, die an E-Mails angehängt sind oder von Kunden stammen, die diese Daten über eine [!DNL UI] hinzufügen, die Sie zu diesem Zweck erstellt und gepflegt haben. Diese Prozesse funktionieren, sind jedoch häufig umständlich, zeitaufwendig und erfordern möglicherweise eine manuelle Dateneingabe. Diese Methoden werden häufig verwendet, um eine Integration schnell einzurichten und auszuführen, bieten aber auf lange Sicht nicht das beste Kundenerlebnis. Alternativ können Sie den [!DNL Audience Manager]-[!DNL API] verwenden, um Segmentmetadaten automatisch abzurufen.

## Automatisierte Methode {#automated-method}

[!DNL Audience Manager] bietet eine Reihe von [REST-APIs](../../api/rest-api-main/rest-api-main.md) mit denen Sie Segmentmetadaten automatisch abrufen können. Mit dem [!DNL API] können Sie Aufträge erstellen, die Segmentmetadaten in terminierten Intervallen oder automatisch abrufen, wenn Sie [!DNL Audience Manager] verarbeiten und eine neue Segment-ID finden. Weitere Informationen finden Sie in den folgenden Schritten.

### Schritt 1: Überprüfen Sie die Audience Manager-APIs

Der [Erste Schritte mit REST-](../../api/rest-api-main/aam-api-getting-started.md)&quot; enthält Informationen zu allgemeinen Anforderungen, Authentifizierung, verfügbaren Methoden usw. Dies ist ein guter Ausgangspunkt, wenn Sie noch nie mit dem [!DNL Audience Manager] [!DNL API] gearbeitet haben.

### Schritt 2: OAuth2-Zugriffsberechtigungen anfordern

Sie benötigen eine Client-ID und ein Geheimnis, um [!DNL API] Aufrufe durchzuführen. Sie können während des Einrichtungsprozesses für die Integration eine Client-ID und ein Geheimnis von Ihrem Integrationsspezialisten erhalten. Sie können auch eine E-Mail-Anfrage an [!UICONTROL Audience Manager Customer Care] unter [!DNL amsupport@adobe.com] senden.

### Schritt 3: Erfassen kundenspezifischer Informationen von jedem integrierten Kunden

Fordern Sie bei jedem integrierten Kunden Folgendes an:

* Benutzername: Dies ist für einen eingeschränkten Benutzer, der über schreibgeschützte Berechtigungen für das Ziel verfügt, das mit einer bestimmten Integration verknüpft ist.
* Kennwort: Das Benutzerkennwort.
* Ziel-ID : Dies ist die ID (eine Ganzzahl), die mit dem Ziel verknüpft ist, das für die bestimmte Server-zu-Server-Integration erstellt wurde.

### Schritt 4: Abrufen von Segmentmetadaten mit einem API-Aufruf

Nachdem Sie die vorherigen Schritte abgeschlossen haben, können Sie eine `GET`-Methode verwenden, um Segmentmetadaten abzurufen. Eine Beispielanfrage und -antwort finden Sie unter [Rückgabe von Zielzuordnungen](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Dieser Aufruf gibt Segmentdaten zurück, die als Schlüssel-Wert-Paare in einem [!DNL JSON]-Objekt formatiert sind. Einige der wichtigen Segmentattribute, die in der Antwort zurückgegeben werden, sind in der folgenden Tabelle aufgeführt.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>Die <span class="keyword"> Audience Manager</span> Segment-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>Der Segmentname. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>Ein Text, der das Segment kurz beschreibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>Der aktuelle Status der Segmentzuordnung. Zu den zurückgegebenen Statusoptionen gehören: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

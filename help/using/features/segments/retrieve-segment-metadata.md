---
description: Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, werden diese Objekte mit numerischen IDs identifiziert. Wenn Sie diese Informationen als Datenpartner für Ihre Kunden freigeben (oder selbst mit ihnen arbeiten), erhalten Sie einen tatsächlichen Namen und eine Beschreibung für Kunden in Berichten, Dashboards oder anderen Benutzeroberflächen (UI). Datenpartner können diese Anzeigenamen ihren Kunden entweder mit manuellen oder automatisierten Methoden zur Verfügung stellen, die in diesem Abschnitt beschrieben sind.
seo-description: Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, werden diese Objekte mit numerischen IDs identifiziert. Wenn Sie diese Informationen als Datenpartner für Ihre Kunden freigeben (oder selbst mit ihnen arbeiten), erhalten Sie einen tatsächlichen Namen und eine Beschreibung für Kunden in Berichten, Dashboards oder anderen Benutzeroberflächen (UI). Datenpartner können diese Anzeigenamen ihren Kunden entweder mit manuellen oder automatisierten Methoden zur Verfügung stellen, die in diesem Abschnitt beschrieben sind.
seo-title: Abrufen von Segmentmetadaten
solution: Audience Manager
title: Abrufen von Segmentmetadaten
uuid: 719 e 2 c 41-8788-4 e 8 a -967 a-e 367421 f 9 f 84
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Retrieving Segment Metadata {#retrieving-segment-metadata}

Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, werden diese Objekte mit numerischen IDs identifiziert. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces ([!DNL UI]). Datenpartner können diese Anzeigenamen ihren Kunden entweder mit manuellen oder automatisierten Methoden zur Verfügung stellen, die in diesem Abschnitt beschrieben sind.

## Manual method {#manual-method}

Als Datenpartner werden Sie wahrscheinlich dazu verwendet, Zielgruppenmetadaten über manuelle Prozesse von Ihren Kunden abzurufen. This could include files attached to emails or from customers adding that data through a [!DNL UI] you've built and maintained for this purpose. Diese Prozesse funktionieren, sind aber oft mühsam, zeitraubend und erfordern möglicherweise manuelle Dateneingaben. Diese Methoden dienen häufig dazu, eine Integration schnell und schnell zu ermöglichen, bieten jedoch langfristig nicht das beste Kundenerlebnis. As an alternative, you can use the [!DNL Audience Manager] [!DNL API] to get segment metadata automatically.

## Automated method {#automated-method}

[!DNL Audience Manager] bietet eine Reihe [von REST-apis](../../api/rest-api-main/rest-api-main.md) , mit denen Sie Segmentmetadaten automatisch abrufen können. With the [!DNL API], you can create jobs that retrieve segment metadata at scheduled intervals or automatically, whenever you process [!DNL Audience Manager] data and find a new segment ID. Weitere Informationen finden Sie unter unten.

### Schritt 1: Überprüfen der Audience Manager-apis

The [Getting Started with REST APIs](../../api/rest-api-main/aam-api-getting-started.md) section contains information about general requirements, authentication, available methods, etc. This is a good place to begin if you haven't worked with the [!DNL Audience Manager] [!DNL API] before.

### Schritt 2: Anmeldedaten für oauth 2 anfordern

You need a client ID and secret to make [!DNL API] calls. Während des Integrationssetups können Sie eine Client-ID und ein geheimer Schlüssel von Ihrem Integrationsspezialisten abrufen. You can also send an email request to [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com].

### Schritt 3: Erfassen kundenspezifischer Informationen aus allen integrierten Kunden

Fordern Sie Folgendes von jedem integrierten Kunden an:

* Benutzername: Dies gilt für einen eingeschränkten Benutzer, der über schreibgeschützte Berechtigungen für das Ziel verfügt, das einer bestimmten Integration zugeordnet ist.
* Kennwort: Das Benutzerkennwort.
* Ziel-ID: Dies ist die ID (eine Ganzzahl), die dem Ziel zugeordnet ist, das für die spezifische Server-zu-Server-Integration erstellt wurde.

### Schritt 4: Segmentmetadaten mit einem API-Aufruf abrufen

After completing the previous steps, you can use a `GET` method to retrieve segment metadata. For a sample request and response, see [Return Destination Mappings](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). This call returns segment data formatted as key-value pairs in a [!DNL JSON] object. Einige der wichtigen Segmentattribute, die in der Antwort zurückgegeben werden, sind in der folgenden Tabelle aufgeführt.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Destinationmappingid</code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager</span> segment ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementname</code> </p> </td> 
   <td colname="col2"> <p>Der Segmentname. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementdescription</code> </p> </td> 
   <td colname="col2"> <p>Ein Text, der das Segment kurz beschreibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Elementstatus</code> </p> </td> 
   <td colname="col2"> <p>Der aktuelle Status der Segmentzuordnung. Zu den zurückgegebenen Statusoptionen gehören: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> aktiv</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inaktiv</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> gelöscht</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
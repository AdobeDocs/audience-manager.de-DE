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


# Abrufen von Segmentmetadaten {#retrieving-segment-metadata}

Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, werden diese Objekte mit numerischen IDs identifiziert. Wenn Sie diese Informationen als Datenpartner für Ihre Kunden freigeben (oder selbst mit ihnen arbeiten), erhalten Sie einen tatsächlichen Namen und eine Beschreibung für Kunden in Berichten, Dashboards oder anderen Benutzeroberflächen ([!DNL UI]). Datenpartner können diese Anzeigenamen ihren Kunden entweder mit manuellen oder automatisierten Methoden zur Verfügung stellen, die in diesem Abschnitt beschrieben sind.

## Manuelle Methode {#manual-method}

Als Datenpartner werden Sie wahrscheinlich dazu verwendet, Zielgruppenmetadaten über manuelle Prozesse von Ihren Kunden abzurufen. Dazu gehören Dateien, die an E-Mails angehängt wurden, oder von Kunden, die diese Daten durch eine [!DNL UI] erstellt und gepflegt haben. Diese Prozesse funktionieren, sind aber oft mühsam, zeitraubend und erfordern möglicherweise manuelle Dateneingaben. Diese Methoden dienen häufig dazu, eine Integration schnell und schnell zu ermöglichen, bieten jedoch langfristig nicht das beste Kundenerlebnis. Alternativ können Sie die Option [!DNL Audience Manager][!DNL API] zum automatischen Abrufen von Segmentmetadaten verwenden.

## Automatisierte Methode {#automated-method}

[!DNL Audience Manager] bietet eine Reihe [von REST-apis](../../api/rest-api-main/rest-api-main.md) , mit denen Sie Segmentmetadaten automatisch abrufen können. Mit diesem [!DNL API]können Sie Aufträge erstellen, die Segmentmetadaten in geplanten Intervallen oder automatisch abrufen, sobald Sie Daten verarbeiten [!DNL Audience Manager] und eine neue Segment-ID finden. Weitere Informationen finden Sie unter unten.

### Schritt 1: Überprüfen der Audience Manager-apis

Der Abschnitt [Erste Schritte mit REST apis](../../api/rest-api-main/aam-api-getting-started.md) enthält Informationen zu allgemeinen Anforderungen, Authentifizierung, verfügbaren Methoden usw. Dies ist ein guter Ort, um zu beginnen, wenn Sie noch nicht mit dem Vorigen [!DNL Audience Manager][!DNL API] gearbeitet haben.

### Schritt 2: Anmeldedaten für oauth 2 anfordern

Für Aufrufe benötigen Sie eine Client-ID und einen [!DNL API] geheimen Schlüssel. Während des Integrationssetups können Sie eine Client-ID und ein geheimer Schlüssel von Ihrem Integrationsspezialisten abrufen. Sie können eine E-Mail-Anfrage auch an [!UICONTROL Audience Manager Customer Care] at [!DNL amsupport@adobe.com]. senden.

### Schritt 3: Erfassen kundenspezifischer Informationen aus allen integrierten Kunden

Fordern Sie Folgendes von jedem integrierten Kunden an:

* Benutzername: Dies gilt für einen eingeschränkten Benutzer, der über schreibgeschützte Berechtigungen für das Ziel verfügt, das einer bestimmten Integration zugeordnet ist.
* Kennwort: Das Benutzerkennwort.
* Ziel-ID: Dies ist die ID (eine Ganzzahl), die dem Ziel zugeordnet ist, das für die spezifische Server-zu-Server-Integration erstellt wurde.

### Schritt 4: Segmentmetadaten mit einem API-Aufruf abrufen

Nach Abschluss der vorherigen Schritte können Sie die Segmentmetadaten mit einer `GET` Methode abrufen. Eine Beispielanforderung und eine Antwort finden Sie unter [Zuordnungen von Zielzielen](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Dieser Aufruf gibt Segmentdaten zurück, die als Schlüssel-Wert-Paare in einem [!DNL JSON] Objekt formatiert sind. Einige der wichtigen Segmentattribute, die in der Antwort zurückgegeben werden, sind in der folgenden Tabelle aufgeführt.

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
   <td colname="col2"> <p>Die Segment-ID <span class="keyword"> des Audience Manager</span> . </p> </td> 
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
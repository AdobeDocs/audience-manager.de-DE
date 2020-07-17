---
description: Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, identifiziert er diese Objekte mit numerischen IDs. Wenn Sie als Datenpartner diese Informationen an Ihre Kunden weitergeben (oder selbst daran arbeiten), bieten ein tatsächlicher Name und eine Beschreibung eine bessere Kundenerfahrung in Berichten, Dashboards oder anderen Benutzeroberflächen (UI). Datenpartner können diese Anzeigenamen ihren Kunden entweder mit den in diesem Abschnitt beschriebenen manuellen oder automatisierten Methoden zur Verfügung stellen.
seo-description: Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, identifiziert er diese Objekte mit numerischen IDs. Wenn Sie als Datenpartner diese Informationen an Ihre Kunden weitergeben (oder selbst daran arbeiten), bieten ein tatsächlicher Name und eine Beschreibung eine bessere Kundenerfahrung in Berichten, Dashboards oder anderen Benutzeroberflächen (UI). Datenpartner können diese Anzeigenamen ihren Kunden entweder mit den in diesem Abschnitt beschriebenen manuellen oder automatisierten Methoden zur Verfügung stellen.
seo-title: Abrufen von Segmentmetadaten
solution: Audience Manager
title: Abrufen von Segmentmetadaten
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 1%

---


# Abrufen von Segmentmetadaten {#retrieving-segment-metadata}

Wenn Audience Manager Segmentinformationen an einen Datenpartner sendet, identifiziert er diese Objekte mit numerischen IDs. Wenn Sie als Datenpartner diese Informationen an Ihre Kunden weitergeben (oder selbst daran arbeiten), bieten ein tatsächlicher Name und eine Beschreibung eine bessere Kundenerfahrung in Berichten, Dashboards oder anderen Benutzeroberflächen ([!DNL UI]). Datenpartner können diese Anzeigenamen ihren Kunden entweder mit den in diesem Abschnitt beschriebenen manuellen oder automatisierten Methoden zur Verfügung stellen.

## Manuelle Methode {#manual-method}

Als Datenpartner sind Sie wahrscheinlich daran gewöhnt, Audiencen-Metadaten von Ihren Kunden über manuelle Prozesse zu erhalten. Dies kann Dateien umfassen, die an E-Mails oder von Kunden angehängt werden, die diese Daten über eine von [!DNL UI] Ihnen zu diesem Zweck erstellte und verwaltete Datei hinzufügen. Diese Prozesse funktionieren, sind aber oft umständlich und zeitaufwendig und erfordern möglicherweise eine manuelle Dateneingabe. Diese Methoden werden häufig verwendet, um eine Integration schnell zu implementieren, bieten aber langfristig nicht die beste Kundenerfahrung. Alternativ können Sie die verwenden, [!DNL Audience Manager] um Segmentmetadaten automatisch abzurufen [!DNL API] .

## Automatisierte Methode {#automated-method}

[!DNL Audience Manager] bietet eine Reihe von [REST-APIs](../../api/rest-api-main/rest-api-main.md) , mit denen Sie Segmentmetadaten automatisch abrufen können. Mit der [!DNL API]können Sie Aufträge erstellen, die Segmentmetadaten in planmäßigen Intervallen oder automatisch abrufen, sobald Sie Daten verarbeiten [!DNL Audience Manager] und eine neue Segment-ID finden. Weitere Informationen finden Sie in den unten stehenden Schritten.

### Schritt 1: Überprüfen der Audience Manager-APIs

Der Abschnitt [Erste Schritte mit REST-APIs](../../api/rest-api-main/aam-api-getting-started.md) enthält Informationen zu allgemeinen Anforderungen, Authentifizierung, verfügbaren Methoden usw. Das ist ein guter Anfang, wenn Sie noch nicht mit dem [!DNL Audience Manager][!DNL API] vorher gearbeitet haben.

### Schritt 2: Zugriffsberechtigungen für OAuth2 anfordern

Sie benötigen eine Client-ID und ein Geheimnis, um [!DNL API] Aufrufe zu tätigen. Sie können während des Integrationsprozesses eine Client-ID und ein Geheimnis von Ihrem Integrationsspezialisten abrufen. Sie können auch eine E-Mail-Anfrage an [!UICONTROL Audience Manager Customer Care] eine Adresse senden [!DNL amsupport@adobe.com].

### Schritt 3: Erfassen kundenspezifischer Informationen von jedem integrierten Kunden

Fordern Sie bei jedem integrierten Kunden Folgendes an:

* Benutzername: Dies gilt für einen eingeschränkten Benutzer mit schreibgeschützten Berechtigungen für das Ziel, das mit einer bestimmten Integration verknüpft ist.
* Kennwort: Das Benutzerkennwort.
* Ziel-ID: Dies ist die ID (eine Ganzzahl), die mit dem Ziel verknüpft ist, das für die jeweilige Server-zu-Server-Integration erstellt wurde.

### Schritt 4: Abrufen von Segmentmetadaten mit einem API-Aufruf

Nach Abschluss der vorherigen Schritte können Sie eine `GET` Methode zum Abrufen von Segmentmetadaten verwenden. Eine Beispielanforderung und -antwort finden Sie unter Zuordnungen [rückkehrender Ziele](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Dieser Aufruf gibt Segmentdaten zurück, die als Schlüssel-Wert-Paare in einem [!DNL JSON] Objekt formatiert sind. Einige der wichtigen Segmentattribute, die in der Antwort zurückgegeben werden, sind in der folgenden Tabelle aufgeführt.

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
   <td colname="col2"> <p>Die Segment-ID des <span class="keyword"> Audience Managers</span> . </p> </td> 
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
   <td colname="col2"> <p>Der aktuelle Status der Segmentzuordnung. Zu den Rückgabestatusoptionen gehören: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
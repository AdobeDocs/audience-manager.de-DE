---
description: In diesem Dokument werden die technischen Einzelheiten im Zusammenhang mit der Einhaltung der Datenschutzbestimmungen für Audience Manager behandelt.
seo-description: In diesem Dokument werden die technischen Einzelheiten im Zusammenhang mit der Einhaltung der Datenschutzbestimmungen für Audience Manager behandelt.
seo-title: Datenschutzanfragen
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Datenschutzanfragen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 55%

---


# Datenschutzanfragen {#data-privacy-requests}

## Überblick {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

Bevor Sie diesen Artikel lesen, sollten Sie das [DSGVO-Glossar](../data-security-and-privacy/aam-gdpr-glossary.md) und das [CCPA-Glossar](aam-ccpa-glossary.md); einsehen, um die hier verwendete Terminologie besser zu verstehen.

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* Über die [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche. Die Dokumentation finden Sie [hier](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Über die **[!DNL Privacy Service API]**. See the documentation [here](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) and the [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)** section, along with their respective namespace IDs (data source IDs).

[Privacy Service](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html) unterstützt zwei Arten von Anfragen: Datenzugriffs- und Datenlöschanfragen.

## Datenzugriffsanfragen {#access-data}

You can send individual data access requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

In der [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche können Sie neue Vorgangsanfragen entweder mithilfe von [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON]-Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON]-Datei aussieht, können Sie [ eine JSON-Beispieldatei herunterladen](../data-security-and-privacy/assets/access_request.json).

Wir sind uns Ihrer Verpflichtung bewusst, Datenschutzanfragen innerhalb der gesetzlich festgelegten Frist zu erfüllen.

## Datenlöschanfragen {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

In der [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche können Sie neue Vorgangsanfragen entweder mithilfe von [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON]-Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON]-Datei aussieht, können Sie [ eine JSON-Beispieldatei herunterladen](../data-security-and-privacy/assets/access_request.json).

Adobe ist sich Ihrer Verpflichtung bewusst, Datenschutzanfragen von Kunden innerhalb von 30 Tagen zu erfüllen. For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

When you send declared IDs, such as cross device [!DNL CRM] IDs or [!DNL cookie] IDs, in data privacy requests, [!DNL Audience Manager] will perform the necessary deletion on all the linked devices (up to 100 devices per declared ID).

[!DNL Audience Manager] versucht, Aktivierungspartner über Löschanfragen zu benachrichtigen, indem Informationen zum Aufheben der Segmentierung für betroffene Personen gesendet werden, die das Löschen bestimmter Daten anfordern. Allerdings können einige Aktivierungspartner:

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

Download our [Partner Excel sheet](assets/AAM-Partners-October2019.xlsx) to see which [!DNL Audience Manager] activation partners support unsegment.

## Opt-out-Anfragen {#opt-out-requests}

[!DNL Audience Manager] unterstützt branchenweite Standards für das Opt-out-Management. Read on for complete information on the types of opt-out supported by [!DNL Audience Manager].

While data access and deletion requests are handled through the [Privacy Service](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html), opt-out requests are currently supported through the [!DNL DCS API]. Read on to learn what the opt-out [!DNL API] calls should look like.

### Globale Opt-out-Anfragen

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. In der folgenden Tabelle werden die Methoden für das globalen Opt-out-Verfahren angezeigt:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-out für </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>Auf der <a href="https://www.adobe.com/de/privacy/opt-out.html#customeruse" format="http" scope="external">Seite „Ihre Datenschutzoptionen“</a> finden Sie 1-Klick-Funktionen, mit denen Ihre Endbenutzer die Datenerfassung durch die Adobe Experience Cloud-Werbelösungen (einschließlich Audience Manager) steuern und deaktivieren können. Weitere Informationen finden Sie im Abschnitt hinsichtlich <a href="https://www.adobe.com/de/privacy/opt-out.html#customeruse" format="http" scope="external"> Geschäftskunden</a> auf der Seite „Ihre Datenschutzoptionen“. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkte API-Aufrufe an Audience Manager </p> </td> 
   <td colname="col2"> <p>Ihre Benutzer können die Datenerfassung durch alle Audience Manager-Marken deaktivieren, indem Sie unten die DCS-API aufrufen und die <a href="../../reference/ids-in-aam.md"> Audience Manager-Benutzer-ID </a> einschließen: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Daraufhin setzen wir die <code>demdex=NOTARGET</code>- und <code>dextp=NOTARGET</code>-Cookies für die gesendete Audience Manager-Benutzer-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte </p> </td> 
   <td colname="col2"> <p>Siehe Opt-out- und Datenschutzeinstellungen für: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/de-DE/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-Geräte </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/de-DE/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-Geräte </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Ihre Endbenutzer können sich auch von der globalen Datenerfassung abmelden, indem Sie die Websites unserer Partner für Industriestandards besuchen.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Nach den oben beschriebenen Opt-out-Anfragen:

* [!DNL Audience Manager] beendet die Datenerfassung, Segmentierung oder Aktivierung, solange der Benutzer seine Browsercookies nicht löscht.
* Historische Daten werden nach 120 Tagen aus dem Benutzerprofil entfernt.

### Opt-out auf Partnerebene mit erklärten ID-Aufrufen

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

Nach einem Opt-out auf Partnerebene mit einem deklarierten ID-Aufruf:

* Die [CRM-ID](../../reference/ids-in-aam.md) wird aus der Datenerfassung ausgeschlossen.
* Die letzte Geräte-ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)), die mit der [CRM-ID](../../reference/ids-in-aam.md) verknüpft ist, wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] beendet alle Datenerfassung, Segmentierung oder Aktivierung für die [!DNL CRM] ID und die letzte Geräte-ID, die mit der [!DNL CRM] ID verknüpft ist;
* [!DNL Audience Manager] Aufhebung der Segmentierung der Ausschluss- [!DNL CRM] ID und der letzten Geräte-ID aus allen Segmenten;
* [!UICONTROL Destination] Partner erhalten die Nicht-Segment-Anforderung für die [!DNL CRM] ID und die letzte Geräte-ID. Die Aufhebung der Segmentierung funktioniert sowohl für [Echtzeit-](data-privacy-requests.md#aam-partners-with-unsegmentation) als auch für Batch-Ziele.
* Es werden keine historischen Daten gelöscht.

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

Für eine deklarierte ID können Sie eine Opt-out-Anfrage mit den `d_cid`- und `d_cid_ic`-Schlüssel-Wert-Paaren erstellen. Die veralten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

#### Ausschluss mit [!DNL CID] und [!DNL CID_IC]

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Opt-out über | Code-Beispiel |
|--- |--- |
| Eine Datenanbieter-ID und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Einen Integrations-Code und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Mehrere `d_cid` und `d_cid_ic` Schlüssel/Wert-Paare. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out auf Partnerebene mit Geräte-ID-Aufrufen

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. Sie können sich von der Datenerfassung für eine bestimmte Geräte-ID für eine Marke abmelden, indem Sie die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) wie folgt aufrufen:

| Opt-out über | Code-Beispiel |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Eine [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Weitere Information über `uuid`, `mid` und `imsOrgId` finden Sie im [Index der IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Nach einem Opt-out auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] beendet die Datenerfassung, Segmentierung oder Aktivierung für den Partner für die Geräte-ID.
* [!DNL Audience Manager] die Segmentierung der Geräte-ID aus allen Segmenten aufheben;
* Zielpartner erhalten die Anfrage zur Aufhebung der Segmentierung für die Geräte-ID. Die Aufhebung der Segmentierung funktioniert sowohl für [Echtzeit-](data-privacy-requests.md#aam-partners-with-unsegmentation) als auch für Batch-Ziele.
* Es werden keine historischen Daten gelöscht.

## [!DNL Audience Manager] Partner mit Unsegmentierungsfunktionen {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

Allerdings können einige der Aktivierungspartner:

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

Consult the [list of device-based destinations](/help/using/features/destinations/device-based-destinations-list.md) to see which [!DNL Audience Manager] activation partners support unsegment.

## Datenkorrekturanfragen {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] Kunden können die relevanten Signale/Eigenschaften/Segmente gegen Profil von Benutzern erfassen und diese Informationen über die [Offline-Datenerfassung](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an senden [!DNL Audience Manager]. Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.

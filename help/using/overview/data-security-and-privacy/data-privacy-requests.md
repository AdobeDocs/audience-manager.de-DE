---
description: In diesem Dokument werden die technischen Einzelheiten im Zusammenhang mit der Einhaltung der Datenschutzbestimmungen für Audience Manager behandelt.
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: DSGVO-Benutzeroberfläche, DSGVO-API, CCPA, Datenschutz
title: Datenschutzanfragen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1444'
ht-degree: 48%

---

# Datenschutzanfragen {#data-privacy-requests}

## Überblick {#overview}

Dieses Dokument bietet einen Überblick über die Verwaltung individueller Datenschutz- und Opt-out-Anfragen, die Sie an senden können [!DNL Audience Manager] durch [Privacy Service-Benutzeroberfläche](https://privacyui.cloud.adobe.io/) und **[!DNL Privacy Service API]**.

Mit diesen Tools können Sie Datenschutzanfragen von Verbrauchern senden, die unter [!DNL GDPR] und [!DNL CCPA].

Bevor Sie diesen Artikel lesen, sollten Sie das [DSGVO-Glossar](../data-security-and-privacy/aam-gdpr-glossary.md) und das [CCPA-Glossar](aam-ccpa-glossary.md); einsehen, um die hier verwendete Terminologie besser zu verstehen.

Sie können einzelne Anfragen zum Zugriff auf und zum Löschen von Verbraucherdaten aus senden [!DNL Audience Manager]auf zwei Arten:

* Über die [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche. Die Dokumentation finden Sie [hier](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Über die **[!DNL Privacy Service API]**. Weitere Informationen finden Sie in der Dokumentation [here](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) und [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Beim Senden individueller Datenschutzanfragen können Sie jede [!DNL Audience Manager] Kennungen (IDs), wie im Abschnitt **[Audience Manager-IDs](data-privacy-ids.md)** zusammen mit den entsprechenden Namespace-IDs (Datenquellen-IDs).

[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) unterstützt zwei Arten von Anfragen: Datenzugriffs- und Datenlöschanfragen.

## Datenzugriffsanfragen {#access-data}

Sie können individuelle Datenzugriffsanfragen über die [Privacy Service-Benutzeroberfläche](https://privacyui.cloud.adobe.io) (Dokumentation [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) oder durch Aufruf der Privacy Service-API (Dokumentation) [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) und [!DNL API] reference [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

In der [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche können Sie neue Vorgangsanfragen entweder mithilfe von [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON]-Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON]-Datei aussieht, können Sie [ eine JSON-Beispieldatei herunterladen](../data-security-and-privacy/assets/access_request.json).

Wir sind uns Ihrer Verpflichtung bewusst, Datenschutzanfragen innerhalb der gesetzlich festgelegten Frist zu erfüllen.

## Datenlöschanfragen  {#delete-data}

Sie können Datenlöschanfragen über die [Privacy Service-Benutzeroberfläche](https://privacyui.cloud.adobe.io) (Dokumentation [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) oder durch Aufruf der Privacy Service-API (Dokumentation) [here](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) und [!DNL API] reference [here](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

In der [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche können Sie neue Vorgangsanfragen entweder mithilfe von [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON]-Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON]-Datei aussieht, können Sie [ eine JSON-Beispieldatei herunterladen](../data-security-and-privacy/assets/access_request.json).

Adobe ist sich Ihrer Verpflichtung bewusst, Datenschutzanfragen von Kunden innerhalb von 30 Tagen zu erfüllen. Aus diesem Grund [!DNL Adobe] verpflichtet sich, Ihre Datenlöschanfrage so bald wie möglich zu verarbeiten.

Als Antwort auf Ihre Anfragen zum Löschen von Verbraucherdaten [!DNL Audience Manager] löscht Eigenschaften und Segmente, die mit dem [!DNL Audience Manager] Kennung, die in der Anfrage enthalten ist. Darüber hinaus wird die [!DNL Audience Manager] Kennungen für die Person, die sich von der weiteren Datenerfassung durch [!DNL Audience Manager] und die entsprechenden ID-Zuordnungen entfernt werden.

Wenn Sie deklarierte IDs senden, z. B. geräteübergreifende [!DNL CRM] IDs oder [!DNL cookie] IDs in Datenschutzanfragen, [!DNL Audience Manager] führt den erforderlichen Löschvorgang auf allen verknüpften Geräten durch (bis zu 100 Geräte pro deklarierter ID).

[!DNL Audience Manager] versucht, Aktivierungspartner über Löschanfragen zu benachrichtigen, indem Informationen zum Aufheben der Segmentierung für betroffene Personen gesendet werden, die das Löschen bestimmter Daten anfordern. Allerdings können einige Aktivierungspartner:

1. Es können keine Aufheben der Segmentierung (oder Entfernen von Segmentanforderungen aus [!DNL Audience Manager] und/oder
2. keine Aktualisierungen von erhalten können [!DNL Audience Manager] mit einer Häufigkeit von weniger als 30 Tagen. In diesen Fällen [!DNL Audience Manager] -Kunden können Löschanfragen nicht automatisiert an Aktivierungspartner senden, indem sie [!DNL Audience Manager].

In diesen Fällen können Sie Löschanfragen nicht automatisiert an Aktivierungspartner senden, indem Sie [!DNL Audience Manager].

Lesen Sie diesbezüglich auch unsere [Dokumentation zu gerätebasierten Zielen](assets/AAM-Partners-October2019.xlsx) zu sehen, [!DNL Audience Manager] Aktivierungspartner unterstützen die Aufhebung der Segmentierung.

## Opt-out-Anfragen {#opt-out-requests}

[!DNL Audience Manager] unterstützt branchenweite Standards für das Opt-out-Management. Umfassende Informationen zu den von [!DNL Audience Manager].

Während Datenzugriffs- und Löschanfragen über das [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en), werden Opt-out-Anfragen derzeit über die [!DNL DCS API]. Informationen zum Opt-out [!DNL API] -Aufrufe sollten so aussehen.

### Globale Opt-out-Anfragen

Das globale Opt-out stellt ein Opt-out-Verfahren für alle [!DNL Audience Manager] und andere [!DNL Adobe Experience Cloud] Lösungen für alle Marken. In der folgenden Tabelle werden die Methoden für das globalen Opt-out-Verfahren angezeigt:

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
   <td colname="col2"> <p>Auf der <a href="https://www.adobe.com/de/privacy/opt-out.html#customeruse" format="http" scope="external">Seite „Ihre Datenschutzoptionen“</a> finden Sie 1-Klick-Funktionen, mit denen Ihre Endbenutzer die Datenerfassung durch die Adobe Experience Cloud-Werbelösungen (einschließlich Audience Manager) steuern und deaktivieren können. Weitere Informationen finden Sie im Abschnitt hinsichtlich <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Geschäftskunden</a> auf der Seite „Ihre Datenschutzoptionen“. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkte API-Aufrufe an Audience Manager </p> </td> 
   <td colname="col2"> <p>Ihre Benutzer können die Datenerfassung durch alle Audience Manager-Marken deaktivieren, indem Sie unten die DCS-API aufrufen und die <a href="../../reference/ids-in-aam.md"> Audience Manager-Benutzer-ID </a> einschließen: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Daraufhin setzen wir die <code>demdex=NOTARGET</code>- und <code>dextp=NOTARGET</code>-Cookies für die gesendete Audience Manager-Benutzer-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte </p> </td> 
   <td colname="col2"> <p>Siehe Opt-out- und Datenschutzeinstellungen für: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-Geräte </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-Geräte </a> </li> 
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

Mit dem Opt-out auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte [!DNL Audience Manager] Partner. Sie können Opt-out-Anfragen auf Partnerebene für geräteübergreifende IDs senden, einschließlich [!DNL CRM] IDs und gehashte E-Mail-Adressen.

Nach einem Opt-out auf Partnerebene mit einem deklarierten ID-Aufruf:

* Die [CRM-ID](../../reference/ids-in-aam.md) wird aus der Datenerfassung ausgeschlossen.
* Die letzte Geräte-ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)), die mit der [CRM-ID](../../reference/ids-in-aam.md) verknüpft ist, wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] wird die Datenerfassung, Segmentierung oder Aktivierung für die [!DNL CRM] ID und die letzte Geräte-ID, die mit der [!DNL CRM] Kennung;
* [!DNL Audience Manager] Aufhebung der Segmentierung des Opt-out [!DNL CRM] ID und letzte Geräte-ID aus allen Segmenten;
* [!UICONTROL Destination] -Partner erhalten die Anforderung zum Aufheben der Segmentierung für die [!DNL CRM] ID und letzte Geräte-ID. Die Aufhebung der Segmentierung funktioniert sowohl für [Echtzeit-](data-privacy-requests.md#aam-partners-with-unsegmentation) als auch für Batch-Ziele.
* Es werden keine historischen Daten gelöscht.

Wann [!DNL Audience Manager] eine Opt-out-Anfrage auf Partnerebene erhält, wird die [!DNL JSON] zurückgegeben von [!DNL DCS] enthält die [Fehlercode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)mit der Nachricht [!UICONTROL "Encountered opt out tag"], anstatt der [!DNL Audience Manager] Benutzer-ID.

Für eine deklarierte ID können Sie eine Opt-out-Anfrage mit den `d_cid`- und `d_cid_ic`-Schlüssel-Wert-Paaren erstellen. Die veralten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

#### Opt-out mit [!DNL CID] und [!DNL CID_IC]

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Opt-out über | Code-Beispiel |
|--- |--- |
| Eine Datenanbieter-ID und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Einen Integrations-Code und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Mehrere  `d_cid`  und  `d_cid_ic`  Schlüssel-Wert-Paare. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out auf Partnerebene mit Geräte-ID-Aufrufen

Mit dem Opt-out auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte [!DNL Audience Manager] Partner. Sie können sich von der Datenerfassung für eine bestimmte Geräte-ID für eine Marke abmelden, indem Sie die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) wie folgt aufrufen:

| Opt-out über | Code-Beispiel |
|--- |--- |
| Ein [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Ein [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Weitere Information über `uuid`, `mid` und `imsOrgId` finden Sie im [Index der IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Nach einem Opt-out auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] beendet die Datenerfassung, Segmentierung oder Aktivierung für den Partner für die Geräte-ID.
* [!DNL Audience Manager] hebt die Segmentierung der Geräte-ID für alle Segmente auf;
* Zielpartner erhalten die Anfrage zur Aufhebung der Segmentierung für die Geräte-ID. Die Aufhebung der Segmentierung funktioniert sowohl für [Echtzeit-](data-privacy-requests.md#aam-partners-with-unsegmentation) als auch für Batch-Ziele.
* Es werden keine historischen Daten gelöscht.

## [!DNL Audience Manager] Partner mit Unsegmentierungsfunktionen {#aam-partners-with-unsegmentation}

Um Sie bei der Automatisierung Ihrer Datenschutzanfragen für Verbraucher zu unterstützen, [!DNL Audience Manager] versucht, Aktivierungspartner über Löschanfragen von betroffenen Personen zu informieren, indem sie ihnen Informationen zur Aufhebung der Segmentierung (oder zum Entfernen der Segmentierung) senden.

Allerdings können einige der Aktivierungspartner:

1. Anfragen zur Aufhebung der Segmentierung können nicht unterstützt werden von [!DNL Audience Manager] und/oder
2. keine Aktualisierungen von erhalten können [!DNL Audience Manager] häufiger als einmal in 30 Tagen.

In diesen Fällen können Sie Löschanfragen nicht automatisiert an Aktivierungspartner senden, indem Sie [!DNL Audience Manager].

Lesen Sie die [Liste gerätebasierter Ziele](/help/using/features/destinations/device-based-destinations-list.md) zu sehen, [!DNL Audience Manager] Aktivierungspartner unterstützen die Aufhebung der Segmentierung.

## Datenkorrekturanfragen {#correction}

Da [!DNL Audience Manager] nicht die Quelle der Daten ist, gibt es eine begrenzte Rolle für die Datenkorrektur in [!DNL Audience Manager]. Die Berichtigung könnte bedeuten, dass der Verbraucher beantragt hat, entweder von einer falschen [!UICONTROL trait]/[!UICONTROL segment] oder für die gewünschte [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] Kunden können die relevanten Signale/Eigenschaften/Segmente anhand von Benutzerprofilen erfassen und diese Informationen über [Offline-Datenerfassung](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) nach [!DNL Audience Manager]. Bitte beachten Sie, dass der Benutzer weiterhin für das Original qualifiziert wird. [!UICONTROL trait] und [!UICONTROL segments] wenn sie ihr Verhalten wiederholen.

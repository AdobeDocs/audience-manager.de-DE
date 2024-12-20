---
description: In diesem Dokument werden die technischen Einzelheiten im Zusammenhang mit der Einhaltung der Datenschutzbestimmungen für Audience Manager behandelt.
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: DSGVO-BENUTZEROBERFLÄCHE, DSGVO-API, CCPA, Datenschutz
title: Datenschutzanfragen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: 6b43885deddb0cdaeb3698051ea110f0a4eed44e
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 42%

---

# Datenschutzanfragen {#data-privacy-requests}

## Überblick {#overview}

Dieses Dokument bietet einen Überblick über die Verwaltung von individuellen Datenschutz- und Opt-out-Anfragen, die Sie über die [Privacy Service-Benutzeroberfläche und die **[!DNL Privacy Service API]** an [!DNL Audience Manager] ](https://privacyui.cloud.adobe.io/) können.

Mit diesen Tools können Sie Datenschutzanfragen von Privatkunden senden, die unter [!DNL GDPR] und [!DNL CCPA] gestellt wurden.

Bevor Sie diesen Artikel lesen, sollten Sie das [DSGVO-Glossar](../data-security-and-privacy/aam-gdpr-glossary.md) und das [CCPA-Glossar](aam-ccpa-glossary.md); einsehen, um die hier verwendete Terminologie besser zu verstehen.

Sie können individuelle Anfragen für den Zugriff auf und das Löschen von Verbraucherdaten aus [!DNL Audience Manager] auf zwei Arten stellen:

* Über die [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche. Die Dokumentation finden Sie [hier](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Über die **[!DNL Privacy Service API]**. Weitere Informationen finden Sie in [ Dokumentation ](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en)hier) und der [!DNL API]-Referenz [hier](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

Beim Senden einzelner Datenschutzanfragen können Sie beliebige [!DNL Audience Manager] (IDs) zusammen mit den entsprechenden Namespace-IDs (Datenquellen-IDs) übermitteln, wie ](data-privacy-ids.md)**Abschnitt**[ Audience Manager-IDs} beschrieben.

[Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) unterstützt zwei Arten von Anfragen: Datenzugriffs- und Datenlöschanfragen.

## Anfragen zum Datenzugriff {#access-data}

Einzelne Datenzugriffsanfragen können über die [Privacy Service-Benutzeroberfläche gesendet werden](https://privacyui.cloud.adobe.io) (Dokumentation [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) oder durch Aufruf der Privacy Service-API (Dokumentation [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) und [!DNL API] Referenz [hier](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

In der [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche können Sie neue Vorgangsanfragen entweder mithilfe von [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON]-Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON]-Datei aussieht, können Sie [ eine JSON-Beispieldatei herunterladen](../data-security-and-privacy/assets/access_request.json).

Wir sind uns Ihrer Verpflichtung bewusst, Datenschutzanfragen innerhalb der gesetzlich festgelegten Frist zu erfüllen.

## Anfragen zum Löschen von Daten {#delete-data}

Sie können Anfragen zum Löschen von Daten über die [Privacy Service-Benutzeroberfläche senden](https://privacyui.cloud.adobe.io) (Dokumentation [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) oder durch Aufruf der Privacy Service-API (Dokumentation [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) und [!DNL API] Referenz [hier](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

In der [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche können Sie neue Vorgangsanfragen entweder mithilfe von [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON]-Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON]-Datei aussieht, können Sie [ eine JSON-Beispieldatei herunterladen](../data-security-and-privacy/assets/access_request.json).

Adobe ist sich Ihrer Verpflichtung bewusst, Datenschutzanfragen von Kunden innerhalb von 30 Tagen zu erfüllen. [!DNL Adobe] verpflichtet sich daher, Ihre Anfrage zur Datenlöschung so schnell wie möglich zu bearbeiten.

Als Reaktion auf Ihre Löschanfragen von Verbraucherdaten löscht [!DNL Audience Manager] Eigenschaften und Segmente, die mit der in der Anfrage enthaltenen [!DNL Audience Manager]-Kennung verknüpft sind. Darüber hinaus werden die jeweiligen [!DNL Audience Manager] Kennungen für die Person, die sich von der weiteren Datenerfassung durch [!DNL Audience Manager] abgemeldet hat, und die jeweiligen ID-Zuordnungen entfernt.

Wenn Sie in Datenschutzanfragen deklarierte IDs wie geräteübergreifende [!DNL CRM]-IDs oder [!DNL cookie]-IDs senden, führt [!DNL Audience Manager] die erforderliche Löschung auf allen verknüpften Geräten durch (bis zu 100 Geräte pro deklarierter ID).

[!DNL Audience Manager] versuchen, Aktivierungspartner über Löschanfragen zu informieren, indem ihnen Informationen zur Aufhebung der Segmentierung für betroffene Personen gesendet werden, die eine Löschung bestimmter Daten anfordern. Allerdings können einige Aktivierungspartner:

1. Segmentaufhebungsanfragen (oder Segmententfernungsanfragen) können nicht von [!DNL Audience Manager] und/oder unterstützt werden.
2. Sie können keine Updates von [!DNL Audience Manager] mit einer Häufigkeit von weniger als 30 Tagen erhalten. In diesen Fällen können [!DNL Audience Manager]-Kunden keine Löschanfragen an Aktivierungspartner senden, wenn diese über [!DNL Audience Manager] automatisiert werden.

In diesen Fällen können Sie keine Löschanfragen automatisch über [!DNL Audience Manager] an Aktivierungspartner senden.

Weitere Informationen dazu, welche [!DNL Audience Manager] Aktivierungspartner die Aufhebung der Segmentierung unterstützen[ finden Sie in ](assets/AAM-Partners-October2019.xlsx) Dokumentation zur Liste der gerätebasierten Ziele .

## Opt-out-Anfragen {#opt-out-requests}

[!DNL Audience Manager] unterstützt branchenweite Standards in Bezug auf das Opt-out-Management. Im Folgenden finden Sie vollständige Informationen zu den von [!DNL Audience Manager] unterstützten Arten von Opt-outs.

Während Datenzugriffs- und Löschanfragen über den [Privacy Service ](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) verarbeitet werden, werden Opt-out-Anfragen derzeit über den [!DNL DCS API] unterstützt. Lesen Sie weiter, um zu erfahren, wie die Opt-out-[!DNL API] aussehen sollten.

### Globale Opt-out-Anfragen

Die globale Abmeldung stellt eine [!DNL Audience Manager] und andere [!DNL Adobe Experience Cloud] Lösungen für alle Marken dar. In der folgenden Tabelle werden die Methoden für das globalen Opt-out-Verfahren angezeigt:

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

* [!DNL Audience Manager] werden jegliche Datenerfassung, Segmentierung oder Aktivierung einstellen, solange der Nutzer seine Browser-Cookies nicht löscht.
* Historische Daten werden nach 120 Tagen aus dem Benutzerprofil entfernt.

### Opt-out auf Partnerebene mit erklärten ID-Aufrufen

Mit dem Opt-out auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte [!DNL Audience Manager] abmelden. Sie können Opt-out-Anfragen auf Partnerebene für geräteübergreifende IDs senden, einschließlich [!DNL CRM]-IDs und Hash-E-Mail-Adressen.

Nach einem Opt-out auf Partnerebene mit einem deklarierten ID-Aufruf:

* Die [CRM-ID](../../reference/ids-in-aam.md) wird aus der Datenerfassung ausgeschlossen.
* Die letzte Geräte-ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)), die mit der [CRM-ID](../../reference/ids-in-aam.md) verknüpft ist, wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] werden künftig sämtliche Datenerfassungs-, Segmentierungs- oder Aktivierungsvorgänge für die [!DNL CRM]-ID und die letzte mit der [!DNL CRM]-ID verknüpfte Geräte-ID einstellen;
* [!DNL Audience Manager] hebt die Segmentierung der abgemeldeten [!DNL CRM]-ID und der letzten Geräte-ID aus allen Segmenten auf;
* [!UICONTROL Destination] Partner erhalten die Anfrage zur Aufhebung der Segmentierung für die [!DNL CRM]-ID und die letzte Geräte-ID. Die Aufhebung der Segmentierung funktioniert sowohl für [Echtzeit-](data-privacy-requests.md#aam-partners-with-unsegmentation) als auch für Batch-Ziele.
* Es werden keine historischen Daten gelöscht.

Wenn [!DNL Audience Manager] eine Opt-out-Anfrage auf Partnerebene erhält, enthält die vom [!DNL DCS] zurückgegebene [!DNL JSON] den [Fehlercode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes) mit der [!UICONTROL "Encountered opt out tag"] Nachricht anstelle der [!DNL Audience Manager] Benutzer-ID.

Für eine deklarierte ID können Sie eine Opt-out-Anfrage mit den `d_cid`- und `d_cid_ic`-Schlüssel-Wert-Paaren erstellen. Die veralten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

#### Opt-out mit [!DNL CID] und [!DNL CID_IC]

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Opt-out über | Code-Beispiel |
|--- |--- |
| Eine Datenanbieter-ID und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Einen Integrations-Code und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Mehrere `d_cid` und `d_cid_ic` Schlüssel-Wert-Paare. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out auf Partnerebene mit Geräte-ID-Aufrufen

Mit dem Opt-out auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte [!DNL Audience Manager] abmelden. Sie können sich von der Datenerfassung für eine bestimmte Geräte-ID für eine Marke abmelden, indem Sie die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) wie folgt aufrufen:

| Opt-out über | Code-Beispiel |
|--- |--- |
| Ein [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Eine [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Weitere Information über `uuid`, `mid` und `imsOrgId` finden Sie im [Index der IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Nach einem Opt-out auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] werden künftig für die Geräte-ID sämtliche Datenerfassungs-, Segmentierungs- oder Aktivierungsvorgänge für den Partner einstellen.
* [!DNL Audience Manager] hebt die Segmentierung der Geräte-ID für alle Segmente auf;
* Zielpartner erhalten die Anfrage zur Aufhebung der Segmentierung für die Geräte-ID. Die Aufhebung der Segmentierung funktioniert sowohl für [Echtzeit-](data-privacy-requests.md#aam-partners-with-unsegmentation) als auch für Batch-Ziele.
* Es werden keine historischen Daten gelöscht.

## [!DNL Audience Manager] Partner mit Nicht-Segmentierungsfunktionen {#aam-partners-with-unsegmentation}

Um Sie bei der Automatisierung Ihrer Datenschutzanfragen an Privatkunden zu unterstützen, versuchen [!DNL Audience Manager], Aktivierungspartner über Löschanfragen von betroffenen Personen zu informieren, indem sie Informationen zur Aufhebung der Segmentierung (oder zum Entfernen von Segmenten) erhalten.

Allerdings können einige der Aktivierungspartner:

1. Aufheben von Segmentanforderungen von [!DNL Audience Manager] und/oder kann nicht unterstützt werden
2. Sie können in 30 Tagen nicht häufiger als einmal Aktualisierungen von [!DNL Audience Manager] erhalten.

In diesen Fällen können Sie keine Löschanfragen automatisch über [!DNL Audience Manager] an Aktivierungspartner senden.

Lesen Sie die [Liste der gerätebasierten Ziele](/help/using/features/destinations/device-based-destinations-list.md) um zu sehen, welche [!DNL Audience Manager] Aktivierungspartner die Aufhebung der Segmentierung unterstützen.

## Datenkorrekturanfragen {#correction}

Da [!DNL Audience Manager] nicht die Quelle der Daten ist, kommt der Datenkorrektur in [!DNL Audience Manager] nur eine begrenzte Rolle zu. Die Berichtigung könnte bedeuten, dass der Verbraucher entweder beantragt hat, von einer falschen [!UICONTROL trait]/[!UICONTROL segment] ausgeschlossen zu werden, oder dass er sich für die gewünschte [!UICONTROL trait]/[!UICONTROL segment] qualifiziert hat.

[!DNL Audience Manager] Kunden können sich dafür entscheiden, die relevanten Signale/Eigenschaften/Segmente anhand von Benutzerprofilen zu erfassen und diese Informationen über [Offline-Datenaufnahme](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an [!DNL Audience Manager] zu senden. Bitte beachten Sie, dass der/die Benutzende weiterhin zum ursprünglichen [!UICONTROL trait] qualifiziert wird und [!UICONTROL segments], wenn er/sie sein/ihr Verhalten wiederholt.

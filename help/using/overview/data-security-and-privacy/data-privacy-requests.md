---
description: In diesem Dokument werden die technischen Einzelheiten im Zusammenhang mit der Einhaltung der Datenschutzbestimmungen für Audience Manager behandelt.
seo-description: In diesem Dokument werden die technischen Einzelheiten im Zusammenhang mit der Einhaltung der Datenschutzbestimmungen für Audience Manager behandelt.
seo-title: Datenschutzanforderungen
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Datenschutzanforderungen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Datenschutzanforderungen {#data-privacy-requests}

## Überblick {#overview}

In diesem Dokument erhalten Sie einen Überblick über die Verwaltung individueller Datenschutzanforderungen und Abmeldeanfragen, die Sie über die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Datenschutzdienstes und die Benutzeroberfläche **[!DNL Privacy Service API]** an Audience Manager senden können.

Mit diesen Tools können Sie Anfragen zum Datenschutz von Verbraucherdaten senden, die im Rahmen von GDPR und CCPA gestellt werden.

Bevor Sie diesen Artikel lesen, sollten Sie das Glossar [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) und das [CCPA Glossar](aam-ccpa-glossary.md)durchlaufen, um die hier verwendete Terminologie besser zu verstehen.

Sie können individuelle Anforderungen zum Zugriff auf und Löschen von Verbraucherdaten aus Audience Manager auf zwei Arten senden:

* Über die Benutzeroberfläche des [Datenschutzdienstes](https://privacyui.cloud.adobe.io/). Die Dokumentation finden Sie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Durch die **[!DNL Privacy Service API]**. Die Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) und die API-Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Beim Senden individueller Datendatenschutzanforderungen können Sie alle Audience Manager-IDs (IDs), wie im Abschnitt **[Audience Manager-IDs](data-privacy-ids.md)**beschrieben, zusammen mit den entsprechenden Namensraum-IDs (Datenquellen-IDs) senden.

Der [Datenschutzdienst](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) unterstützt zwei Arten von Anforderungen: Anforderungen zum Datenzugriff und zum Löschen von Daten.

## Datenzugriffsanforderungen {#access-data}

Sie können individuelle Datenzugriffsanfragen über die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Datenschutzdienstes (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) oder durch Aufruf der [!DNL Privacy Service API] (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) und [!DNL API] Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) senden.

Die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Datenschutzdienstes ermöglicht Ihnen, neue Auftragsanforderungen entweder mithilfe des [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON] Datei zu erstellen.

Um zu sehen, wie eine gültige [!DNL JSON] Datei aussieht, können Sie eine JSON-Musterdatei [herunterladen](../data-security-and-privacy/assets/access_request.json).

Wir verstehen Ihre Verpflichtung, Ihre Datenschutzanforderungen innerhalb der gesetzlich festgelegten Frist zu erfüllen.

## Datenlöschungsanforderungen{#delete-data}

Sie können Datenlöschungsanfragen über die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Datenschutzdienstes ( [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)Dokumentation) oder durch Aufruf der [!DNL Privacy Service API] (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) und API-Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) senden.

Die Benutzeroberfläche [des](https://privacyui.cloud.adobe.io/) Datenschutzdienstes ermöglicht Ihnen, neue Auftragsanforderungen entweder mithilfe des [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON] Datei zu erstellen.

Um zu sehen, wie eine gültige [!DNL JSON] Datei aussieht, können Sie eine JSON-Musterdatei [herunterladen](../data-security-and-privacy/assets/access_request.json).

Adobe versteht Ihr Eintreten für die Einhaltung der Datenschutzanforderungen von Kunden innerhalb von 30 Tagen. Aus diesem Grund ist Adobe verpflichtet, Ihre Anforderung zum Löschen von Daten so schnell wie möglich zu bearbeiten.

Als Antwort auf Ihre Anforderungen zum Löschen von Kundendaten löscht Audience Manager Eigenschaften und Segmente, die mit der Audience Manager-ID in der Anforderung verknüpft sind. Darüber hinaus werden die jeweiligen Audience Manager-IDs für die von Audience Manager aus der weiteren Datenerfassung ausgenommene Person und die entsprechenden ID-Zuordnungen entfernt.

Wenn Sie deklarierte IDs, wie z. B. geräteübergreifende [!DNL CRM] IDs oder Cookie-IDs, in Datenschutzanforderungen senden, führt Audience Manager den erforderlichen Löschvorgang auf allen verknüpften Geräten durch (bis zu 100 Geräte pro deklarierter ID).

Audience Manager versucht, die Aktivierung-Partner über Löschungsanfragen zu benachrichtigen, indem er ihnen Segmentinformationen für Datensubjekte sendet, die das Löschen bestimmter Daten anfordern. Einige Partnereinrichtungen der Aktivierung:

1. Segmentanforderungen vom Audience Manager können nicht unterstützt (oder entfernt) und/oder
2. sind nicht in der Lage, Updates von Audience Manager mit einer Häufigkeit von weniger als 30 Tagen zu erhalten. In diesen Fällen sind Audience Manager-Kunden nicht in der Lage, Löschanforderungen automatisch über Audience Manager an Aktivierungen-Partner zu senden.

In diesen Fällen ist es nicht möglich, Löschanforderungen automatisch über Audience Manager an Aktivierung-Partner zu senden.

Laden Sie sich unser [Partner-Excel-Blatt](assets/AAM-Partners-October2019.xlsx) herunter, um zu sehen, welche Audience Manager-Aktivierung-Partner Segmentunterschiede unterstützen.

## Abmeldeanforderungen {#opt-out-requests}

Audience Manager unterstützt branchenweite Standards für das Opt-out-Management. Lesen Sie für vollständige Informationen zu den von Audience Manager unterstützten Abmeldearten.

Während Datenzugriffs- und Löschanforderungen über den [Datenschutzdienst](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)verarbeitet werden, werden Abmeldeanforderungen derzeit über die DCS-API unterstützt. Lesen Sie weiter, um zu erfahren, wie die Ausschluss-API-Aufrufe aussehen sollten.

### Globale Abmeldeanforderungen

Das globale Opt-out stellt eine Abmeldung für alle Audience Manager- und anderen Adobe Experience Cloud-Lösungen für alle Marken dar. In der folgenden Tabelle werden die Methoden für die globale Abmeldung Liste:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Abmeldung für </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>Auf der Seite <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> "Datenschutzoptionen" </a> stehen 1-Klick-Funktionen zur Verfügung, mit denen Endbenutzer die Datenerfassung durch die Adobe Experience Cloud-Werbesysteme (einschließlich Audience Manager) steuern und abwählen können. Weitere Informationen finden Sie im Abschnitt zum <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Geschäftskunden </a> auf der Seite "Datenschutzoptionen". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkte API-Aufrufe an Audience Manager </p> </td> 
   <td colname="col2"> <p>Ihre Benutzer können die Datenerfassung durch alle Audience Manager-Marken deaktivieren, indem Sie unten die DCS API aufrufen und die <a href="../../reference/ids-in-aam.md"> Audience Manager-Benutzer-ID einschließen </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Daher werden Cookies für die gesendete Audiencen-Manager-Benutzer-ID festgelegt <code>demdex=NOTARGET</code> und <code>dextp=NOTARGET</code> gesetzt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte </p> </td> 
   <td colname="col2"> <p>Siehe Ausschluss- und Datenschutzeinstellungen für: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-Geräte </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-Geräte </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Ihre Endbenutzer können die globale Datenerfassung auch Opt-out, indem sie die Websites unserer Partner für Industriestandards besuchen.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Befolgen Sie die oben beschriebenen Abmeldeanfragen:

* Audience Manager beendet die Datenerfassung, Segmentierung oder Aktivierung, solange der Benutzer seine Browsercookies nicht löscht.
* Historische Daten werden nach 120 Tagen aus dem Profil entfernt.

### Abmeldeoption auf Partnerebene mit erklärten ID-Aufrufen

Mit der Abmeldung auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte Audience Manager-Partner ausschließen. Sie können Abmeldeanfragen auf Partnerebene für geräteübergreifende IDs, einschließlich CRM-IDs und Hash-E-Mail-Adressen, senden.

Nach einer Abmeldung auf Partnerebene mit einem deklarierten ID-Aufruf:

* Die [CRM-ID](../../reference/ids-in-aam.md) wird aus der Datenerfassung ausgeschlossen.
* Die letzte Geräte-ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)), die mit der [CRM-ID](../../reference/ids-in-aam.md) verknüpft ist, wird aus der Datenerfassung ausgeschlossen.
* Audience Manager beendet die Datenerfassung, Segmentierung oder Aktivierung für die CRM-ID und die letzte Geräte-ID, die mit der CRM-ID verknüpft ist.
* Audience Manager hebt die Segmentierung der Ausschluss-CRM-ID und der letzten Geräte-ID aus allen Segmenten auf.
* Zielpartner erhalten die Nicht-Segment-Anforderung für die CRM-ID und die letzte Geräte-ID. Die Segmentierung funktioniert sowohl für [Echtzeit](data-privacy-requests.md#aam-partners-with-unsegmentation) - als auch für Stapelziele.
* Es werden keine Verlaufsdaten gelöscht.

Wenn Audience Manager eine Abmeldeanforderung auf Partnerebene erhält, enthält die vom DCS zurückgegebene JSON den [Fehlercode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)mit der Meldung [!UICONTROL "Encountered opt out tag"], nicht die Audience Manager-Benutzer-ID.

Sie können eine deklarierte ID-Abmeldeanforderung mit den Paaren `d_cid` und dem Schlüssel- `d_cid_ic` -Wert erstellen. Die alten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Ausschluss mit CID und CID_IC

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine Datenanbieter-ID und Benutzer-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Ein Integrationscode und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Mehrere Schlüssel-Wert-Paare d_cid und d_cid_ic. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Ausschluss auf Partnerebene mit Geräte-ID-Aufrufen

Mit der Abmeldung auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte Audience Manager-Partner ausschließen. Sie können die Datenerfassung für eine bestimmte Geräte-ID für eine Marke deaktivieren, indem Sie die folgenden Aufrufe an die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)richten:

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine eindeutige Audience-Manager-Benutzer-ID (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Eine Experience Cloud ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Mehr über `uuid`und `mid` im `imsOrgId` IDs-Index in Audience Manager [](/help/using/reference/ids-in-aam.md).

Nach einer Abmeldung auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte-ID wird aus der Datenerfassung ausgeschlossen.
* Audience Manager beendet die Datenerfassung, Segmentierung oder Aktivierung für den Partner und setzt die Geräte-ID in Zukunft ein.
* Audience Manager hebt die Segmentierung der Geräte-ID aus allen Segmenten auf.
* Zielpartner erhalten die Anforderung zum Entfernen des Segments für die Geräte-ID. Die Segmentierung funktioniert sowohl für [Echtzeit](data-privacy-requests.md#aam-partners-with-unsegmentation) - als auch für Stapelziele.
* Es werden keine Verlaufsdaten gelöscht.

## Audience Manager verfügt über Unsegmentierungsfunktionen {#aam-partners-with-unsegmentation}

Um Ihnen bei der Automatisierung Ihrer Verbraucherdatendatenschutzanforderungen zu helfen, versucht Audience Manager, die Aktivierung-Partner über Löschungsanfragen von Datensubjekten zu informieren, indem sie die Segmentinformationen vom Segment trennen (oder entfernen).

Einige unserer Partner in der Aktivierung:

1. Nicht-Segmentanforderungen von Audience Manager können nicht unterstützt werden und/oder
2. sind nicht in der Lage, Aktualisierungen von Audience Manager häufiger als einmal in 30 Tagen zu erhalten.

In diesen Fällen ist es nicht möglich, Löschanforderungen automatisch über Audience Manager an Aktivierung-Partner zu senden.

Prüfen Sie die [Liste der gerätebasierten Ziele](/help/using/features/destinations/device-based-destinations-list.md) , um zu sehen, welche Audience Manager-Aktivierung-Partner Segmentunterschiede unterstützen.

## Datenkorrekturanforderungen {#correction}

Da Audience Manager nicht die Datenquelle ist, ist die Datenkorrektur in Audience Manager eingeschränkt. Die Korrektur könnte bedeuten, dass der Verbraucher entweder beantragt hat, von einer falschen Eigenschaft/einem falschen Segment ausgeschlossen oder für die gewünschte Eigenschaft/das gewünschte Segment qualifiziert zu werden.

Audience Manager Kunden können die relevanten Signale/Eigenschaften/Segmente gegen Profil des Benutzers erfassen und diese Informationen über die [Offline-Datenerfassung](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an Audience Manager senden. Bitte beachten Sie, dass der Benutzer weiterhin für die ursprünglichen Eigenschaften und Segmente qualifiziert ist, wenn er sein Verhalten wiederholt.

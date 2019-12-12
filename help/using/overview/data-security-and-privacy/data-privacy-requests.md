---
description: In diesem Dokument werden die technischen Details im Zusammenhang mit der Einhaltung der Datenschutzbestimmungen für Audience Manager behandelt.
seo-description: In diesem Dokument werden die technischen Details im Zusammenhang mit der Einhaltung der Datenschutzbestimmungen für Audience Manager behandelt.
seo-title: Datenschutzanforderungen
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Datenschutzanforderungen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 09ac547f22bc07e5b8609226ddd736cb79cbc700

---


# Datenschutzanforderungen {#data-privacy-requests}

## Überblick {#overview}

Dieses Dokument bietet einen Überblick über die Verwaltung der individuellen Datenschutzanforderungen und Abmeldeanforderungen, die Sie über die Benutzeroberfläche[ des ](https://gdprui.cloud.adobe.io/)Datenschutzdienstes und über das **[!DNL Privacy Service API]** Dialogfeld an Audience Manager senden können.

Mit diesen Tools können Sie Anfragen zum Datenschutz von Verbraucherdaten senden, die unter GDPR und CCPA gestellt werden.

Bevor Sie diesen Artikel lesen, sollten Sie das Glossar [GDPR](../data-security-and-privacy/aam-gdpr-glossary.md) und das [CCPA Glossar](aam-ccpa-glossary.md)durchlaufen, um die hier verwendete Terminologie besser zu verstehen.

Sie können einzelne Anforderungen auf zwei Arten senden, um auf Benutzerdaten zuzugreifen und sie aus Audience Manager zu löschen:

* Über die Benutzeroberfläche des [Datenschutzdienstes](https://gdprui.cloud.adobe.io/). Die Dokumentation finden Sie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Durch die **[!DNL Privacy Service API]**. Die Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) und die API-Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Beim Senden individueller Datendatenschutzanforderungen können Sie alle Audience Manager-IDs (IDs), wie im Abschnitt **[Audience Manager-IDs](data-privacy-ids.md)** beschrieben, zusammen mit ihren jeweiligen Namespace-IDs (Datenquellen-IDs) senden.

Der [Datenschutzdienst](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) unterstützt zwei Arten von Anforderungen: Anforderungen zum Datenzugriff und zum Löschen von Daten.

## Datenzugriffsanforderungen {#access-data}

Sie können individuelle Datenzugriffsanfragen über die Benutzeroberfläche[ des ](https://gdprui.cloud.adobe.io/)Datenschutzdienstes (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) oder durch Aufruf der [!DNL Privacy Service API] (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) und [!DNL API] Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) senden.

Die Benutzeroberfläche[ des ](https://gdprui.cloud.adobe.io/)Datenschutzdienstes ermöglicht Ihnen, neue Auftragsanforderungen entweder mithilfe des [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON] Datei zu erstellen.

Um zu sehen, wie eine gültige [!DNL JSON] Datei aussieht, können Sie eine JSON-Musterdatei [herunterladen](../data-security-and-privacy/assets/access_request.json).

Wir verstehen Ihre Verpflichtung, Ihre Datenschutzanforderungen innerhalb der gesetzlich festgelegten Frist zu erfüllen.

## Datenlöschungsanforderungen{#delete-data}

Sie können Datenlöschungsanfragen über die Benutzeroberfläche[ des ](https://gdprui.cloud.adobe.io/)Datenschutzdienstes ( [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)Dokumentation) oder durch Aufruf der [!DNL Privacy Service API] (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) und API-Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) senden.

Die Benutzeroberfläche[ des ](https://gdprui.cloud.adobe.io/)Datenschutzdienstes ermöglicht Ihnen, neue Auftragsanforderungen entweder mithilfe des [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON] Datei zu erstellen.

Um zu sehen, wie eine gültige [!DNL JSON] Datei aussieht, können Sie eine JSON-Musterdatei [herunterladen](../data-security-and-privacy/assets/access_request.json).

Adobe versteht Ihre Verpflichtung, Kundenanfragen zum Datenschutz innerhalb von 30 Tagen nach Empfang zu erfüllen. Aus diesem Grund ist Adobe verpflichtet, Ihre Anforderung zum Löschen von Daten so schnell wie möglich zu bearbeiten.

Als Antwort auf Ihre Anforderungen zum Löschen von Benutzerdaten löscht Audience Manager Eigenschaften und Segmente, die mit der Zielgruppen-Manager-ID in der Anforderung verknüpft sind. Darüber hinaus werden die jeweiligen Audience Manager-IDs für die einzelne Person, die von der weiteren Datenerfassung durch Audience Manager ausgeschlossen wurde, und die entsprechenden ID-Zuordnungen entfernt.

Wenn Sie deklarierte IDs, wie z. B. geräteübergreifende [!DNL CRM] IDs oder Cookie-IDs, in Datenschutzanforderungen senden, führt Audience Manager den erforderlichen Löschvorgang auf allen verknüpften Geräten durch (bis zu 100 Geräte pro deklarierter ID).

Audience Manager versucht, Aktivierungspartner über Löschanforderungen zu benachrichtigen, indem er ihnen Segmentinformationen für Datensubjekte sendet, die das Löschen bestimmter Daten anfordern. Einige Aktivierungspartner:

1. Nicht-Segment-Anforderungen aus Audience Manager können nicht unterstützt (oder entfernt) und/oder
2. sind nicht in der Lage, Updates von Audience Manager mit einer Häufigkeit von weniger als 30 Tagen zu erhalten. In diesen Fällen sind Audience Manager-Kunden nicht in der Lage, Löschanforderungen automatisch über Audience Manager an Aktivierungspartner zu senden.

In diesen Fällen ist es nicht möglich, Löschanforderungen automatisch über Audience Manager an Aktivierungspartner zu senden.

Laden Sie sich unser [Partner-Excel-Blatt](assets/AAM-Partners-October2019.xlsx) herunter, um zu sehen, welche Audience Manager-Aktivierungspartner das Segment nicht unterstützen.

## Abmeldeanforderungen {#opt-out-requests}

Audience Manager unterstützt branchenweite Standards für die Abmeldeverwaltung. Lesen Sie für vollständige Informationen zu den von Audience Manager unterstützten Abmeldearten.

Während Datenzugriffs- und Löschanforderungen über den [Datenschutzdienst](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)verarbeitet werden, werden Abmeldeanforderungen derzeit über die DCS-API unterstützt. Lesen Sie weiter, um zu erfahren, wie die Ausschluss-API-Aufrufe aussehen sollten.

### Globale Abmeldeanforderungen

Das globale Ausschluss stellt eine Abmeldung für alle Marken in Audience Manager und anderen Adobe Experience Cloud-Lösungen dar. In der folgenden Tabelle sind die Methoden aufgeführt, die für das globale Ausschluss verwendet werden:

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
   <td colname="col2"> <p>Auf der Seite <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> "Datenschutzoptionen" </a> stehen Funktionen mit einem Klick zur Verfügung, mit denen Endbenutzer die Datenerfassung durch die Adobe Experience Cloud-Anzeigenlösungen (einschließlich Audience Manager) steuern und abwählen können. Weitere Informationen finden Sie im Abschnitt zum <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Geschäftskunden </a> auf der Seite "Datenschutzoptionen". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Direkte API-Aufrufe an Audience Manager </p> </td> 
   <td colname="col2"> <p>Ihre Benutzer können die Datenerfassung durch alle Audience Manager-Marken deaktivieren, indem Sie unten die DCS API aufrufen und die <a href="../../reference/ids-in-aam.md"> Audience Manager-Benutzer-ID einschließen </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Als Ergebnis werden Cookies für die gesendete Audience Manager-Benutzer-ID festgelegt <code>demdex=NOTARGET</code> und <code>dextp=NOTARGET</code> gesetzt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte </p> </td> 
   <td colname="col2"> <p>Siehe Ausschluss- und Datenschutzeinstellungen für: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android-Geräte </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS-Geräte </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Ihre Endbenutzer können sich auch von der globalen Datenerfassung abmelden, indem sie die Websites unserer Partner für Branchenstandards besuchen.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Befolgen Sie die oben beschriebenen Abmeldeanfragen:

* Audience Manager beendet in Zukunft die Datenerfassung, Segmentierung oder Aktivierung, solange der Benutzer seine Browser-Cookies nicht löscht.
* Historische Daten werden nach 120 Tagen aus dem Benutzerprofil entfernt.

### Abmeldung auf Partnerebene mit erklärten ID-Aufrufen

Mit der Abmeldung auf Partnerebene können Sie Benutzer von der Datenerfassung durch bestimmte Audience Manager-Partner ausschließen. Sie können Abmeldeanfragen auf Partnerebene für geräteübergreifende IDs, einschließlich CRM-IDs und Hash-E-Mail-Adressen, senden.

Nach einer Abmeldung auf Partnerebene mit einem deklarierten ID-Aufruf:

* Die [CRM-ID](../../reference/ids-in-aam.md) wird aus der Datenerfassung ausgeschlossen.
* Die letzte Geräte-ID (Unique User ID[für](../../reference/ids-in-aam.md)Audience Manager), die mit der [CRM-ID](../../reference/ids-in-aam.md) verknüpft ist, wird aus der Datenerfassung ausgeschlossen.
* Audience Manager beendet die Datenerfassung, Segmentierung oder Aktivierung für die CRM-ID und die letzte Geräte-ID, die mit der CRM-ID verknüpft ist.
* Audience Manager hebt die Segmentierung der Ausschluss-CRM-ID und der letzten Geräte-ID aus allen Segmenten auf.
* Zielpartner erhalten die Nicht-Segment-Anforderung für die CRM-ID und die letzte Geräte-ID. Die Segmentierung funktioniert sowohl für [Echtzeit](data-privacy-requests.md#aam-partners-with-unsegmentation) - als auch für Stapelziele.
* Es werden keine Verlaufsdaten gelöscht.

Wenn Audience Manager eine Abmeldeanforderung auf Partnerebene erhält, enthält die vom DCS zurückgegebene JSON den [Fehlercode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)mit der Meldung [!UICONTROL "Encountered opt out tag"], nicht die Audience Manager-Benutzer-ID.

Sie können eine deklarierte ID-Abmeldeanforderung mit den Paaren `d_cid` und dem Schlüssel- `d_cid_ic` Wert erstellen. Die alten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Ausschluss mit CID und CID_IC

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine Datenanbieter-ID und Benutzer-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Ein Integrationscode und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Mehrere Schlüssel-Wert-Paare d_cid und d_cid_ic. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Ausschluss auf Partnerebene mit Geräte-ID-Aufrufen

Mit der Abmeldung auf Partnerebene können Sie Benutzer von der Datenerfassung durch bestimmte Audience Manager-Partner ausschließen. Sie können die Datenerfassung für eine bestimmte Geräte-ID für eine Marke deaktivieren, indem Sie die folgenden Aufrufe an die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)richten:

| Ausschluss mit | Codebeispiel |
|--- |--- |
| Eine eindeutige Benutzer-ID für Audience Manager (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Eine Experience Cloud ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Mehr über `uuid`und `mid` im `imsOrgId`ID-Index in Audience Manager[](/help/using/reference/ids-in-aam.md) .

Nach einer Abmeldung auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte-ID wird aus der Datenerfassung ausgeschlossen.
* Audience Manager beendet die Datenerfassung, Segmentierung oder Aktivierung für den Partner und fährt mit der Geräte-ID fort.
* Audience Manager hebt die Segmentierung der Geräte-ID aus allen Segmenten auf.
* Zielpartner erhalten die Anforderung zum Entfernen des Segments für die Geräte-ID. Die Segmentierung funktioniert sowohl für [Echtzeit](data-privacy-requests.md#aam-partners-with-unsegmentation) - als auch für Stapelziele.
* Es werden keine Verlaufsdaten gelöscht.

## Audience Manager-Partner mit Unsegmentierungsfunktionen {#aam-partners-with-unsegmentation}

Um Ihnen bei der Automatisierung Ihrer Anfragen zum Datenschutz zu helfen, versucht Audience Manager, Aktivierungspartner über Löschungsanfragen von Datensubjekten zu benachrichtigen, indem sie diese vom Segment trennen (oder entfernen).

Einige unserer Aktivierungspartner:

1. Nicht segmentbezogene Anforderungen von Audience Manager können nicht unterstützt werden und/oder
2. sind nicht in der Lage, häufiger Updates von Audience Manager als einmal in 30 Tagen zu erhalten.

In diesen Fällen ist es nicht möglich, Löschanforderungen automatisch über Audience Manager an Aktivierungspartner zu senden.

Laden Sie sich unser [Partner-Excel-Blatt](assets/AAM-Partners-October2019.xlsx) herunter, um zu sehen, welche Audience Manager-Aktivierungspartner das Segment nicht unterstützen.

## Datenkorrekturanforderungen {#correction}

Da Audience Manager nicht die Quelle der Daten ist, ist die Datenkorrektur in Audience Manager eingeschränkt. Die Korrektur könnte bedeuten, dass der Verbraucher entweder beantragt hat, von einer falschen Eigenschaft/einem falschen Segment ausgeschlossen oder für die gewünschte Eigenschaft/das gewünschte Segment qualifiziert zu werden.

Audience Manager-Kunden können die relevanten Signale/Eigenschaften/Segmente gegen Benutzerprofile erfassen und diese Informationen über die [Offline-Datenerfassung](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) an Audience Manager senden. Bitte beachten Sie, dass der Benutzer weiterhin für die ursprünglichen Eigenschaften und Segmente qualifiziert ist, wenn er sein Verhalten wiederholt.

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

Dieses Dokument bietet einen Überblick über die Verwaltung der individuellen Datenschutzanforderungen und Abmeldeanforderungen, die Sie über die [Benutzeroberfläche des Privacy Service](https://privacyui.cloud.adobe.io/) und **[!DNL Privacy Service API]** an [!DNL Audience Manager] senden können.

Mit diesen Tools können Sie Anfragen zum Datenschutz von Verbraucherdaten senden, die unter [!DNL GDPR] und [!DNL CCPA] gestellt werden.

Bevor Sie diesen Artikel lesen, sollten Sie das [DSGVO-Glossar](../data-security-and-privacy/aam-gdpr-glossary.md) und das [CCPA-Glossar](aam-ccpa-glossary.md); einsehen, um die hier verwendete Terminologie besser zu verstehen.

Sie können einzelne Anforderungen senden, um auf Verbrauchsdaten von [!DNL Audience Manager] zuzugreifen und diese zu löschen. Dazu haben Sie zwei Möglichkeiten:

* Über die [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche. Die Dokumentation finden Sie [hier](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Über die **[!DNL Privacy Service API]**. Lesen Sie die Dokumentation [hier](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) und den [!DNL API] Verweis [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Beim Senden individueller Datendatenschutzanforderungen können Sie alle [!DNL Audience Manager]-IDs (IDs) übermitteln, wie im Abschnitt **[Audience Manager-IDs](data-privacy-ids.md)** beschrieben, zusammen mit den entsprechenden Namensraum-IDs (Datenquellen-IDs).

[Privacy Service](https://docs.adobe.com/content/help/de-DE/experience-platform/privacy/home.html) unterstützt zwei Arten von Anfragen: Datenzugriffs- und Datenlöschanfragen.

## Datenzugriffsanfragen {#access-data}

Sie können individuelle Datenzugriffsanforderungen über die [Privacy Service-Benutzeroberfläche](https://privacyui.cloud.adobe.io) (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) oder über die Privacy Service-API (-API [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) und [!DNL API] Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) senden.

In der [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche können Sie neue Vorgangsanfragen entweder mithilfe von [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON]-Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON]-Datei aussieht, können Sie [ eine JSON-Beispieldatei herunterladen](../data-security-and-privacy/assets/access_request.json).

Wir sind uns Ihrer Verpflichtung bewusst, Datenschutzanfragen innerhalb der gesetzlich festgelegten Frist zu erfüllen.

## Datenlöschanfragen {#delete-data}

Sie können Datenlöschanforderungen über die [Privacy Service-Benutzeroberfläche](https://privacyui.cloud.adobe.io) (Dokumentation [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) oder die Privacy Service-API (-API [hier ](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) und [!DNL API] Referenz [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) senden.

In der [Privacy Service](https://privacyui.cloud.adobe.io/)-Benutzeroberfläche können Sie neue Vorgangsanfragen entweder mithilfe von [!UICONTROL Request Builder] oder durch Hochladen einer [!DNL JSON]-Datei erstellen.

Um zu sehen, wie eine gültige [!DNL JSON]-Datei aussieht, können Sie [ eine JSON-Beispieldatei herunterladen](../data-security-and-privacy/assets/access_request.json).

Adobe ist sich Ihrer Verpflichtung bewusst, Datenschutzanfragen von Kunden innerhalb von 30 Tagen zu erfüllen. [!DNL Adobe] verpflichtet sich daher, Ihre Datenlöschungsanfrage so bald wie möglich zu bearbeiten.

Als Antwort auf Ihre Anforderungen zum Löschen von Benutzerdaten löscht [!DNL Audience Manager] Eigenschaften und Segmente, die mit der [!DNL Audience Manager]-Kennung in der Anforderung verknüpft sind. Zusätzlich werden die entsprechenden [!DNL Audience Manager]-IDs für die von [!DNL Audience Manager] ausgenommene Person und die entsprechenden ID-Zuordnungen entfernt.

Wenn Sie deklarierte IDs wie z. B. geräteübergreifende [!DNL CRM]-IDs oder [!DNL cookie]-IDs senden, führt [!DNL Audience Manager] in Datendatenschutzanforderungen den erforderlichen Löschvorgang auf allen verknüpften Geräten durch (bis zu 100 Geräte pro deklarierter ID).

[!DNL Audience Manager] versucht, Aktivierungspartner über Löschanfragen zu benachrichtigen, indem Informationen zum Aufheben der Segmentierung für betroffene Personen gesendet werden, die das Löschen bestimmter Daten anfordern. Allerdings können einige Aktivierungspartner:

1. Nicht-Segmentanforderungen von [!DNL Audience Manager] können nicht unterstützt (oder entfernt werden) und/oder
2. sind nicht in der Lage, Updates von [!DNL Audience Manager] mit einer Häufigkeit von weniger als 30 Tagen zu erhalten. In diesen Fällen sind [!DNL Audience Manager]-Kunden nicht in der Lage, Löschanforderungen automatisch über [!DNL Audience Manager] an Aktivierung-Partner zu senden.

In diesen Fällen ist es nicht möglich, Löschanforderungen automatisch über [!DNL Audience Manager] an Aktivierung-Partner zu senden.

Laden Sie unser [Partner Excel Sheet](assets/AAM-Partners-October2019.xlsx) herunter, um zu sehen, welche [!DNL Audience Manager] Aktivierung-Partner das Segment unterstützen.

## Opt-out-Anfragen {#opt-out-requests}

[!DNL Audience Manager] unterstützt branchenweite Standards für das Opt-out-Management. Lesen Sie für vollständige Informationen zu den von [!DNL Audience Manager] unterstützten Opt-out-Typen.

Während Datenzugriffs- und Löschanforderungen über den [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) verarbeitet werden, werden Abmeldeanforderungen derzeit über das [!DNL DCS API] unterstützt. Lesen Sie weiter, um zu erfahren, wie die Ausschluss- [!DNL API]-Aufrufe aussehen sollten.

### Globale Opt-out-Anfragen

Das globale Opt-out stellt eine Abmeldung für [!DNL Audience Manager] und andere [!DNL Adobe Experience Cloud]-Lösungen für alle Marken dar. In der folgenden Tabelle werden die Methoden für das globalen Opt-out-Verfahren angezeigt:

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

Mit der Abmeldung auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte [!DNL Audience Manager]-Partner ausschließen. Sie können Abmeldeanfragen auf Partnerebene für geräteübergreifende IDs, einschließlich [!DNL CRM]-IDs und Hash-E-Mail-Adressen, senden.

Nach einem Opt-out auf Partnerebene mit einem deklarierten ID-Aufruf:

* Die [CRM-ID](../../reference/ids-in-aam.md) wird aus der Datenerfassung ausgeschlossen.
* Die letzte Geräte-ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)), die mit der [CRM-ID](../../reference/ids-in-aam.md) verknüpft ist, wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] beendet alle Datenerfassung, Segmentierung oder Aktivierung für die  [!DNL CRM] ID und die letzte Geräte-ID, die mit der  [!DNL CRM] ID verknüpft ist;
* [!DNL Audience Manager] Aufhebung der Segmentierung der Ausschluss- [!DNL CRM] ID und der letzten Geräte-ID aus allen Segmenten;
* [!UICONTROL Destination] Partner erhalten die Nicht-Segment-Anforderung für die  [!DNL CRM] ID und die letzte Geräte-ID. Die Aufhebung der Segmentierung funktioniert sowohl für [Echtzeit-](data-privacy-requests.md#aam-partners-with-unsegmentation) als auch für Batch-Ziele.
* Es werden keine historischen Daten gelöscht.

Wenn [!DNL Audience Manager] eine Abmeldeanforderung auf Partnerebene empfängt, enthält das [!DNL JSON] zurückgegebene [!DNL DCS] den [Fehlercode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes) mit der Meldung [!UICONTROL "Encountered opt out tag"] anstelle der [!DNL Audience Manager] Benutzer-ID.

Für eine deklarierte ID können Sie eine Opt-out-Anfrage mit den `d_cid`- und `d_cid_ic`-Schlüssel-Wert-Paaren erstellen. Die veralten Parameter wie `d_dpid` und `d_dpuuid` funktionieren weiterhin, werden jedoch als veraltet betrachtet. Siehe [CID ersetzt DPID und DPUUID](../../reference/cid.md). In den Beispielen werden Variablenplatzhalter *kursiv* angegeben.

#### Ausschluss mit [!DNL CID] und [!DNL CID_IC]

Eine Beschreibung und Syntax finden Sie unter [URL-Variablen und -Syntax für deklarierte IDs](../../features/declared-ids.md#variables-and-syntax).

| Opt-out über | Code-Beispiel |
|--- |--- |
| Eine Datenanbieter-ID und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Einen Integrations-Code und eine Benutzer-ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Mehrere Schlüssel-Wert-Paare `d_cid` und `d_cid_ic`. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out auf Partnerebene mit Geräte-ID-Aufrufen

Mit der Abmeldung auf Partnerebene können Sie Ihre Benutzer von der Datenerfassung durch bestimmte [!DNL Audience Manager]-Partner ausschließen. Sie können sich von der Datenerfassung für eine bestimmte Geräte-ID für eine Marke abmelden, indem Sie die [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) wie folgt aufrufen:

| Opt-out über | Code-Beispiel |
|--- |--- |
| Ein [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Eine [!DNL Experience Cloud]-ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Weitere Information über `uuid`, `mid` und `imsOrgId` finden Sie im [Index der IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Nach einem Opt-out auf Partnerebene mit einem Geräte-ID-Aufruf:

* Die Geräte wird aus der Datenerfassung ausgeschlossen.
* [!DNL Audience Manager] beendet die Datenerfassung, Segmentierung oder Aktivierung für den Partner für die Geräte-ID.
* [!DNL Audience Manager] die Segmentierung der Geräte-ID aus allen Segmenten aufheben;
* Zielpartner erhalten die Anfrage zur Aufhebung der Segmentierung für die Geräte-ID. Die Aufhebung der Segmentierung funktioniert sowohl für [Echtzeit-](data-privacy-requests.md#aam-partners-with-unsegmentation) als auch für Batch-Ziele.
* Es werden keine historischen Daten gelöscht.

## [!DNL Audience Manager] Partner mit Unsegmentierungsfunktionen  {#aam-partners-with-unsegmentation}

Um Ihnen bei der Automatisierung Ihrer Verbraucherdatendatenschutzanforderungen zu helfen, versucht [!DNL Audience Manager], die Aktivierung-Partner über Löschungsanfragen von Datensubjekten zu informieren, indem sie die Segmentinformationen zurücksenden (oder entfernen).

Allerdings können einige der Aktivierungspartner:

1. Nicht-Segmentanforderungen von [!DNL Audience Manager] können nicht unterstützt werden und/oder
2. sind nicht in der Lage, Updates von [!DNL Audience Manager] häufiger als einmal in 30 Tagen zu empfangen.

In diesen Fällen ist es nicht möglich, Löschanforderungen automatisch über [!DNL Audience Manager] an Aktivierung-Partner zu senden.

Sehen Sie sich die [Liste der gerätebasierten Ziele](/help/using/features/destinations/device-based-destinations-list.md) an, um zu sehen, welche [!DNL Audience Manager]-Aktivierungen-Partner das Segment unterstützen.

## Datenkorrekturanfragen {#correction}

Da [!DNL Audience Manager] nicht die Quelle der Daten ist, ist die Datenkorrektur in [!DNL Audience Manager] eingeschränkt. Die Korrektur könnte bedeuten, dass der Verbraucher entweder aufgefordert hat, von einem falschen [!UICONTROL trait]/[!UICONTROL segment] disqualifiziert zu werden oder auf das gewünschte [!UICONTROL trait]/[!UICONTROL segment] einzustellen.

[!DNL Audience Manager] Kunden können die relevanten Signale/Eigenschaften/Segmente gegen Profil von Benutzern erfassen und diese Informationen über die  [Offlinedaten-](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Erfassung an senden  [!DNL Audience Manager]. Bitte beachten Sie, dass der Benutzer weiterhin für das Original [!UICONTROL trait] und [!UICONTROL segments] qualifiziert ist, wenn er sein Verhalten wiederholt.

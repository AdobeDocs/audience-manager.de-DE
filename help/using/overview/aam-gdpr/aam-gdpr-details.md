---
description: In diesem Dokument werden die technischen Aspekte im Zusammenhang mit der Allgemeinen Datenschutzverordnung (GDPR) für Audience Manager behandelt und das Übermitteln von GDPR-Anforderungen an Audience Manager erläutert.
seo-description: In diesem Dokument werden die technischen Aspekte im Zusammenhang mit der Allgemeinen Datenschutzverordnung (GDPR) für Audience Manager behandelt und das Übermitteln von GDPR-Anforderungen an Audience Manager erläutert.
seo-title: DSGVO im Audience Manager
solution: Audience Manager
keywords: GDPR-Benutzeroberfläche, GDPR-API
title: DSGVO im Audience Manager
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: b32283a6cb3d001f0a1fc85f3e63fba651f32760

---


# DSGVO im Audience Manager{#gdpr-in-audience-manager}

In diesem Dokument werden die technischen Aspekte im Zusammenhang mit der Allgemeinen Datenschutzverordnung (GDPR) für Audience Manager behandelt und das Übermitteln von GDPR-Anforderungen an Audience Manager erläutert.

## GDPR-Dokumentation in der Experience Cloud {#gdpr-documentation}

Bevor Sie die Audience Manager-Spezifikationen lesen, sollten Sie sich das Experience Cloud-Material für die Europäische Datenschutzverordnung (GDPR) ansehen, das im folgenden Link aufgeführt ist:

* [GDPR und Ihr Geschäft](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [GDPR Whitepaper](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [DSGVO-Terminologie](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

Die folgenden Abschnitte erläutern, was GDPR für Audience Manager bedeutet und wie Sie GDPR-Anforderungen an Audience Manager senden können.

## Typen von GDPR-Anforderungen und Anleitung zum Erstellen einer GDPR-Anforderung {#types-of-gdpr-requests}

Als Audience Manager-Kunde können Sie einzelne GDPR-Anforderungen senden, um auf Kundendaten zuzugreifen und sie zu löschen, entweder über die Benutzeroberfläche **des** Datenschutzdienstes ([UI-Link hier](https://gdprui.cloud.adobe.io/) und [Dokumentation hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)) oder durch Aufruf der **Privacy Service API** ([Dokumentation hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)undAPI-Referenz hiernachzulesen). You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). Bei Fragen wenden Sie sich bitte an den Kundendienst unter gdprsupport@adobe.com.

## Datenzugriff {#access-data}

Wir verstehen Ihr Engagement, Ihre GDPR Kundenanfragen innerhalb von 30 Tagen nach Empfang zu erfüllen. Deshalb versuchen wir, Ihre Datenzugriffsanfrage so schnell wie möglich zu bearbeiten.

**Anfrage**

Sie können Datenzugriffsanforderungen über die Benutzeroberfläche **des** Datenschutzdienstes ([UI-Link hier](https://gdprui.cloud.adobe.io/) und [Dokumentation hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)) oder über die API **des** Datenschutzdienstes ([Dokumentation hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)und hierAPI-Referenz) protokollieren. In beiden Fällen müssen Sie eine JSON mit den Audience Manager-IDs hochladen, für die Sie die Datenzugriffsanforderung senden. Um zu sehen, wie ein gut geformter JSON aussieht, können Sie ein Beispiel-JSON **[herunterladen](assets/access_request.json)**.

**Antwort**

Die Antworten auf die Datenanforderungen enthalten eine Zusammenfassung der Gesamtzahl der Eigenschaften und Segmente, der Eigenschaftsart, der Beschreibungen der Eigenschaften und Segmente sowie der jeweiligen Datenquellennamen. Die Zugriffsantwort enthält außerdem Daten von Zweitanbietern und Drittanbietern, auf die der Data Controller zugreifen kann, zusammen mit den Erstanbieterdaten. Wenn [!UICONTROL declared IDs] z. B. geräteübergreifende CRM-IDs oder Kunden-Cookie-IDs in GDPR-Anforderungen gesendet werden, enthält Audience Manager die Zugriffsantwort aller verknüpften Geräte (bis zu 100 Geräte pro deklarierter ID).

**Antwortstatus**

Wenn in der Antwort Fehler aus Audience Manager auftreten, werden diese als Fehlercodes in der Antwort angezeigt. Es gibt eine [Liste mit Fehlercodes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md), in der Sie weitere Informationen zu den zurückgegebenen Fehlern finden.

**Beispielantwort**

Eine Beispielzugriffsantwort könnte wie die unten stehende aussehen. In diesem Beispiel ist die ID des Datenbetreibers eine Cookie-ID. Sie haben sich für mehrere Eigenschaften qualifiziert und gehören zu einigen Segmenten. Die Cookie-ID ist mit einer mobilen ID verknüpft. Das Beispiel enthält auch Metadaten für das verwendete Telefon.

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

Die nachstehende Tabelle enthält Beschreibungen aller zurückgegebenen Felder in der Antwort auf den Datenzugriff in der Reihenfolge, in der sie oben angezeigt werden.

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Feld </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>Die Benutzer-ID für die folgenden Daten. Hierbei handelt es sich entweder um eine ID, die Sie in der GDPR-Datenzugriffsanforderung angegeben haben, oder um eine ID, die mit einer der angegebenen deklarierten IDs verknüpft ist. Die ID-Typen werden im Abschnitt <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager-IDs</a> beschrieben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Wird auch als Datenquelle bezeichnet. Siehe Abschnitt <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager-IDs</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>Die ID des Namespace/der Datenquelle. Alle zulässigen Werte finden Sie unter <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager-IDs (IDs)</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>Integrationscodes sind benutzerfreundliche Namen für Ihre Datenquellen und helfen Ihnen, Ihre Datenquellen einfacher zu verfolgen als die Datenquellen-IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name </code> </p> </td> 
   <td colname="col2"> <p>Der Name des Eigentümers der Datenquelle. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">Bei Erstanbieterdaten ist dies der eigene Firmenname des Kunden. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">Bei Daten von Fremdherstellern ist dies der Name des Partnerunternehmens. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">Bei Daten von Drittanbietern ist dies der Name des Datenpartners. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>Der Typ der ID, für die Sie den Datenzugriff nach DSGVO angefordert haben. Akzeptierte Typen werden im Abschnitt <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager-IDs</a> aufgeführt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>Warnungen geben weitere Informationen zur Datenzugriffsanforderung zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>Kurze Informationen zur Warnung. </p> <p>Folgende zwei Warnungen werden möglicherweise angezeigt: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Gerätedaten </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Unvollständige Anforderung </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>Eine detailliertere Beschreibung der Warnung, die Sie erhalten haben: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Gerätedaten - Enthält Daten von allen Benutzern dieses Geräts </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Unvollständige Anforderung - Die Abfrage von Audience Manager-Daten wurde nicht abgeschlossen. Einige Informationen fehlen möglicherweise. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>Die Eigenschaften und Segmente, die mit dieser Benutzer-ID verknüpft sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>Eigenschaften, die mit der Benutzer-ID verknüpft sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Der Name der Eigenschaft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>Der Eigenschaftstyp. Die möglichen Werte sind: </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>Erstanbieter</i> für Ihre eigenen Eigenschaften. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Zweitanbieter</i> für Eigenschaften, die zu Ihren Partnern gehören. Lesen Sie unseren <a href="../../overview/data-types-collected.md#second-party-data"> Artikel zu Zweitparteidaten</a> für weitere Informationen. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Drittanbieter</i> für Eigenschaften, die von Datenpartnern über den <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>bezogen werden. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Ein paar Worte, die helfen, den Zweck oder die Funktion der Eigenschaft zu beschreiben. Dies ist ein optionales Feld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>Die <a href="../../features/data-export-controls.md"> Datenexportsteuerelemente</a> , die auf die Datenquelle dieser Eigenschaft angewendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Eigentümers der Datenquelle, zu der diese Eigenschaft gehört. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Bei Erstanbieterdaten ist dies der eigene Firmenname des Kunden. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Bei Daten von Fremdherstellern ist dies der Name des Partnerunternehmens. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Bei Daten von Drittanbietern ist dies der Name des Datenpartners. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>Der genaue Zeitpunkt, zu dem das Datenfach zuletzt für diese Eigenschaft qualifiziert wurde. Das Datumsformat ist JJJ-MM-TT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segments </code> </p> </td> 
   <td colname="col2"> <p>Segmente, denen dieser Benutzer angehört. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Einige Wörter, die Ihnen helfen, dieses Segment zu beschreiben. Dies ist ein optionales Feld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data export controls</code> </p> </td> 
   <td colname="col2"> <p>Die <a href="../../features/data-export-controls.md"> Datenexportsteuerelemente</a> , die auf die Datenquelle dieses Segments angewendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data provider name</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Eigentümers der Datenquelle, zu der dieses Segment gehört. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Bei Erstanbieterdaten ist dies der eigene Firmenname des Kunden. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Bei Daten von Fremdherstellern ist dies der Name des Partnerunternehmens. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Bei Daten von Drittanbietern ist dies der Name des Datenpartners. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>Die exakte Zeit, zu der sich der Data Subject zuletzt für dieses Segment qualifiziert hat. Das Datumsformat ist JJJ-MM-TT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>Gibt an, ob das Datenfach derzeit für dieses Segment qualifiziert ist. Gibt zurück <code><i>true</i></code> oder <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> links </code> </p> </td> 
   <td colname="col2"> <p>Zusätzliche ID, mit der diese ID verknüpft wurde. Informationen werden zurückgegeben am: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (Datenquelle) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace-ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">Name des Datenanbieters </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID-Typ </li> 
     </ul> </p> <p>Alle diese Felder werden in den ersten Zeilen dieser Tabelle beschrieben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>Der Zeitpunkt, zu dem ein ID-Synchronisierungsereignis die Verknüpfung zwischen IDs hergestellt hat. Das Datumsformat ist JJJ-MM-TT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>Informationen zum Gerät. Diese Informationen enthalten die unten stehenden Felder. Beachten Sie, dass nicht alle Felder für alle Gerätetypen zurückgegeben werden. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Hardwareinformationen </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Gerätehersteller </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>Der Marketingname des Geräts </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>Das Gerätemodell </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>Der Name des Betriebssystems des Geräts </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>Die Version des Betriebssystems </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>Gerätehersteller </p> </li> 
     </ul> </p> <p> <p>Hinweis: Geräte-Metadaten werden nur zurückgegeben, wenn Sie eine der folgenden Methoden senden: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">Mobil-IDs </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager-IDs </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud IDs </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datenlöschung {#delete-data}

Wir verstehen Ihr Engagement, Ihre GDPR Kundenanfragen innerhalb von 30 Tagen nach Empfang zu erfüllen. Daher versuchen wir, Ihre Anforderung zum Löschen von Daten so schnell wie möglich zu bearbeiten.

**Anfrage**

Sie können Datenlöschungsanfragen über die Benutzeroberfläche **des** Datenschutzdienstes ([UI-Link hier](https://gdprui.cloud.adobe.io/) und [Dokumentation hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)) oder über die API **des** Datenschutzdienstes ([Dokumentation hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)und Referenzen zur API hier) protokollieren. In beiden Fällen müssen Sie eine JSON mit den Audience Manager-IDs hochladen, für die Sie die Datenzugriffsanforderung senden. Um zu sehen, wie ein gut geformter JSON aussieht, können Sie ein Beispiel-JSON **[herunterladen](assets/delete_request.json)**.

**Antwort**

Als Antwort auf Datenlöschungsanforderungen löschen wir Eigenschaften und Segmente, die mit der jeweiligen Audience Manager-ID verknüpft sind. Darüber hinaus werden die jeweiligen Audience Manager-IDs für die Datengrundlage endgültig aus der weiteren Datenerfassung durch Audience Manager ausgeschlossen und die entsprechenden ID-Zuordnungen werden entfernt. Wenn deklarierte IDs wie geräteübergreifende CRM-IDs oder Kunden-Cookie-IDs in GDPR-Anforderungen gesendet werden, führt Audience Manager die erforderlichen Löschaktionen auf allen verknüpften Geräten durch (bis zu 100 Geräte pro deklarierter ID).

## Abmeldeanforderung {#opt-out-request}

Für Abmeldeanfragen lesen Sie bitte unsere Dokumentation zur [Abmeldeverwaltung](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager-IDs {#aam-ids}

Beim Senden von GDPR-Anforderungen an Adobe Audience Manager müssen Sie eine der unten aufgeführten IDs (IDs) einschließen. Weitere Informationen zu den ID-Formaten finden Sie in unserem [Index der Audience Manager-IDs](../../reference/ids-in-aam.md).

### Adobe Audience Manager Unique User ID

**Benutzer-ID**: aam_uuid

**Definition**:Adobe Audience Manager Unique User ID

**Namespace-ID**: 0

>[!NOTE]
>
>Sie können auch den CORE-Namespace verwenden. Siehe zweites JSON-Beispiel.

**Beispiel in JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**Benutzer-ID**:mid

**Definition**: Adobe Experience Cloud ID, früher als Besucher-ID oder Marketing Cloud ID bekannt

**Namespace-ID**: 4

>[!NOTE]
>
>Sie können auch den ECID-Namespace verwenden. Siehe zweites JSON-Beispiel.

**Beispiel in JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### Customer ID

**Benutzer-ID**: cid

**Definition**: Kunden-ID, z. B. ein für anonyme Site-Besucher eingerichtetes Cookie oder eine CRM-ID eines Offline-Systems oder ein Hash-Benutzername

**Namespace-ID**: Kundenspezifisch. Bitte finden Sie es in Ihrer Audience Manager-Instanz.

**Beispiel in JSON**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### Mobilwerbung-ID

**Benutzer-ID**: d_cid

**Definition**: Anzeigen-IDs für Mobilgeräte
>[!IMPORTANT]
>
> Wenn Sie das Mobile SDK verwenden, sollten Sie außerdem die Experience Cloud ID (MID) zusammen mit mobilen Anzeigen-IDs senden, um Antworten zum vollständigen GDPR-Zugriff und Löschen zu erhalten.

**Namespace-ID**:

* IDFA: 2015
* GAID: 2014

Weitere Informationen finden Sie unter [Globale Datenquellen](../../features/global-data-sources.md) .

**Beispiel in JSON**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### Integrationscode

**Benutzer-ID**: d_cid_ic

**Definition**: Ein Integrationscode für die Datenquelle. Dies kann anstelle der Datenquellen-ID/Namespace-ID in der API-Anforderung an den Adobe Experience Cloud-Datenschutzzentrale-Dienst verwendet werden.

**Namespace-ID**: Nicht anwendbar

Beispiel in JSON:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```

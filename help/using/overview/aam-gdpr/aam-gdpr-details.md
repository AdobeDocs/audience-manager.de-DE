---
description: Dieses Dokument beschreibt die technischen Hinweise zur allgemeinen Datenschutzregel (GDPR) für Audience Manager und zeigt Ihnen, wie Sie GDPR-Anforderungen an Audience Manager senden.
seo-description: Dieses Dokument beschreibt die technischen Hinweise zur allgemeinen Datenschutzregel (GDPR) für Audience Manager und zeigt Ihnen, wie Sie GDPR-Anforderungen an Audience Manager senden.
seo-title: DSGVO im Audience Manager
solution: Audience Manager
title: DSGVO im Audience Manager
uuid: ed 23 a 478-32 be -460 d-bb 03-a 735317 f 7 c 0 f
translation-type: tm+mt
source-git-commit: b791e22e9c8c848a8fc14c6d6494f77c9e7335dc

---


# DSGVO im Audience Manager{#gdpr-in-audience-manager}

Dieses Dokument beschreibt die technischen Hinweise zur allgemeinen Datenschutzregel (GDPR) für Audience Manager und zeigt Ihnen, wie Sie GDPR-Anforderungen an Audience Manager senden.

## GDPR Documentation in the Experience Cloud {#gdpr-documentation}

Bevor Sie die Details zu Audience Manager lesen, empfehlen wir Ihnen, das Erlebnis-Cloud-Material für die allgemeine, unten verlinkte European Data Protection Regel (GDPR) zu durchlaufen:

* [GDPR und Ihr Geschäft](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [GDPR Whitepaper](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [DSGVO-Terminologie](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

In den folgenden Abschnitten wird erläutert, was GDPR für Audience Manager bedeutet und wie Sie GDPR-Anforderungen an Audience Manager senden können.

## Types of GDPR Requests and How to Make a GDPR Request {#types-of-gdpr-requests}

As an Audience Manager customer, you can submit individual GDPR requests to access and delete customer data, either through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). Wenden Sie sich bei Fragen an den Kundendienst unter gdprsupport@adobe.com.

## Datenzugriff {#access-data}

Wir verstehen Ihre Verpflichtung, Ihre GDPR-Kundenanforderungen innerhalb von 30 Tagen nach dem Empfang zu berücksichtigen. Aus diesem Grund versuchen wir, Ihre Datenzugriffsanforderung so schnell wie möglich zu verarbeiten.

**Anfrage**

You can log data access requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `access` action). In beiden Fällen müssen Sie eine JSON-Datei mit den Audience Manager-Identifikatoren hochladen, für die Sie die Datenzugriffsanforderung senden. See what a well-formed JSON looks like in the **[Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/access_request.json)**.

**Antwort**

Antworten für den Zugriff auf Datenanforderungen enthalten eine Zusammenfassung der Gesamtanzahl der Eigenschaften und Segmente, Eigenschaftstypen, Beschreibungen von Eigenschaften und Segmenten zusammen mit den jeweiligen Datenquellennamen. Die Antwortantwort beinhaltet auch Daten von Drittanbietern und Drittanbietern, auf die der Datencontroller zusammen mit den Erstanbieterdaten zugreifen kann. When [!UICONTROL declared IDs] such as cross device CRM IDs or customer cookie IDs are sent in GDPR requests, Audience Manager will include the Access response from all the linked devices (up to 100 devices per declared ID).

**Antwortstatus**

Wenn in der Antwort Fehler aus Audience Manager auftreten, werden diese als Fehlercodes in der Antwort angezeigt. We have a [list of error codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md), where you can find more information about the returned errors.

**Beispielantwort**

Eine Beispielantwort könnte wie folgt aussehen. In diesem Beispiel ist die ID des Datennamens eine Cookie-ID. Sie sind für mehrere Eigenschaften qualifiziert und gehören zu einigen Segmenten. Die Cookie-ID ist mit einer mobilen ID verknüpft. Das Beispiel enthält auch Metadaten für das Smartphone, das sie verwenden.

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

Die unten stehende Tabelle enthält Beschreibungen aller zurückgegebenen Felder in der Datenzugriffsantwort in der Reihenfolge, in der sie oben angezeigt werden.

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
   <td colname="col2"> <p>Die Benutzer-ID für die folgenden Daten. Dies ist entweder eine ID, die Sie in der GDPR-Datenzugriffsanforderung bereitgestellt haben, oder eine ID, die mit einer der angegebenen IDs verknüpft ist. The ID types are described in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Wird auch als Datenquelle bezeichnet. See the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>Die ID des Namespace/der Datenquelle. See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>Integrationscodes sind benutzerfreundliche Namen für Ihre Datenquellen und erleichtern Ihnen die einfachere Verfolgung Ihrer Datenquellen als die Verwendung von Datenquellen-IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Name des Datenanbieters </code> </p> </td> 
   <td colname="col2"> <p>Der Name des Eigentümers der Datenquelle. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">Bei Erstanbieterdaten ist dies der Unternehmensname des Kunden. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">Bei Drittanbieterdaten ist dies der Name des Partnerunternehmens. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">Bei Drittanbieterdaten ist dies der Name des Datenpartners. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>Der Typ der ID, für die Sie den Datenzugriff nach DSGVO angefordert haben. Accepted types are listed in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Warnungen</code> </p> </td> 
   <td colname="col2"> <p>Warnungen geben weitere Informationen über die Datenzugriffsanforderung zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Titel </code> </p> </td> 
   <td colname="col2"> <p>Kurze Informationen zur Warnung. </p> <p>Die beiden Warnungen, die Sie erhalten, sind: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Gerätedaten </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Unvollständige Anforderung </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Beschreibung </code> </p> </td> 
   <td colname="col2"> <p>Eine detailliertere Beschreibung der erhaltenen Warnung: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Gerätedaten: Enthält Daten aller Benutzer dieses Geräts </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Unvollständige Anforderung - Das Abrufen von Audience Manager-Daten wurde nicht abgeschlossen. Einige Informationen fehlen möglicherweise. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Daten </code> </p> </td> 
   <td colname="col2"> <p>Die mit dieser Benutzer-ID verknüpften Eigenschaften und Segmente. </p> </td> 
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
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Zweite Partei</i> für Eigenschaften, die Ihren Partnern angehören. Read our <a href="../../overview/data-types-collected.md#second-party-data"> Second Party Data</a> article for more information. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Drittanbieter</i> für Eigenschaften, die von Datenpartnern über den <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace abgerufen</a>wurden. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Beschreibung</code> </p> </td> 
   <td colname="col2"> <p>Einige Wörter, die den Zweck oder die Funktion des Merkmals beschreiben. Dies ist ein optionales Feld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Datenexportsteuerelemente</code> </p> </td> 
   <td colname="col2"> <p><a href="../../features/data-export-controls.md"> Die Datenexportsteuerelemente,</a> die auf die Datenquelle dieses Merkmals angewendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Name des Datenanbieters</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Eigentümers der Datenquelle, zu der dieses Merkmal gehört. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Bei Erstanbieterdaten ist dies der Unternehmensname des Kunden. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Bei Drittanbieterdaten ist dies der Name des Partnerunternehmens. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Bei Drittanbieterdaten ist dies der Name des Datenpartners. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> letzte Neuerstellung</code> </p> </td> 
   <td colname="col2"> <p>Die genaue Zeit, an der der Datenbetreff zuletzt für diese Eigenschaft qualifiziert ist. Das Datumsformat ist JJJJ-MM-TT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Segmente </code> </p> </td> 
   <td colname="col2"> <p>Segmente, zu denen dieser Benutzer gehört. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Beschreibung</code> </p> </td> 
   <td colname="col2"> <p>Einige Wörter, die dieses Segment beschreiben. Dies ist ein optionales Feld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Datenexportsteuerelemente</code> </p> </td> 
   <td colname="col2"> <p><a href="../../features/data-export-controls.md"> Die Datenexportsteuerelemente,</a> die auf die Datenquelle dieses Segments angewendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Name des Datenanbieters</code> </p> </td> 
   <td colname="col2"> <p>Der Name des Eigentümers der Datenquelle, zu der dieses Segment gehört. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Bei Erstanbieterdaten ist dies der Unternehmensname des Kunden. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Bei Drittanbieterdaten ist dies der Name des Partnerunternehmens. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Bei Drittanbieterdaten ist dies der Name des Datenpartners. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> letzte Neuerstellung</code> </p> </td> 
   <td colname="col2"> <p>Die genaue Zeit, an der die Daten zuletzt für dieses Segment qualifiziert sind. Das Datumsformat ist JJJJ-MM-TT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> aktiv</code> </p> </td> 
   <td colname="col2"> <p>Gibt an, ob der Datenbetreff derzeit für dieses Segment qualifiziert ist. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Links </code> </p> </td> 
   <td colname="col2"> <p>Zusätzliche ID, mit der diese ID verknüpft wurde. Informationen werden zurückgegeben am: </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (Datenquelle) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">Namespace-ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">Name des Datenanbieters </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID-Typ </li> 
     </ul> </p> <p>Alle diese Felder werden in den ersten Zeilen dieser Tabelle beschrieben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Datetime verknüpfen</code> </p> </td> 
   <td colname="col2"> <p>Die genaue Zeit, an der ein ID-Synchronisierungsereignis den Link zwischen den IDs tätigte. Das Datumsformat ist JJJJ-MM-TT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Gerätemetadaten </code> </p> </td> 
   <td colname="col2"> <p>Informationen zum Gerät. Diese Informationen enthalten die folgenden Felder. Beachten Sie, dass nicht alle Felder für alle Gerätetypen zurückgegeben werden. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Hardwareinformationen </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Gerätehersteller </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>Der Marketingname des Geräts </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>Das Gerätemodell </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>Name des Betriebssystems des Geräts (OS) </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>Die Version des Betriebssystems </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>Der Geräteanbieter </p> </li> 
     </ul> </p> <p> <p>Hinweis: Wir geben nur Gerätemetadaten zurück, wenn Sie eines der folgenden senden: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">Mobile IDs </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager-IDs </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud-IDs </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datenlöschung {#delete-data}

Wir verstehen Ihre Verpflichtung, Ihre GDPR-Kundenanforderungen innerhalb von 30 Tagen nach dem Empfang zu berücksichtigen. Aus diesem Grund versuchen wir, Ihre Anforderung zum Löschen von Daten so schnell wie möglich zu verarbeiten.

**Anfrage**

You can log data deletion requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `delete` action). In beiden Fällen müssen Sie eine JSON-Datei mit den Audience Manager-Identifikatoren hochladen, für die Sie die Datenzugriffsanforderung senden. See what a well-formed JSON looks like in the [Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/delete_request.json)**.

**Antwort**

Als Antwort auf Löschanforderungen löschen wir Eigenschaften und Segmente, die mit dem entsprechenden Audience Manager-Bezeichner verknüpft sind. Darüber hinaus werden die entsprechenden Audience Manager-ids für den Datenbetreff dauerhaft von der weiteren Datenerfassung durch Audience Manager abgemeldet und die entsprechenden ID-Zuordnungen werden entfernt. Wenn deklarierte IDs, wie z. B. geräteübergreifende CRM-Ids oder Kunden-Cookie-ids in GDPR-Anforderungen gesendet werden, führt Audience Manager die erforderlichen Aktionen auf allen verknüpften Geräten aus (bis zu 100 Geräte pro deklarierter ID).

## Opt-out Request {#opt-out-request}

For opt-out requests, please refer to our documentation on [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager Identifiers (IDs) {#aam-ids}

Beim Senden von GDPR-Anforderungen an Adobe Audience Manager müssen Sie eine der unten aufgeführten ids (IDs) angeben. You can find more information on the ID formats in our [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

### Eindeutige Benutzer-ID für Adobe Audience Manager

**Benutzer-ID**: aam_ uuid

**Definition**: Eindeutige Benutzer-ID für Adobe Audience Manager

**Namespace-ID**: 0

>[!NOTE]
>
>Sie können auch den Namespace CORE verwenden. Siehe auch das zweite JSON-Beispiel.

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

**Benutzer-ID**: mid

**Definition**: Adobe Experience Cloud ID, früher Visitor ID oder Marketing Cloud ID

**Namespace-ID**: 4

>[!NOTE]
>
>Sie können auch den ECID-Namespace verwenden. Siehe auch das zweite JSON-Beispiel.

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

**Definition**: Kunden-ID, z. B. ein Cookie, das Sie für anonyme Site-Besucher oder eine CRM-ID von einem Offline-System oder einem Hash-Benutzernamen festlegen

**Namespace-ID**: Kundenspezifisch. Finden Sie es von Ihrer Audience Manager-Instanz aus.

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

### Mobile Advertising ID

**Benutzer-ID**: d_ cid

**Definition**: Mobile Advertising IDs.
>[!IMPORTANT]
>
> Wenn Sie das Mobile SDK verwenden, sollten Sie die Experience Cloud ID (MID) zusammen mit mobilen Advertising-IDs zum vollständigen GDPR-Zugriff und zum Löschen von Antworten senden.

**Namespace-ID**:

* IDFA: 20915
* GAID: 20914

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

**Benutzer-ID**: d_ cid_ ic

**Definition**: Ein Integrationscode für die Datenquelle. Dies kann anstelle der Datenquellen-ID/Namespace-ID in der API-Anfrage an den Adobe Experience Cloud Privacy Core Service verwendet werden.

**Namespace-ID**: Nicht zutreffend

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

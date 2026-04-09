---
description: Methoden der Domain-Verwaltung, mit denen Sie die Domains erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: API-Methoden für die Domain-Verwaltung
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
TQID: https://experienceleague.adobe.com/KQYsAmIQd2J88N7d7AdxABYomY-CDXJe5f3RccRcY-g
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 340
ht-degree: 2%

---

# API-Methoden für die Domain-Verwaltung {#domain-management-api-methods}

Methoden der Domain-Verwaltung, mit denen Sie die Domains erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).

<!-- c_partner_site.xml -->

## Erstellen einer neuen Domain {#create-new-domain}

Eine `POST` Methode zum Erstellen einer neuen Domain (nur für Cookie-Ziele).

<!-- r_post_new_partner_site.xml -->

### Anfrage

`POST` `https://api.demdex.com/v1/partner-sites/`

### Beispielanforderung

```
{
   "url":"example1.com"
}
```

### Antwort

Bei einer erfolgreichen Antwort werden `201 created` und die Partner-Site zurückgegeben, einschließlich ihrer eindeutigen ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Löschen einer Domain {#delete-domain}

Eine `DELETE` Methode zum Entfernen einer Domain (nur für Cookie-Ziele).

<!-- r_delete_partner_site.xml -->

### Anfrage

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Antwort

Eine erfolgreiche Antwort gibt `204 no content` zurück. Gibt `404 not found` zurück, wenn die Partnerseite nicht gefunden werden kann.

## Zurückgeben von Eigenschaften für eine Domain {#return-props-domain}

Eine `GET` Methode, die Details zur angegebenen Domain zurückgibt (nur für Cookie-Ziele).

<!-- r_get_partner_site.xml -->

### Anfrage

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und Daten zurück, wie im folgenden Beispiel gezeigt. Gibt `404 Not found` zurück, wenn die Site-ID oder der Partner nicht gefunden wurde.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Eigenschaften für alle Domains zurückgeben {#return-props-all-domains}

Eine `GET` Methode, die Informationen zu all Ihren Domains zurückgibt (nur für Cookie-Ziele).

<!-- r_get_partner_sites.xml -->

### Anfrage

`GET https://api.demdex.com/v1/partner-sites/`

### Optionale Abfrageparameter

Sie können diese optionalen Parameter mit [!DNL API] Methoden verwenden, die *alle*-Eigenschaften für ein Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an den [!DNL API] übergeben. Siehe [Optionale Parameter](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> Gibt Ergebnisse nach Seitenzahl zurück. Nummerierung beginnt bei 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Legt die Anzahl der von der Anfrage zurückgegebenen Antwortergebnisse fest (10 ist der Standardwert). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Sortiert Ergebnisse entsprechend der angegebenen JSON-Eigenschaft und gibt sie zurück. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Sortiert die Ergebnisse in absteigender Reihenfolge und gibt sie zurück. Aufsteigend ist Standard. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle finden, die das Wort „Test“ in einem der Wertefelder für dieses Element enthalten. Ihre Beispielanfrage könnte wie folgt aussehen: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Sie können nach jedem Wert suchen, der von einer „get all“-Methode zurückgegeben wird. </p> </td>
  </tr> 
 </tbody> 
</table>

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und Daten in einem Array zurück, wie im folgenden Beispiel gezeigt. Gibt `404 Not found` zurück, wenn die Site-ID oder der Partner nicht gefunden wurde.

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```

---
description: Domänenverwaltungsmethoden, mit denen Sie die Domänen erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).
seo-description: Domänenverwaltungsmethoden, mit denen Sie die Domänen erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).
seo-title: Domänenverwaltungs-API-Methoden
solution: Audience Manager
title: Domänenverwaltungs-API-Methoden
uuid: f 2 f 08 bc 5-ea 42-4171-9 a 43-0 b 20976 f 0 cb 0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domain Management API Methods {#domain-management-api-methods}

Domänenverwaltungsmethoden, mit denen Sie die Domänen erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

`POST` Eine Methode, mit der Sie eine neue Domäne für (nur Cookie-Ziele) erstellen können.

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

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#delete-domain}

`DELETE` Eine Methode, mit der Sie eine Domäne entfernen können (nur für Cookie-Ziele).

<!-- r_delete_partner_site.xml -->

### Anfrage

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Antwort

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#return-props-domain}

`GET` Eine Methode, die Details über die angegebene Domäne zurückgibt (nur für Cookie-Ziele).

<!-- r_get_partner_site.xml -->

### Anfrage

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Antwort

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#return-props-all-domains}

A `GET` method that returns information about all your domains (for cookie destinations only).

<!-- r_get_partner_sites.xml -->

### Anfrage

`GET https://api.demdex.com/v1/partner-sites/`

### Optionale Abfrageparameter

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col1"><code> Pagesize</code> </td> 
   <td colname="col2"> Legt die Anzahl der von der Anforderung zurückgegebenen Antwortergebnisse fest (Standard: 10). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td> 
   <td colname="col2"> Sortiert und gibt Ergebnisse gemäß der angegebenen JSON-Eigenschaft zurück. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> absteigend</code> </td>
   <td colname="col2"> Sortiert die Ergebnisse in absteigender Reihenfolge und gibt sie zurück. Aufsteigend ist die Standardeinstellung. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> suchen</code> </td>
   <td colname="col2">Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Angenommen, Sie möchten Ergebnisse für alle Modelle mit dem Wort "Test" in allen Wertfeldern für dieses Element suchen. Ihre Beispielanforderung könnte wie folgt aussehen: <p><code> ' GET '' https://api.demdex.com/v1/models/?search=Test '</code>. </p> <p>Sie können nach jedem Wert suchen, der von einer "get all" -Methode zurückgegeben wird. </p> </td>
  </tr> 
 </tbody> 
</table>

### Antwort

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

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

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


# Domänenverwaltungs-API-Methoden {#domain-management-api-methods}

Domänenverwaltungsmethoden, mit denen Sie die Domänen erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).

<!-- c_partner_site.xml -->

## Neue Domäne erstellen {#create-new-domain}

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

Eine erfolgreiche Antwort gibt `201 created` und die Partner-Site einschließlich der eindeutigen ID zurück.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Eine Domäne löschen {#delete-domain}

`DELETE` Eine Methode, mit der Sie eine Domäne entfernen können (nur für Cookie-Ziele).

<!-- r_delete_partner_site.xml -->

### Anfrage

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Antwort

Eine erfolgreiche Antwort wird zurückgegeben `204 no content`. Gibt zurück, `404 not found` wenn die Partner-Site nicht gefunden werden kann.

## Rückgabeeigenschaften für eine Domäne {#return-props-domain}

`GET` Eine Methode, die Details über die angegebene Domäne zurückgibt (nur für Cookie-Ziele).

<!-- r_get_partner_site.xml -->

### Anfrage

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Antwort

Eine erfolgreiche Antwort gibt Daten `200 OK` und Daten wie im Beispiel unten gezeigt ein. Gibt zurück, `404 Not found` wenn die Site-ID oder der Partner nicht gefunden wird.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Rückgabeeigenschaften für alle Domänen {#return-props-all-domains}

Eine Methode, `GET` die Informationen über alle Ihre Domänen zurückgibt (nur für Cookie-Ziele).

<!-- r_get_partner_sites.xml -->

### Anfrage

`GET https://api.demdex.com/v1/partner-sites/`

### Optionale Abfrageparameter

Sie können diese optionalen Parameter mit [!DNL API] Methoden verwenden, die *alle* Eigenschaften für ein Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn Sie diese Abfrage an [!DNL API]&quot;an&quot; übergeben. Siehe [Optionale Parameter](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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

Eine erfolgreiche Antwort gibt Daten `200 OK` und Daten in einem Array zurück, wie im Beispiel unten dargestellt. Gibt zurück, `404 Not found` wenn die Site-ID oder der Partner nicht gefunden wird.

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

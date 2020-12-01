---
description: Domänenverwaltungsmethoden, mit denen Sie die Domänen erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).
seo-description: Domänenverwaltungsmethoden, mit denen Sie die Domänen erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).
seo-title: API-Methoden für die Domänenverwaltung
solution: Audience Manager
title: API-Methoden für die Domänenverwaltung
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 6%

---


# API-Methoden für die Domänenverwaltung {#domain-management-api-methods}

Domänenverwaltungsmethoden, mit denen Sie die Domänen erstellen und verwalten können, an die Sie Daten senden möchten (nur für Cookie-Ziele).

<!-- c_partner_site.xml -->

## Neue Domäne {#create-new-domain} erstellen

Eine `POST`-Methode, mit der Sie eine neue Domäne für (nur Cookie-Ziele) erstellen können.

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

Eine erfolgreiche Antwort gibt `201 created` und die Partner-Site einschließlich ihrer eindeutigen ID zurück.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Eine Domäne {#delete-domain} löschen

Eine `DELETE`-Methode, mit der Sie eine Domäne entfernen können (nur für Cookie-Ziele).

<!-- r_delete_partner_site.xml -->

### Anfrage

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Antwort

Eine erfolgreiche Antwort gibt `204 no content` zurück. Gibt `404 not found` zurück, wenn die Partner-Site nicht gefunden werden kann.

## Rückgabeeigenschaften für eine Domäne {#return-props-domain}

Eine `GET`-Methode, die Details zur angegebenen Domäne zurückgibt (nur für Cookie-Ziele).

<!-- r_get_partner_site.xml -->

### Anfrage

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und die Daten wie im Beispiel unten dargestellt zurück. Gibt `404 Not found` zurück, wenn die Site-ID oder der Partner nicht gefunden wurde.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Rückgabeeigenschaften für alle Domänen {#return-props-all-domains}

Eine `GET`-Methode, die Informationen über alle Ihre Domänen zurückgibt (nur für Cookie-Ziele).

<!-- r_get_partner_sites.xml -->

### Anfrage

`GET https://api.demdex.com/v1/partner-sites/`

### Optionale Abfrage-Parameter

Sie können diese optionalen Parameter mit [!DNL API]-Methoden verwenden, die *alle*-Eigenschaften für ein Objekt zurückgeben. Legen Sie diese Optionen in der Anforderungszeichenfolge fest, wenn diese Abfrage an das [!DNL API] übergeben wird. Siehe [Optionale Parameter](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Gibt Ergebnisse nach Seitenzahl zurück. Nummerierung von Beginn bei 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Legt die Anzahl der Antwortergebnisse fest, die von der Anforderung zurückgegeben werden (10 ist standardmäßig). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Sortiert Ergebnisse und gibt sie entsprechend der angegebenen JSON-Eigenschaft zurück. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Sortiert die Ergebnisse und gibt sie in absteigender Reihenfolge zurück. Aufsteigend ist der Standardwert. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Gibt Ergebnisse basierend auf der angegebenen Zeichenfolge zurück, die Sie als Suchparameter verwenden möchten. Nehmen wir beispielsweise an, Sie möchten Ergebnisse für alle Modelle suchen, die das Wort "Test"in einem der Wertefelder für dieses Element enthalten. Ihre Musteranforderung könnte wie folgt aussehen: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Sie können nach jedem Wert suchen, der von der Methode "get all"zurückgegeben wird. </p> </td>
  </tr> 
 </tbody> 
</table>

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und Daten in einem Array zurück, wie im Beispiel unten dargestellt. Gibt `404 Not found` zurück, wenn die Site-ID oder der Partner nicht gefunden wurde.

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

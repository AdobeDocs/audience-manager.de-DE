---
description: Methoden, mit denen Sie die allgemeine Taxonomie von Audience Manager anzeigen können. Durch dieses optionale Classification-Schema werden Eigenschaften in branchenübliche Kategorien organisiert.
seo-description: Methoden, mit denen Sie die allgemeine Taxonomie von Audience Manager anzeigen können. Durch dieses optionale Classification-Schema werden Eigenschaften in branchenübliche Kategorien organisiert.
seo-title: Taxonomic API-Methoden
solution: Audience Manager
title: Taxonomic API-Methoden
uuid: 4 ee 29 ba 5-e 9 ba -4498-a 6 ee -7343227 dd 7 ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomic API-Methoden {#taxonomic-api-methods}

Methoden, mit denen Sie die allgemeine Taxonomie von Audience Manager anzeigen können. Durch dieses optionale Classification-Schema werden Eigenschaften in branchenübliche Kategorien organisiert.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Sie können keine neuen taxonomischen Kategorien erstellen oder Eigenschaften mit diesen Methoden klassifizieren. Um eine Eigenschaft zu klassifizieren, geben Sie die entsprechende Eigenschaft `categoryId` mit einer Eigenschaft für das Erstellen oder Aktualisieren an.

## Geben Sie eine spezifische Taxonomie zurück. {#return-specific-taxonomy}

Eine `GET` Methode, die Details über die angegebene Taxonomische Kategorie zurückgibt.

<!-- r_rest_api_taxonomy.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und die Kategorie für die angegebene ID an. Eine nicht erfolgreiche Anforderung gibt zurück, `404 No Content` wenn die ID nicht vorhanden ist.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## Alle Taxonomischen Kategorien zurückgeben {#return-all-taxonomy-categories}

`GET` Eine Methode, die eine Liste der Kategorien der obersten Ebene in einem Array zurückgibt.

<!-- r_rest_api_taxonomies.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`

### Antwort

Abgeschnitten.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## Rückkehrende Taxonomische Unterkategorien {#return-taxonomy-sub-categories}

Eine `GET` Methode, die Unterkategorien für die angegebene übergeordnete Kategorie in einem Array zurückgibt.

<!-- r_rest_api_taxonomy_sub.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und die Kategorie für die angegebene ID an. Eine nicht erfolgreiche Anforderung gibt zurück, `404 No Content` wenn die ID nicht vorhanden ist. Abgeschnitten.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```

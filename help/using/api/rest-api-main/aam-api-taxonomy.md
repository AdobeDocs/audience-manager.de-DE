---
description: Methoden, mit denen Sie die allgemeine Taxonomie von Audience Manager anzeigen können. Dieses optionale Klassifizierungssystem gliedert Eigenschaften in branchenübliche Kategorien.
seo-description: Methoden, mit denen Sie die allgemeine Taxonomie von Audience Manager anzeigen können. Dieses optionale Klassifizierungssystem gliedert Eigenschaften in branchenübliche Kategorien.
seo-title: Taxonomische API-Methoden
solution: Audience Manager
title: Taxonomische API-Methoden
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomische API-Methoden {#taxonomic-api-methods}

Methoden, mit denen Sie die allgemeine Taxonomie von Audience Manager anzeigen können. Dieses optionale Klassifizierungssystem gliedert Eigenschaften in branchenübliche Kategorien.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Mit diesen Methoden können Sie keine neuen taxonomischen Kategorien erstellen oder Eigenschaften klassifizieren. Um eine Eigenschaft zu klassifizieren, geben Sie die entsprechende `categoryId` mit einer Eigenschafts- oder Aktualisierungsmethode an.

## Rückgabe einer bestimmten Taxonomie {#return-specific-taxonomy}

Eine `GET` Methode, die Details zur angegebenen taxonomischen Kategorie zurückgibt.

<!-- r_rest_api_taxonomy.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Antwort

Eine erfolgreiche Antwort `200 OK` und die Kategorie für die angegebene ID werden zurückgegeben. Eine nicht erfolgreiche Anforderung wird zurückgegeben, `404 No Content` wenn die ID nicht vorhanden ist.

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

## Alle Taxonomiekategorien zurückgeben {#return-all-taxonomy-categories}

Eine `GET` Methode, die eine Liste der Kategorien der obersten Ebene in einem Array zurückgibt.

<!-- r_rest_api_taxonomies.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`

### Antwort

Kürzlich wegen der Kürze.

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

Eine erfolgreiche Antwort `200 OK` und die Kategorie für die angegebene ID werden zurückgegeben. Eine nicht erfolgreiche Anforderung wird zurückgegeben, `404 No Content` wenn die ID nicht vorhanden ist. Kürzlich wegen der Kürze.

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

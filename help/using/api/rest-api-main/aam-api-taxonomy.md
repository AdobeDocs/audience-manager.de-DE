---
description: Methoden, mit denen Sie die Ansicht des Audience Managers gemeinsame Taxonomie. Dieses optionale Klassifizierungssystem organisiert Eigenschaften in branchenüblichen Kategorien.
seo-description: Methoden, mit denen Sie die Ansicht des Audience Managers gemeinsame Taxonomie. Dieses optionale Klassifizierungssystem organisiert Eigenschaften in branchenüblichen Kategorien.
seo-title: Taxonomische API-Methoden
solution: Audience Manager
title: Taxonomische API-Methoden
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---


# Taxonomische API-Methoden {#taxonomic-api-methods}

Methoden, mit denen Sie die Ansicht des Audience Managers gemeinsame Taxonomie. Dieses optionale Klassifizierungssystem organisiert Eigenschaften in branchenüblichen Kategorien.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Mit diesen Methoden können Sie keine neuen taxonomischen Kategorien erstellen oder Eigenschaften klassifizieren. Um eine Eigenschaft zu klassifizieren, geben Sie die entsprechende `categoryId`-Methode mit einer Eigenschaftserstellungs- oder Aktualisierungsmethode an.

## Rückgabe einer bestimmten Taxonomie {#return-specific-taxonomy}

Eine `GET`-Methode, die Details zur angegebenen taxonomischen Kategorie zurückgibt.

<!-- r_rest_api_taxonomy.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und die Kategorie für die angegebene ID zurück. Eine nicht erfolgreiche Anforderung gibt `404 No Content` zurück, wenn die ID nicht vorhanden ist.

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

## Alle taxonomischen Kategorien {#return-all-taxonomy-categories} zurückgeben

Eine `GET`-Methode, die eine Liste der Kategorien der obersten Ebene in einem Array zurückgibt.

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

## Rückgabe von Taxonomischen Unter-Kategorien {#return-taxonomy-sub-categories}

Eine `GET`-Methode, die Untergruppen für die angegebene übergeordnete Kategorie in einem Array zurückgibt.

<!-- r_rest_api_taxonomy_sub.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und die Kategorie für die angegebene ID zurück. Eine nicht erfolgreiche Anforderung gibt `404 No Content` zurück, wenn die ID nicht vorhanden ist. Kürzlich wegen der Kürze.

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

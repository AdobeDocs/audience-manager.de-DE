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


# Taxonomic API Methods {#taxonomic-api-methods}

Methoden, mit denen Sie die allgemeine Taxonomie von Audience Manager anzeigen können. Durch dieses optionale Classification-Schema werden Eigenschaften in branchenübliche Kategorien organisiert.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Sie können keine neuen taxonomischen Kategorien erstellen oder Eigenschaften mit diesen Methoden klassifizieren. To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

A `GET` method that returns details about the specified taxonomic category.

<!-- r_rest_api_taxonomy.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Antwort

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist.

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

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

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

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

A `GET` method that returns sub-categories for the specified parent category in an array.

<!-- r_rest_api_taxonomy_sub.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Antwort

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist. Abgeschnitten.

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

---
description: Methoden, mit denen Sie die gemeinsame Taxonomie des Audience Managers anzeigen können. Dieses optionale Klassifizierungssystem organisiert Eigenschaften in Kategorien, die dem Branchenstandard entsprechen.
seo-description: Methoden, mit denen Sie die gemeinsame Taxonomie des Audience Managers anzeigen können. Dieses optionale Klassifizierungssystem organisiert Eigenschaften in Kategorien, die dem Branchenstandard entsprechen.
seo-title: Taxonomische API-Methoden
solution: Audience Manager
title: Taxonomische API-Methoden
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 8%

---

# Taxonomische API-Methoden {#taxonomic-api-methods}

Methoden, mit denen Sie die gemeinsame Taxonomie des Audience Managers anzeigen können. Dieses optionale Klassifizierungssystem organisiert Eigenschaften in Kategorien, die dem Branchenstandard entsprechen.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Mit diesen Methoden können Sie keine neuen Taxonomiekategorien erstellen oder Eigenschaften klassifizieren. Um eine Eigenschaft zu klassifizieren, geben Sie die entsprechende `categoryId` mit einer Methode zum Erstellen oder Aktualisieren von Eigenschaften an.

## Rückgabe einer bestimmten Taxonomie {#return-specific-taxonomy}

Eine `GET` -Methode, die Details zur angegebenen taxonomischen Kategorie zurückgibt.

<!-- r_rest_api_taxonomy.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und die Kategorie für die angegebene ID zurück. Eine nicht erfolgreiche Anfrage gibt `404 No Content` zurück, wenn die ID nicht vorhanden ist.

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

Eine `GET` -Methode, die eine Liste der Kategorien der obersten Ebene in einem Array zurückgibt.

<!-- r_rest_api_taxonomies.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`

### Antwort

Kürzt aus Gründen der Kürze.

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

## Rückgabe Taxonomischer Unterkategorien {#return-taxonomy-sub-categories}

Eine `GET` -Methode, die Unterkategorien für die angegebene übergeordnete Kategorie in einem Array zurückgibt.

<!-- r_rest_api_taxonomy_sub.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und die Kategorie für die angegebene ID zurück. Eine nicht erfolgreiche Anfrage gibt `404 No Content` zurück, wenn die ID nicht vorhanden ist. Kürzt aus Gründen der Kürze.

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

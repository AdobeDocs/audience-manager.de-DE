---
description: Methoden zum Anzeigen der allgemeinen Audience Manager-Taxonomie. Mit diesem optionalen Klassifizierungsschema werden Eigenschaften in branchenübliche Kategorien unterteilt.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Taxonomische API-Methoden
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
TQID: https://experienceleague.adobe.com/LIHEWvF3t-VNHJEviomvCF-dxE2Jy-BFxBynonvwP3w
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 173
ht-degree: 1%

---

# Taxonomische API-Methoden {#taxonomic-api-methods}

Methoden zum Anzeigen der allgemeinen Audience Manager-Taxonomie. Mit diesem optionalen Klassifizierungsschema werden Eigenschaften in branchenübliche Kategorien unterteilt.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Mit diesen Methoden können keine neuen taxonomischen Kategorien erstellt oder Eigenschaften klassifiziert werden. Um eine Eigenschaft zu klassifizieren, geben Sie die entsprechende `categoryId` mit einer Methode zum Erstellen oder Aktualisieren von Eigenschaften an.

## Gibt eine bestimmte Taxonomie zurück {#return-specific-taxonomy}

Eine `GET` Methode, die Details zur angegebenen taxonomischen Kategorie zurückgibt.

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

## Alle taxonomischen Kategorien zurückgeben {#return-all-taxonomy-categories}

Eine `GET` Methode, die eine Liste der Kategorien der obersten Ebene in einem Array zurückgibt.

<!-- r_rest_api_taxonomies.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`

### Antwort

Aus Gründen der Kürze gekürzt

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

## Gibt taxonomische Unterkategorien zurück {#return-taxonomy-sub-categories}

Eine `GET` Methode, die Unterkategorien für die angegebene übergeordnete Kategorie in einem Array zurückgibt.

<!-- r_rest_api_taxonomy_sub.xml -->

### Anfrage

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Antwort

Eine erfolgreiche Antwort gibt `200 OK` und die Kategorie für die angegebene ID zurück. Eine nicht erfolgreiche Anfrage gibt `404 No Content` zurück, wenn die ID nicht vorhanden ist. Aus Gründen der Kürze gekürzt

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

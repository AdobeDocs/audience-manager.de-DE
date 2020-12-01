---
description: Optionale Methoden, mit denen Sie Eigenschaften einem benutzerdefinierten Typ oder einer benutzerdefinierten Kategorie zuweisen können, üblicherweise entsprechend der Funktion oder für Ihre eigenen internen Berichte-Prozesse.
seo-description: Optionale Methoden, mit denen Sie Eigenschaften einem benutzerdefinierten Typ oder einer benutzerdefinierten Kategorie zuweisen können, üblicherweise entsprechend der Funktion oder für Ihre eigenen internen Berichte-Prozesse.
seo-title: Eigenschaftstypmethoden
solution: Audience Manager
title: Eigenschaftstypmethoden
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 9%

---


# Eigenschaftstypmethoden {#trait-type-methods}

Optionale Methoden, mit denen Sie Eigenschaften einem benutzerdefinierten Typ oder einer benutzerdefinierten Kategorie zuweisen können, üblicherweise entsprechend der Funktion oder für Ihre eigenen internen Berichte-Prozesse.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Eigenschafts-Typmethoden weisen Kategorien, die von der [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods) verwendet werden, keine Eigenschaften zu. Stellen Sie sich diese als Etiketten vor, die von der allgemeinen Taxonomie getrennt sind.

Als visuelle Referenz dient [!UICONTROL Trait Types] als Dropdown-Steuerelement im [!DNL UI] unter **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Erstellen eines neuen Eigenschaftentyps {#create-trait-type}

Eine `POST`-Methode, mit der Sie einen neuen Eigenschaftstyp erstellen können.

<!-- r_rest_api_create_trait_type.xml -->

### Anfrage

`POST https://api.demdex.com/v1/customer-trait-types`

### Beispielanforderung

```
{
"name":"Custom trait type"
}
```

### Antwort

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Rückgabeeigenschaften für einen Eigenschaftstyp {#return-props}

Eine `GET`-Methode, die Details zum angegebenen Eigenschaftstyp zurückgibt.

<!-- r_rest_api_get_trait_type.xml -->

### Anfrage

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### Antwort

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Rückgabeeigenschaften für alle Eigenschaftstypen {#return-props-all}

Eine `GET`-Methode, die Details zu allen Eigenschaftstypen in einem Array zurückgibt.

<!-- r_rest_api_get_trait_types.xml -->

### Anfrage

`GET https://api.demdex.com/v1/customer-trait-types/`

### Antwort

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```

---
description: Optionale Methoden, mit denen Sie einem benutzerdefinierten Typ oder einer Kategorie Eigenschaften zuweisen können, normalerweise entsprechend der Funktion oder für Ihre eigenen internen Berichterstellungsprozesse.
seo-description: Optionale Methoden, mit denen Sie einem benutzerdefinierten Typ oder einer Kategorie Eigenschaften zuweisen können, normalerweise entsprechend der Funktion oder für Ihre eigenen internen Berichterstellungsprozesse.
seo-title: Eigenschaftstypmethoden
solution: Audience Manager
title: Eigenschaftstypmethoden
uuid: 082931 d 5-457 b -4622-817 b -86303 f 38 c 26 a
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Eigenschaftstypmethoden {#trait-type-methods}

Optionale Methoden, mit denen Sie einem benutzerdefinierten Typ oder einer Kategorie Eigenschaften zuweisen können, normalerweise entsprechend der Funktion oder für Ihre eigenen internen Berichterstellungsprozesse.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Eigenschaften von Eigenschaften weisen Kategorien, die von der [allgemeinen Taxonomie verwendet werden, keine Eigenschaften](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)zu. Stellen Sie sich diese als Beschriftungen vor, die von der allgemeinen Taxonomie getrennt sind.

Bei visueller Referenz handelt [!UICONTROL Trait Types] es sich um eine Dropdown-Steuerung im [!DNL UI] Abschnitt unter **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Neuen Eigenschaften-Typ erstellen {#create-trait-type}

Eine `POST` Methode, mit der Sie einen neuen Eigenschaftstyp erstellen können.

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

## Rückgabeeigenschaften für einen Trait-Typ {#return-props}

Eine `GET` Methode, die Details zum angegebenen Eigenschaftstyp zurückgibt.

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

## Rückgabeeigenschaften für alle Trait-Typen {#return-props-all}

`GET` Eine Methode, die Details zu all Ihren Eigenschaften in einem Array zurückgibt.

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

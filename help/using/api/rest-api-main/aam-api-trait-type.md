---
description: Optionale Methoden, mit denen Sie Eigenschaften einem benutzerdefinierten Typ oder einer benutzerspezifischen Kategorie zuweisen können, in der Regel entsprechend der Funktion oder für Ihre eigenen internen Berichtsprozesse.
seo-description: Optionale Methoden, mit denen Sie Eigenschaften einem benutzerdefinierten Typ oder einer benutzerspezifischen Kategorie zuweisen können, in der Regel entsprechend der Funktion oder für Ihre eigenen internen Berichtsprozesse.
seo-title: Eigenschafts-Typmethoden
solution: Audience Manager
title: Eigenschafts-Typmethoden
uuid: 082931d5-457b-4622-817b-86303f38c26a
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Eigenschafts-Typmethoden {#trait-type-methods}

Optionale Methoden, mit denen Sie Eigenschaften einem benutzerdefinierten Typ oder einer benutzerspezifischen Kategorie zuweisen können, in der Regel entsprechend der Funktion oder für Ihre eigenen internen Berichtsprozesse.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Mit den Methoden des Eigenschaftstyps werden keine Eigenschaften den von der [allgemeinen Taxonomie](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)verwendeten Kategorien zugewiesen. Stellen Sie sich diese als Etiketten vor, die von der allgemeinen Taxonomie getrennt sind.

Als visuelle Referenz dient [!UICONTROL Trait Types] ein Dropdown-Steuerelement, das sich im [!DNL UI] darunter befindet **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Erstellen eines neuen Eigenschaftstyps {#create-trait-type}

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

## Rückgabeeigenschaften für einen Eigenschaftstyp {#return-props}

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

## Rückgabeeigenschaften für alle Eigenschaftstypen {#return-props-all}

Eine `GET` Methode, die Details zu allen Eigenschaftstypen in einem Array zurückgibt.

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

---
description: In diesem Dokument werden die Typen von Audience Manager-IDs beschrieben, die Sie in Datendatenschutzanfragen verwenden können.
seo-description: This document covers the types of Audience Manager IDs that you can use in data privacy requests.
seo-title: Audience Manager Identifiers (IDs)
solution: Audience Manager
keywords: DSGVO-Benutzeroberfläche, DSGVO-API, CCPA, Datenschutz, AAM-ID
title: Audience Manager-IDs
feature: Data Governance & Privacy
exl-id: 5f18ed0a-c875-4596-a4d1-f9a7fe871d1b
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 96%

---

# Audience Manager-IDs {#aam-ids}

Bei der Übermittlung von [Datenschutzanfragen](data-privacy-requests.md) an Adobe Audience Manager müssen Sie eine der unten aufgeführten IDs angeben. Weitere Informationen zu den ID-Formaten finden Sie in unserem [Index of IDs in Audience Manager](../../reference/ids-in-aam.md).

## Adobe Audience Manager Unique User ID

* **Benutzer-ID**: `aam_uuid`
* **Definition**: Adobe Audience Manager Unique User ID
* **Namespace-ID**: 0

**JSON-Beispiel**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>Sie können auch den [!DNL CORE]-Namespace verwenden.

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **Benutzer-ID**: `mid`
* **Definition**: [!DNL Adobe Experience Cloud ID], früher bekannt als [!DNL Visitor ID] oder [!DNL Marketing Cloud ID]
* **Namespace-ID**: 4

>[!NOTE]
>
>Sie können auch den [!DNL ECID]-Namespace verwenden. Siehe das zweite [!DNL JSON]-Beispiel.

**JSON-Beispiel**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## Kunden-ID

**Benutzer-ID**: `cid`

**Definition**: Kunden-ID, z. B. ein für anonyme Site-Besucher eingerichtetes Cookie, eine [!DNL CRM]-ID eines Offline-Systems oder ein Hash-Benutzername.

**Namespace-ID**: Kundenspezifisch. Sie finden sie in Ihrer Audience Manager-Instanz.

**JSON-Beispiel**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## Mobile Advertising-ID

**Benutzer-ID**: `d_cid`

**Definition**: IDs für mobile Werbung.

**Namespace-ID**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Weitere Informationen finden Sie unter [Globale Data Sources](../../features/global-data-sources.md).

>[!IMPORTANT]
>
> Wenn Sie das [!DNL SDK] verwenden, sollten Sie außerdem die Experience Cloud ID (`MID`) zusammen mit den Mobile Advertising-IDs senden, um vollständige Antworten auf Zugriffs- und Löschanfragen zu erhalten.

**JSON-Beispiel**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## Integrations-Code

**Benutzer-ID**: `d_cid_ic`

**Definition**: Ein Integrations-Code für die Datenquelle. Dieser kann anstelle der Datenquellen-ID/Namespace-ID in der [!DNL API]-Anfrage an [!DNL Adobe Experience Cloud Privacy Core Service] verwendet werden.

**Namespace-ID**: Nicht zutreffend

**JSON-Beispiel**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```

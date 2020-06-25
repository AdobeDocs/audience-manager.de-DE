---
description: Dieses Dokument behandelt die Typen von Audience Manager-IDs, die Sie in Datendatenschutzanforderungen verwenden können.
seo-description: Dieses Dokument behandelt die Typen von Audience Manager-IDs, die Sie in Datendatenschutzanforderungen verwenden können.
seo-title: Audience Manager-IDs (IDs)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Audience Manager-IDs (IDs)
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 10%

---


# Audience Manager-IDs (IDs) {#aam-ids}

Bei der Übermittlung von [Datendatenschutzanforderungen](data-privacy-requests.md) an Adobe Audience Manager müssen Sie eine der unten aufgeführten IDs (IDs) angeben. Weitere Informationen zu den ID-Formaten finden Sie in unserem [Index der Audience Manager-IDs](../../reference/ids-in-aam.md).

## Individuelle Benutzer-ID des Adobe Audience Managers

* **Benutzer-ID**: `aam_uuid`
* **Definition**: Individuelle Benutzer-ID des Adobe Audience Managers
* **Namensraum-ID**: 0

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
>You can also use the [!DNL CORE] namespace.

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
* **Namensraum-ID**: 4

>[!NOTE]
>
>You can also use the [!DNL ECID] namespace. Siehe zweites [!DNL JSON] Beispiel.

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

## Customer ID

**Benutzer-ID**: `cid`

**Definition**: Kunden-ID, z. B. ein für anonyme Site-Besucher eingerichtetes Cookie, eine [!DNL CRM] ID eines Offline-Systems oder ein Hash-Benutzername.

**Namensraum-ID**: Kundenspezifisch. Bitte finden Sie es in Ihrer Audience Manager-Instanz.

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

## Mobilwerbung-ID

**Benutzer-ID**: `d_cid`

**Definition**: Anzeigen-IDs für Mobilgeräte

**Namespace-ID**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Weitere Informationen finden Sie unter [Globale Datenquellen](../../features/global-data-sources.md) .

>[!IMPORTANT]
>
> Wenn Sie das Mobilgerät verwenden [!DNL SDK]sollten Sie außerdem die Experience Cloud-ID (`MID`) zusammen mit mobilen Anzeigen-IDs senden, um vollständige Antworten auf &quot;Zugriff&quot;und &quot;Löschen&quot;zu erhalten.

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

## Integrationscode

**Benutzer-ID**: `d_cid_ic`

**Definition**: Ein Integrationscode für die Datenquelle. Dies kann anstelle der Datenquellen-ID/Namensraum-ID in der [!DNL API] Anforderung verwendet [!DNL Adobe Experience Cloud Privacy Core Service]werden.

**Namensraum-ID**: Nicht anwendbar

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

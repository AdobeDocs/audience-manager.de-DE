---
description: Der Authentifizierungsstatus des Besuchers in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Gerätehilfen-Profil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNKNOWN und LOGGED_OUT in Ereignis-Aufrufen auf dieselbe Weise.
keywords: dpm.demdex.net
seo-description: Der Authentifizierungsstatus des Besuchers in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Gerätehilfen-Profil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNKNOWN und LOGGED_OUT in Ereignis-Aufrufen auf dieselbe Weise.
seo-title: Besucherauthentifizierungsstatus in Audience Manager
solution: Audience Manager
title: Besucherauthentifizierungsstatus in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Besucherauthentifizierungsstatus in Audience Manager{#visitor-authentication-states-in-audience-manager}

Der Authentifizierungsstatus des Besuchers in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Gerätehilfen-Profil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNKNOWN und LOGGED_OUT in Ereignis-Aufrufen auf dieselbe Weise.

Ab [!DNL Experience Cloud] ID-Dienst Version 1.5 enthält die `setCustomerID` Methode das optionale `AuthState` Objekt. `AuthState` identifiziert Besucher gemäß ihrem [Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] verarbeitet die realisierten Eigenschaften unterschiedlich, je nach Authentifizierungsstatus, der im Aufruf übergeben wird, und der [Profil Merge Rule](../features/profile-merge-rules/merge-rules-dashboard.md) , die Sie für die Segmentierung verwenden.

## Authentifizierungsstatus: UNBEKANNT {#auth-status-unknown}

| Anforderungswert | **Lesen** von Informationen aus dem authentifizierten Profil | **Neue Eigenschaften in das authentifizierte Profil schreiben** |
---------|----------|---------
| 0 | <ul><li>Ja, wenn die Authentifizierungsoption Merge Rule = &quot;Last Authenticated Profils&quot;.</li><li>Nein, wenn die Authentifizierungsoption Merge Rule = &quot;Current Authenticated Profils&quot; oder &quot;No Authenticated Profil&quot;.</li></ul> | Nein, die Eigenschaftsdaten werden dem Profil des Geräts hinzugefügt. |


Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentifizierungsstatus: AUTHENTICATED {#auth-status-authenticated}

| Anforderungswert | **Lesen** von Informationen aus dem authentifizierten Profil | **Neue Eigenschaften in das authentifizierte Profil schreiben** |
---------|----------|---------
| 1 | <ul><li>Ja, wenn die Authentifizierungsoption Merge Rule = &quot;Current Authenticated Profils&quot; oder &quot;Last Authenticated Profils&quot; ist.</li><li>Nein, wenn die authentifizierte Option Merge Rule = &quot;No Authenticated Profil&quot;.</li></ul> | Ja, die Eigenschaftendaten werden dem authentifizierten Profil hinzugefügt. |

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentifizierungsstatus: LOGGED_OUT {#auth-status-logged-out}

| Anforderungswert | **Lesen** von Informationen aus dem authentifizierten Profil | **Neue Eigenschaften in das authentifizierte Profil schreiben** |
---------|----------|---------
| 2 | <ul><li>Ja, wenn die Merge-Regel für die authentifizierte Option = &quot;Letzte authentifizierte Profil&quot;</li><li>Nein, wenn die Merge-Regel für die authentifizierte Option = &quot;Aktuelle authentifizierte Profil&quot;oder &quot;Kein authentifiziertes Profil&quot;</li></ul> | Nein, die Eigenschaftsdaten werden in das Profil des Geräts geschrieben. |

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] führt in allen drei Fällen eine ID-Synchronisierung zwischen [CID und UUID](../reference/ids-in-aam.md) durch.

>[!MORELIKETHIS]
>
>* [Kunden-IDs und Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)


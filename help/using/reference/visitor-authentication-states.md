---
description: Der Authentifizierungsstatus der Besucher in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Geräteprofil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Authentifizierungsstatus der Besucher-ID UNKNOWN und LOGGED_OUT in Ereignisaufrufen auf dieselbe Weise.
keywords: dpm.demdex.net
seo-description: Der Authentifizierungsstatus der Besucher in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Geräteprofil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Authentifizierungsstatus der Besucher-ID UNKNOWN und LOGGED_OUT in Ereignisaufrufen auf dieselbe Weise.
seo-title: Besucherauthentifizierungsstatus in Audience Manager
solution: Audience Manager
title: Besucherauthentifizierungsstatus in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 'Referenz '
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: c3c829ef1335d1e073b719f8252103fa578bb4e6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 7%

---

# Besucherauthentifizierungsstatus in Audience Manager{#visitor-authentication-states-in-audience-manager}

Der Authentifizierungsstatus der Besucher in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Geräteprofil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Authentifizierungsstatus der Besucher-ID UNKNOWN und LOGGED_OUT in Ereignisaufrufen auf dieselbe Weise.

Ab [!DNL Experience Cloud] ID-Dienst v1.5 enthält die `setCustomerID`-Methode das optionale `AuthState`-Objekt. `AuthState` identifiziert Besucher anhand ihres  [Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] verarbeitet die realisierten Eigenschaften unterschiedlich, je nach dem Authentifizierungsstatus, der im Aufruf übergeben wird, und der  [Profilzusammenführungsrichtlinie, die Sie für die Segmentierung ](../features/profile-merge-rules/merge-rules-dashboard.md) verwenden.

## Authentifizierungsstatus: UNBEKANNT {#auth-status-unknown}

| Anforderungswert | Informationen aus dem authentifizierten Profil lesen | Neue Eigenschaften in das authentifizierte Profil schreiben |
|---|---|---|
| 0 | <ul><li>Ja, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nein, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL No Authenticated Profile]</li></ul> | Nein, die Eigenschaftsdaten werden dem Geräteprofil hinzugefügt. |

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentifizierungsstatus: AUTHENTIFIZIERT {#auth-status-authenticated}

| Anforderungswert | Informationen aus dem authentifizierten Profil lesen | Neue Eigenschaften in das authentifizierte Profil schreiben |
|---|---|---|
| 1 | <ul><li>Ja, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL Last Authenticated Profiles]</li><li>Nein, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Ja, die Eigenschaftsdaten werden dem authentifizierten Profil hinzugefügt. |

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentifizierungsstatus: LOGGED_OUT {#auth-status-logged-out}

| Anforderungswert | Informationen aus dem authentifizierten Profil lesen | Neue Eigenschaften in das authentifizierte Profil schreiben |
|---|---|---|
| 2 | <ul><li>Ja, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nein, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL No Authenticated Profile]</li></ul> | Nein, die Eigenschaftsdaten werden in das Geräteprofil geschrieben. |

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] führt in allen drei Fällen eine ID-Synchronisierung zwischen  [CID und ](../reference/ids-in-aam.md) UUID durch.

>[!MORELIKETHIS]
>
>* [Kunden-IDs und Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)


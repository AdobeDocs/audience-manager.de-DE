---
description: Der Authentifizierungsstatus der Besucher in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Geräteprofil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Authentifizierungsstatus der Besucher-ID UNKNOWN und LOGGED_OUT in Ereignisaufrufen auf dieselbe Weise.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Authentifizierungsstatus von Besuchern im Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Authentifizierungsstatus von Besuchern im Audience Manager{#visitor-authentication-states-in-audience-manager}

Der Authentifizierungsstatus der Besucher in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Geräteprofil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Authentifizierungsstatus der Besucher-ID UNKNOWN und LOGGED_OUT in Ereignisaufrufen auf dieselbe Weise.

Ab der [!DNL Experience Cloud] ID-Dienstversion 1.5 enthält die `setCustomerID` -Methode das optionale `AuthState` -Objekt. `AuthState` identifiziert Besucher anhand ihres [Authentifizierungsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] verarbeitet die realisierten Eigenschaften unterschiedlich, je nach dem Authentifizierungsstatus, der im Aufruf übergeben wird, und der [Profilzusammenführungsregel](../features/profile-merge-rules/merge-rules-dashboard.md), die Sie für die Segmentierung verwenden.

## Authentifizierungsstatus: UNBEKANNT {#auth-status-unknown}

| Anforderungswert | Informationen aus dem authentifizierten Profil lesen | Neue Eigenschaften in das authentifizierte Profil schreiben |
|---|---|---|
| 0 | <ul><li>Ja, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nein, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL No Authenticated Profile].</li></ul> | Nein, die Eigenschaftsdaten werden dem Geräteprofil hinzugefügt. |

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentifizierungsstatus: AUTHENTICATED {#auth-status-authenticated}

| Anforderungswert | Informationen aus dem authentifizierten Profil lesen | Neue Eigenschaften in das authentifizierte Profil schreiben |
|---|---|---|
| 1 | <ul><li>Ja, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL Last Authenticated Profiles] ist.</li><li>Nein, wenn der [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Ja, die Eigenschaftsdaten werden dem authentifizierten Profil hinzugefügt. |

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentifizierungsstatus: LOGGED_OUT {#auth-status-logged-out}

| Anforderungswert | Informationen aus dem authentifizierten Profil lesen | Neue Eigenschaften in das authentifizierte Profil schreiben |
|---|---|---|
| 2 | <ul><li>Ja, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nein, wenn [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL No Authenticated Profile].</li></ul> | Nein, die Eigenschaftsdaten werden in das Geräteprofil geschrieben. |

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] führt in allen drei Fällen eine ID-Synchronisierung zwischen [CID und UUID](../reference/ids-in-aam.md) durch.

>[!MORELIKETHIS]
>
>* [Kunden-IDs und Authentifizierungsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)

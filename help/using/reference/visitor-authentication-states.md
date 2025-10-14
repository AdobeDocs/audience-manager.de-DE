---
description: Der Besucherauthentifizierungsstatus in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Geräteprofil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager behandelt den Authentifizierungsstatus der Besucher-ID UNKNOWN und LOGGED_OUT bei Ereignisaufrufen auf die gleiche Weise.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Status der Besucherauthentifizierung in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Status der Besucherauthentifizierung in Audience Manager{#visitor-authentication-states-in-audience-manager}

Der Besucherauthentifizierungsstatus in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Geräteprofil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager behandelt den Authentifizierungsstatus der Besucher-ID UNKNOWN und LOGGED_OUT bei Ereignisaufrufen auf die gleiche Weise.

Ab Version 1.5 [!DNL Experience Cloud] ID-Service enthält die `setCustomerID`-Methode das optionale `AuthState`. `AuthState` identifiziert Besucher anhand ihres [Authentifizierungsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=de). [!DNL Audience Manager] verarbeitet die realisierten Eigenschaften je nach dem im Aufruf übergebenen Authentifizierungsstatus und der für die Segmentierung verwendeten [Profilzusammenführungsregel](../features/profile-merge-rules/merge-rules-dashboard.md) unterschiedlich.

## Authentifizierungsstatus: UNBEKANNT {#auth-status-unknown}

| Wert der Anfrage | Lesen von Informationen aus dem authentifizierten Profil | Schreiben neuer Eigenschaften in das authentifizierte Profil |
|---|---|---|
| 0 | <ul><li>Ja, wenn die [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nein, wenn die [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL No Authenticated Profile].</li></ul> | Nein, die Eigenschaftsdaten werden zum Geräteprofil hinzugefügt. |

Beispielaufruf (der dem Authentifizierungsstatus entsprechende Anfragewert ist hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentifizierungsstatus: AUTHENTIFIZIERT {#auth-status-authenticated}

| Wert der Anfrage | Lesen von Informationen aus dem authentifizierten Profil | Schreiben neuer Eigenschaften in das authentifizierte Profil |
|---|---|---|
| 1 | <ul><li>Ja, wenn die [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL Last Authenticated Profiles].</li><li>Nein, wenn die [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | Ja, die Eigenschaftsdaten werden zum authentifizierten Profil hinzugefügt. |

Beispielaufruf (der dem Authentifizierungsstatus entsprechende Anfragewert ist hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentifizierungsstatus: LOGGED_OUT {#auth-status-logged-out}

| Wert der Anfrage | Lesen von Informationen aus dem authentifizierten Profil | Schreiben neuer Eigenschaften in das authentifizierte Profil |
|---|---|---|
| 2 | <ul><li>Ja, wenn die [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>Nein, wenn die [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL No Authenticated Profile].</li></ul> | Nein, die Eigenschaftsdaten werden in das Geräteprofil geschrieben. |

Beispielaufruf (der dem Authentifizierungsstatus entsprechende Anfragewert ist hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] führt in allen drei Fällen eine ID[Synchronisierung zwischen CID &#x200B;](../reference/ids-in-aam.md) UUID durch.

>[!MORELIKETHIS]
>
>* [Kunden-IDs und Authentifizierungsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=de)

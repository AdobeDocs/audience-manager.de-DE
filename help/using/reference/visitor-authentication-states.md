---
description: Der Authentifizierungsstatus des Besuchers in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Gerätehilfen-Profil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNKNOWN und LOGGED_OUT in Ereignis-Aufrufen auf dieselbe Weise.
keywords: dpm.demdex.net
seo-description: Der Authentifizierungsstatus des Besuchers in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Gerätehilfen-Profil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNKNOWN und LOGGED_OUT in Ereignis-Aufrufen auf dieselbe Weise.
seo-title: Besucherauthentifizierungsstatus in Audience Manager
solution: Audience Manager
title: Besucherauthentifizierungsstatus in Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Besucherauthentifizierungsstatus in Audience Manager{#visitor-authentication-states-in-audience-manager}

Der Authentifizierungsstatus des Besuchers in Audience Manager bestimmt, ob die neuen Eigenschaftsinformationen in das authentifizierte Profil des Besuchers oder in das Gerätehilfen-Profil geschrieben werden, aus dem die Daten erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNKNOWN und LOGGED_OUT in Ereignis-Aufrufen auf dieselbe Weise.

Ab dem ID-Dienst v1.5+ enthält die `setCustomerID`-Methode das optionale `AuthState`-Objekt. [!DNL Experience Cloud] `AuthState` identifiziert Besucher gemäß ihrem  [Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] verarbeitet die realisierten Eigenschaften unterschiedlich, je nachdem, welcher Authentifizierungsstatus im Aufruf und in der  [Profil Merge-Regel, die Sie für die Segmentierung ](../features/profile-merge-rules/merge-rules-dashboard.md) verwenden, übergeben wurde.

## Authentifizierungsstatus: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Anforderungswert </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informationen </b> aus dem authentifizierten Profil </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Eigenschaften </b> zum Schreiben in das authentifizierte Profil </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Ja, wenn die Authentifizierungsoption Merge Rule = "Last Authenticated Profils". </p> </td> 
   <td colname="col3" morerows="1"> <p>Nein, die Eigenschaftsdaten werden dem Profil des Geräts hinzugefügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nein, wenn die Authentifizierungsoption Merge Rule = "Current Authenticated Profils" oder "No Authenticated Profil". </p> </td> 
  </tr> 
 </tbody> 
</table>

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentifizierungsstatus: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Anforderungswert </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informationen </b> aus dem authentifizierten Profil </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Eigenschaften </b> zum Schreiben in das authentifizierte Profil </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Ja, wenn die Authentifizierungsoption Merge Rule = "Current Authenticated Profils" oder "Last Authenticated Profils" ist. </p> </td> 
   <td colname="col3" morerows="1"> <p>Ja, die Eigenschaftendaten werden dem authentifizierten Profil hinzugefügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nein, wenn die authentifizierte Option Merge Rule = "No Authenticated Profil". </p> </td> 
  </tr> 
 </tbody> 
</table>

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentifizierungsstatus: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Anforderungswert </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informationen </b> aus dem authentifizierten Profil </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Eigenschaften </b> zum Schreiben in das authentifizierte Profil </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Ja, wenn die Merge-Regel für die authentifizierte Option = "Letzte authentifizierte Profil" </td> 
   <td colname="col3" morerows="1"> <p>Nein, die Eigenschaftsdaten werden in das Profil des Geräts geschrieben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Nein, wenn die Merge-Regel für die authentifizierte Option = "Aktuelle authentifizierte Profil"oder "Kein authentifiziertes Profil" </td> 
  </tr> 
 </tbody> 
</table>

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] führt in allen drei Fällen eine ID-Synchronisierung zwischen  [CID und ](../reference/ids-in-aam.md) UUID durch.

>[!MORELIKETHIS]
>
>* [Kunden-IDs und Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)


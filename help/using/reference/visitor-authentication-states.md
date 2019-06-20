---
description: Der Besucher-Authentifizierungsstatus in Audience Manager bestimmt, ob die neuen Eigenschaften in das authentifizierte Profil des Besuchers geschrieben werden oder ob die Daten vom Geräteprofil erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNBEKANNT und PROTOKOLLIERT_ OUT in Ereignisaufrufen auf die gleiche Weise.
keywords: dpm.demdex.net
seo-description: Der Besucher-Authentifizierungsstatus in Audience Manager bestimmt, ob die neuen Eigenschaften in das authentifizierte Profil des Besuchers geschrieben werden oder ob die Daten vom Geräteprofil erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNBEKANNT und PROTOKOLLIERT_ OUT in Ereignisaufrufen auf die gleiche Weise.
seo-title: Besucher-Authentifizierungsstatus in Audience Manager
solution: Audience Manager
title: Besucher-Authentifizierungsstatus in Audience Manager
uuid: d 748 c 0 c 3-5833-4 fb 9-ab 3 e -793 f 5 f 252 e 47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Besucher-Authentifizierungsstatus in Audience Manager{#visitor-authentication-states-in-audience-manager}

Der Besucher-Authentifizierungsstatus in Audience Manager bestimmt, ob die neuen Eigenschaften in das authentifizierte Profil des Besuchers geschrieben werden oder ob die Daten vom Geräteprofil erfasst wurden. Audience Manager verarbeitet die Besucher-ID-Authentifizierungsstatus UNBEKANNT und PROTOKOLLIERT_ OUT in Ereignisaufrufen auf die gleiche Weise.

Ab [!DNL Experience Cloud] dem ID-Dienst v 1.5 + enthält die `setCustomerID` Methode das optionale `AuthState` Objekt. `AuthState` identifiziert Besucher gemäß ihrem [Authentifizierungsstatus](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). [!DNL Audience Manager] verarbeitet die neu gestalteten Eigenschaften je nach dem Authentifizierungsstatus, der im Aufruf übergeben wird, und der [Profilzusammenführung, die](../features/profile-merge-rules/merge-rules-dashboard.md) Sie für die Segmentierung verwenden.

## Authentifizierungsstatus: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Anforderungswert </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informationen</b> aus dem authentifizierten Profil lesen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Neue</b> Eigenschaften in das authentifizierte Profil schreiben </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Ja, wenn die Option "Authentifizierte Optionen zusammenführen" =" Zuletzt authentifizierte Profile" . </p> </td> 
   <td colname="col3" morerows="1"> <p>Nein, die Eigenschaftsdaten werden dem Geräteprofil hinzugefügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nein, wenn die Option "Authentifizierte Optionen zusammenführen" =" Zur Zeit authentifizierte Profile" oder "Kein Authentifizierungsprofil" . </p> </td> 
  </tr> 
 </tbody> 
</table>

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentifizierungsstatus: AUTHENTIFIZIERT {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Anforderungswert </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informationen</b> aus dem authentifizierten Profil lesen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Neue</b> Eigenschaften in das authentifizierte Profil schreiben </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Ja, wenn die Option "Authentifizierte Optionen zusammenführen" =" Zur Zeit authentifizierte Profile" oder "Zuletzt authentifizierte Profile" . </p> </td> 
   <td colname="col3" morerows="1"> <p>Ja, die Eigenschaftsdaten werden dem authentifizierten Profil hinzugefügt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Nein, wenn die Option "Authentifizierte Option" =" Kein Authentifizierungsprofil" . </p> </td> 
  </tr> 
 </tbody> 
</table>

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentifizierungsstatus: LOGGED_ OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Anforderungswert </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Informationen</b> aus dem authentifizierten Profil lesen </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Neue</b> Eigenschaften in das authentifizierte Profil schreiben </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>2</code> </p> </td> 
   <td colname="col2"> Ja, wenn die Option "Authentifizierte Optionen zusammenführen" =" Zuletzt authentifizierte Profile « </td> 
   <td colname="col3" morerows="1"> <p>Nein, die Eigenschaftsdaten werden in das Geräteprofil geschrieben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Nein, wenn die Option "Authentifizierte Optionen zusammenführen" =" Zur Zeit authentifizierte Profile" oder "Kein Authentifizierungsprofil « </td> 
  </tr> 
 </tbody> 
</table>

Beispielaufruf (der Anforderungswert, der dem Authentifizierungsstatus entspricht, wird hervorgehoben):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] führt in allen drei Fällen eine ID-Synchronisierung zwischen [CID und UUID](../reference/ids-in-aam.md) durch.

>[!MORE_ LIKE_ THIS]
>
>* [Kunden-IDs und Authentifizierungsstatus](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)


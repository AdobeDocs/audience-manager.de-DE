---
description: Aktualisieren Sie Ihren Code so, dass er d_cid oder d_cid_ic anstelle von d_dpid und d_dpuuid verwendet. Die Variablen DPID und DPUUID funktionieren weiterhin, aber Sie sollten sie als veraltet betrachten. Dazu gehören die DPID- und DPUUID-Varianten ohne das Präfix d_.
seo-description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-title: CID Replaces DPID and DPUUID
solution: Audience Manager
title: CID ersetzt DPID und DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: Reference
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 1%

---

# CID ersetzt DPID und DPUUID{#cid-replaces-dpid-and-dpuuid}

Aktualisieren Sie Ihren Code, um `d_cid` oder `d_cid_ic` anstelle von `d_dpid` und `d_dpuuid` zu verwenden. Die Variablen DPID und DPUUID funktionieren weiterhin, aber Sie sollten sie als veraltet betrachten. Dazu gehören die Varianten DPID und DPUUID ohne die `d_ prefix`.

## DPID und DPUUID: Eine Überprüfung {#dpid-dpuuid-review}

DPID und DPUUID sind Schlüssel-Wert-Paare, die eine Datenanbieter-ID und eine Benutzer-ID enthalten. Diese Schlüssel-Wert-Paare verknüpfen Provider-IDs mit Benutzer-IDs. Sie senden Daten bei Ereignisaufrufen, eingehenden Synchronisierungsereignissen und ID-Aufrufen ein. Ohne sie hätten [!DNL Audience Manager] und andere Services oder Funktionen keine Möglichkeit, IDs abzugleichen und zu synchronisieren. Diese Variablen werden manchmal mit oder ohne das `d_` Präfix ausgedrückt, wie unten gezeigt. Beachten Sie, dass im Code *kursiv* einen Variablenplatzhalter angibt.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntax </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Datenanbieter-ID (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eindeutige Benutzer-ID des Datenanbieters (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Diese Schlüssel-Wert-Paare funktionieren weiterhin, sind aber veraltet. Sie sollten Ihren Code aktualisieren, um stattdessen CID oder CID_IC zu verwenden.

## CID und CID_IC: Über {#cid-cidic-about}

Die Schlüssel-Wert-Paare CID und CID_IC ersetzen DPID und DPUUID. Sie bieten dieselben Funktionen wie die DPID und die DPUUID, sind aber effizienter, da sie die Datenanbieter-ID (oder den Integrations-Code) und die Benutzer-ID in einem einzigen Schlüssel-Wert-Paar enthalten. In jedem Schlüssel-Wert-Paar:

* Das Symbol = trennt den Schlüssel von den zugehörigen Werten.
* Das nicht druckbare ASCII-Zeichen %01 trennt die Werte.

`d_cid` und `d_cid_ic` verwenden die unten dargestellte Syntax. Beachten Sie, dass im Code *kursiv* einen Variablenplatzhalter angibt.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntax </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Customer ID (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kunden-ID-Integrationscode (CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> Ein <span class="term">-Integrationscode</span> ist eine alternative ID, die Sie anstelle der vom Audience Manager <span class="keyword"> Data Source-ID verwenden können</span>. Siehe <a href="../features/manage-datasources.md#create-data-source"> Erstellen einer Daten-Source</a> , wenn Sie einen Integrations-Code konfigurieren müssen. </p> </td> 
  </tr> 
 </tbody> 
</table>

Siehe auch [URL-Variablen und Syntax für deklarierte IDs](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>Sie können Integrations-Codes für Ihre eigenen Datenquellen und für globale [freigegebene Datenquellen](../features/datasources-list-and-settings.md#settings-menu-options) verwenden, auf die Sie Zugriff haben. Sie können beispielsweise Integrations-Codes verwenden, wenn Sie mit Datenquellen für mobile Kennungen arbeiten. Verwenden Sie die folgenden Integrations-Codes, genau wie unten angegeben:

* **DSID_20914** für GAID, für Geräte, auf denen das Android-Betriebssystem ausgeführt wird.
* **DSID_20915** für IDFA, wobei es sich um Geräte handelt, auf denen das iOS-Betriebssystem ausgeführt wird.

**Beispiele**

In der folgenden Tabelle finden Sie Beispiele nach Ereignistyp.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ereignistyp </th> 
   <th colname="col2" class="entry"> Beispiel </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ereignis- </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">Neu: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Veraltet: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eingehende Synchronisation (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">Neu: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Veraltet: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generieren der Audience Manager-UUID (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">Neu: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Veraltet: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Jeder Aufruf kann auch mehrere `d_cid` und `d_cid_ic` Schlüssel-Wert-Paare wie diese enthalten:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Wichtige Überlegungen für Entwicklungs-Teams {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Element </p> </th> 
   <th colname="col2" class="entry"> <p>Beschreibung </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL-Codierung </p> </td> 
   <td colname="col2"> <p>Ihre Entwicklungs<i>Teams müssen </i> URL-Codierung auf die folgenden Variablen im CID-Schlüssel-Wert-Paar anwenden: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Hinweis: Sie müssen die Benutzer-ID und den Integrationscode (<i>) </i> einer Zeichenfolge verketten. Dies liegt daran, dass das ASCII-Zeichen %01, das die beiden Variablen trennt, nicht in der URL-Codierung erfasst werden darf. </p> </p> <p>Die URL-Codierung stellt sicher, dass Ihre Benutzer-IDs und Integrations-Codes, die reservierte oder unsichere Zeichen wie + oder = enthalten, aber nicht beschränkt auf + oder =, korrekt an unsere Server übertragen werden. </p> <p>Verwenden Sie als Referenz die <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII</a>Kodierungstabelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Verwenden von Integrations-Codes für globale freigegebene Datenquellen </p> </td> 
   <td colname="col2"> <p>Sie können Integrations-Codes für Ihre eigenen Datenquellen und für globale <a href="../features/datasources-list-and-settings.md#settings-menu-options"> freigegebene Datenquellen verwenden</a> auf die Sie Zugriff haben. Sie können beispielsweise Integrations-Codes verwenden, wenn Sie mit Datenquellen für mobile Kennungen arbeiten. Verwenden Sie die folgenden Integrations-Codes, genau wie unten angegeben: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> für GAID, für Geräte, auf denen das Android-Betriebssystem ausgeführt wird. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> für IDFA, wobei es sich um Geräte handelt, auf denen das iOS-Betriebssystem ausgeführt wird. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

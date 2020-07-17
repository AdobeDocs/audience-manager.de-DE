---
description: Eine optionale boolesche Konfiguration, die festlegt, ob DIL Daten an die Adobe Experience Cloud-Gerätekooperation sendet oder nicht.
seo-description: Eine optionale boolesche Konfiguration, die festlegt, ob DIL Daten an die Adobe Experience Cloud-Gerätekooperation sendet oder nicht.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c5362a38-93c0-4edb-bdcb-106e43f33a92
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 78%

---


# isCoopSafe{#iscoopsafe}

Eine optionale boolesche Konfiguration, die festlegt, ob DIL Daten an die Adobe Experience Cloud-Gerätekooperation sendet oder nicht.

## Anforderungen {#requirements}

To use `isCoopSafe` you must:

* Verwenden Sie [!UICONTROL DIL] v6.11 oder höher.
* Teilnahme an der [Experience Cloud-Gerätekooperation](https://docs.adobe.com/content/help/de-DE/device-co-op/using/home.html). Zukünftige Mitglieder der Gerätekooperation sollten diese Dokumentation ebenfalls lesen, um festzustellen, ob `isCoopSafe` mögliche Fragen über die Verwendung der Daten zur Erstellung eines Gerätediagramms beantwortet.

* Work with your [!DNL Adobe] consultant to set an allowlist or a denylist flag on your Device Co-op account. Es gibt keinen Selbstbedienungspfad, um diese Flags zu aktivieren.

## Nutzungsszenarios {#use-cases}

`isCoopSafe` ist in zwei Nutzungsszenarios hilfreich, in denen es um die Erfassung der Daten von aktuellen oder zukünftigen Mitgliedern der Gerätekooperation geht. Diese Nutzungsszenarios beziehen sich darauf, wie Site-Besucherdaten an die Gerätekooperation übergeben werden, um das Gerätediagramm zu erstellen. In der folgenden Tabelle wird beschrieben, wie `isCoopSafe` in diesen Nutzungsszenarios verwendet wird, um Daten an das Gerätediagramm zu senden oder die Datenübergabe zu blockieren.

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Anwendungsfall </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Authentifizierte Besucher</b> </p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code to control how data for authenticated visitors who have or have not accepted term-of-use agreements is used by the Device Co-op to build the device graph. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL auf Drittanbieter-Sites</b> </p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code for use on third-party sites where you: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">Sie können nicht sicherstellen, dass authentifizierte Besucher die Nutzungsvereinbarungen akzeptiert haben. </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">Sie müssen steuern, wie die Daten durch die Gerätekooperation verwendet werden, um das Gerätediagramm zu erstellen. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Syntax und Codebeispiel {#syntax-code-sample}

**Syntax:** `isCoopSafe: true | false`

Die booleschen Optionen bestimmen, ob Kundendaten von der Gerätekooperation verwendet werden können.

* `isCoopSafe: true`: Von einem Mobile-SDK oder einer Website erfasste Besucherdaten *können* zur Erstellung des Gerätediagramms verwendet werden.

* `isCoopSafe: false`: Von einem Mobile-SDK oder einer Website erfasste Besucherdaten *können nicht* zur Erstellung des Gerätediagramms verwendet werden.

**Code-Beispiel**

Legen Sie dies fest, wenn DIL instanziiert.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## POST-Parameter für Ereignisaufrufe {#post-parameters}

Depending on the flag you set ( `true` or `false`), [!UICONTROL DIL] translates `isCoopSafe` into these POST parameters and sends them to [!DNL Adobe] in an event call:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

Anhand der POST-Parameter stellt die [!DNL Experience Cloud]-Gerätekooperation fest, ob Benutzerdaten in das Gerätediagramm aufgenommen werden dürfen oder nicht. Die folgende Tabelle definiert die Beziehung zwischen den booleschen Kennzeichnungen von `isCoopSafe` und den im Ereignisaufruf übergebenen POST-Parametern. Wenn Sie `isCoopSafe` nicht verwenden, wird keiner von ihnen in einem Ereignisaufruf übergeben.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Konfigurationsstatus </th> 
   <th colname="col2" class="entry"> POST-Parameter </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>Die Gerätekooperation kann Besucherdaten verwenden, um das Gerätediagramm zu erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>Die Gerätekooperation kann keine Besucherdaten verwenden, um das Gerätediagramm zu erstellen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Post-Instanziierungs-APIs {#post-instantiation}

Mit diesen APIs können Sie den Status von `isCoopSafe` überschreiben. Sie ermöglichen es, den Status nach der Instanziierung bzw. Anmeldung eines Besuchers auf einer Site oder bei einer Single-Page-Anwendung zu ändern, wenn die Seite nicht aktualisiert wird. Beispielsweise müssen Sie diese APIs aufrufen, wenn sich ein Benutzer auf Ihrer Site oder bei Ihrer Anwendung authentifiziert und später eine Nutzungsrichtlinie akzeptiert, die der Gerätekooperation die Verwendung seiner Daten ermöglicht.

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopSafe(); </code> </p> </td> 
   <td colname="col2"> <p>Sets POST parameter <code> d_coop_safe=1 </code> in all subsequent event calls. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance.api.setAsCoopUnsafe(); </code> </p> </td> 
   <td colname="col2"> <p>Sets POST parameter <code> d_coop_unsafe=1 </code> in all subsequent event calls. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->


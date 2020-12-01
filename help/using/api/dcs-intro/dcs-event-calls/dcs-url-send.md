---
description: Beginn für Informationen zum Durchführen von /Ereignis-Aufrufen an den DCS. Dieser Abschnitt enthält Informationen zur Aufrufsyntax, zu Parametern, zur Formatierung und ein Anforderungsbeispiel.
seo-description: Beginn für Informationen zum Durchführen von /Ereignis-Aufrufen an den DCS. Dieser Abschnitt enthält Informationen zur Aufrufsyntax, zu Parametern, zur Formatierung und ein Anforderungsbeispiel.
seo-title: Senden von Daten an den DCS
solution: Audience Manager
title: Senden von Daten an den DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 6%

---


# Senden von Daten an den DCS {#send-data-to-the-dcs}

Beginn hier für Informationen zum Durchführen von `/event`-Aufrufen an [!DNL DCS]. Dieser Abschnitt enthält Informationen zur Aufrufsyntax, zu Parametern, zur Formatierung und ein Anforderungsbeispiel.

>[!NOTE]
>
>Im Code und in den Beispielen steht *italics* für einen variablen Platzhalter. Ersetzen Sie einen echten Wert für den Platzhalter, wenn Sie Daten an das [!DNL DCS] senden, mit dieser Methode.

## Aufrufsyntax {#dcs-call-syntax}

Eine einfache `URL`-Zeichenfolge, die Daten an das [!DNL DCS] sendet, verwendet die nachstehende Syntax.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Sie können Daten auch mit der `POST`-Methode an [!DNL DCS] senden. Die Aufrufsyntax wird unter [DCS API-Methoden](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md) beschrieben.

## Aufrufparameter {#dcs-call-parameters}

Die folgende Tabelle definiert die grundlegenden Komponenten eines einfachen [!DNL DCS]-Aufrufs.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komponente </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs enthält: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Ihr Domänenalias zugewiesen von <span class="keyword"> Audience Manager</span> (z. B. <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Die Zieldomäne, die immer <code> demdex.net</code> lautet. Siehe <a href="../../../reference/demdex-calls.md">Grundlegendes zu Aufrufen an die Domäne „demdex.net“</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifiziert den Aufruf als Ereignis-Aufruf. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definiert den Beginn der URL-Zeichenfolge, die die Daten enthält, die Sie an das <span class="wintitle"> DCS</span> senden möchten. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Ein eindeutiger Bezeichner im Schlüssel-Wert-Paar. </p> <p>Diese Schlüssel-Wert-Paare verwenden ein spezifisches Präfix, um den Datentyp zu identifizieren, den Sie an das <span class="wintitle"> DCS</span> senden. Weitere Informationen finden Sie unter <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Unterstützte Attribute für DCS-API-Aufrufe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Ein Variablenwert, der zu einem durch einen Schlüssel im Schlüssel-Wert-Paar definierten Satz gehört. </p> <p>Beim Arbeiten mit Werten: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Schließen Sie Zeichenfolgendaten in Dubletten-Anführungszeichen ein (z. B. <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Sie können mehrere Schlüssel an einen einzelnen Wert übergeben (z. B. <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionale Antwortparameter. </p> <p> Keiner dieser Schritte ist erforderlich, um Daten an den <span class="wintitle"> DCS</span> zu senden. Wenn <span class="wintitle"> DCS</span> eine Antwort zurückgeben soll, müssen Sie <code> d_rtbd=json</code> in Ihre Anforderung einbeziehen. </p> <p>Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Value Paare Definiert</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Beispielaufruf {#dcs-sample-call}

Dieses Beispiel zeigt die fiktive Firma [!DNL Acme, Inc.], die Daten über einen [!DNL HTTP]-Aufruf an [!DNL DCS] sendet. Beachten Sie, dass dieser Aufruf die optionalen Parameter `d_dst=1`, `d_rtbd=json` und `d_cb=callback` enthält. Diese weisen darauf hin, dass [!DNL Acme] eine [!DNL JSON] Antwort von [!DNL DCS] mit einer Rückruffunktion erhalten möchte. Denken Sie daran, das ist nur ein Beispiel. Ausschneiden und Einfügen dieses Codes sollten Sie vermeiden.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Nächste Schritte {#dcs-next-steps}

Jetzt, wo Sie mit dem Senden von Daten an das [!DNL DCS] vertraut sind, ist es an der Zeit, zu prüfen, wie Sie Daten zurückerhalten und diese Informationen analysieren können. Siehe [Daten vom DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md) empfangen.

>[!MORELIKETHIS]
>
>* [Schlüssel-Wert-Paare – Erklärung](../../../reference/key-value-pairs-explained.md)


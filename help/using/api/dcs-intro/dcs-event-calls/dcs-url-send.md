---
description: Hier beginnen, um Informationen zum Ausführen von /event-Aufrufen an den DCS zu erhalten. Dieser Abschnitt enthält Informationen zur Aufrufsyntax, zu Parametern, zur Formatierung und ein Beispiel für eine Anfrage.
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: Senden von Daten an den DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---

# Senden von Daten an den DCS {#send-data-to-the-dcs}

Beginnen Sie hier, um Informationen über `/event` Aufrufe an die [!DNL DCS] zu erhalten. Dieser Abschnitt enthält Informationen zur Aufrufsyntax, zu Parametern, zur Formatierung und ein Beispiel für eine Anfrage.

>[!NOTE]
>
>Im Code und in den Beispielen *kursiv* ein variabler Platzhalter. Ersetzen Sie den Platzhalter durch einen tatsächlichen Wert, wenn Sie mit dieser Methode Daten an den [!DNL DCS] senden.

## Aufrufsyntax {#dcs-call-syntax}

Eine einfache `URL`-Zeichenfolge, die Daten an den [!DNL DCS] sendet, verwendet die unten dargestellte Syntax.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Sie können auch Daten mithilfe der `POST` -Methode an die [!DNL DCS] senden. Die Aufrufsyntax wird unter [DCS-API-Methoden](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md) beschrieben.

## Aufrufparameter {#dcs-call-parameters}

In der folgenden Tabelle werden die grundlegenden Komponenten eines einfachen [!DNL DCS]-Aufrufs definiert.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Ihr Domain-Alias, der von <span class="keyword"> Audience Manager zugewiesen </span> (z. B. <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Die Ziel-Domain, die immer <code> demdex.net</code> ist. Siehe <a href="../../../reference/demdex-calls.md"> Aufrufe an die Domain „demdex.net“</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifiziert den Aufruf als einen Ereignisaufruf. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definiert den Beginn der URL-Zeichenfolge, die die Daten enthält, die Sie an den <span class="wintitle"> DCS senden </span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Eine eindeutige Kennung im Schlüssel-Wert-Paar. </p> <p>Diese Schlüssel-Wert-Paare verwenden ein bestimmtes Präfix, um den Datentyp zu identifizieren, den Sie an den <span class="wintitle"> DCS senden</span>. Weitere Informationen finden Sie unter <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> unterstützter Attribute für DCS-API-Aufrufe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Ein Variablenwert, der zu einem Satz gehört, der durch einen Schlüssel im Schlüssel-Wert-Paar definiert wird. </p> <p>Arbeiten mit Werten: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Schließen Sie Zeichenfolgendaten in doppelte Anführungszeichen ein (z. B. <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Sie können mehrere Schlüssel in für einen einzelnen Wert übergeben (z. B. <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatieren von Schlüssel-Wert-Paaren in DCS-Aufrufen</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionale Antwortparameter. </p> <p> Keine dieser Informationen ist erforderlich, um Daten an den <span class="wintitle"> DCS zu senden</span>. Wenn der <span class="wintitle"> DCS</span> jedoch eine Antwort zurückgeben soll, müssen Sie <code> d_rtbd=json</code> in Ihre Anfrage aufnehmen. </p> <p>Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Schlüssel-Wert-Paare definiert</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Beispielaufruf {#dcs-sample-call}

Dieses Beispiel zeigt, wie das fiktive Unternehmen Daten [!DNL Acme, Inc.] einem [!DNL HTTP]-Aufruf an die [!DNL DCS] sendet. Beachten Sie, dass dieser Aufruf die optionalen Parameter `d_dst=1`, `d_rtbd=json` und `d_cb=callback` enthält. Diese zeigen an, dass [!DNL Acme] eine [!DNL JSON] Antwort von der [!DNL DCS] mit einer Rückruffunktion erhalten möchte. Denken Sie daran, dies ist nur ein Beispiel. Diesen Code nicht ausschneiden und einfügen.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Nächste Schritte {#dcs-next-steps}

Da Sie nun mit dem Senden von Daten an die [!DNL DCS] vertraut sind, ist es an der Zeit, sich anzusehen, wie Sie Daten daraus zurückgewinnen und diese Informationen analysieren können. Siehe [Empfangen von Daten vom DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Schlüssel-Wert-Paare – Erklärung](../../../reference/key-value-pairs-explained.md)

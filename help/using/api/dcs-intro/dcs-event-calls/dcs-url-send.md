---
description: Beginnen Sie hier, um Informationen zu /event aufrufen. Dieser Abschnitt enthält Informationen über die Syntaxsyntax, Parameter, Formatierung und ein Beispiel für eine Anforderung.
seo-description: Beginnen Sie hier, um Informationen zu /event aufrufen. Dieser Abschnitt enthält Informationen über die Syntaxsyntax, Parameter, Formatierung und ein Beispiel für eine Anforderung.
seo-title: Daten an den DCS senden
solution: Audience Manager
title: Daten an den DCS senden
uuid: 024 e 307 d-bfcb -46 cf-ac 3 a-fc 71 df 0248 fe
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Daten an den DCS senden {#send-data-to-the-dcs}

Beginnen Sie hier, um weitere Informationen zum Durchführen `/event` von Aufrufen an [!UICONTROL DCS]. Dieser Abschnitt enthält Informationen über die Syntaxsyntax, Parameter, Formatierung und ein Beispiel für eine Anforderung.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Ersetzen Sie einen echten Wert für den Platzhalter, wenn Sie Daten an diese [!UICONTROL DCS] Methode senden.

## Syntax aufrufen {#dcs-call-syntax}

Eine einfache `URL` Zeichenfolge, die Daten an die [!UICONTROL DCS] folgende Syntax sendet:

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>=<i>val 1</i>, &amp;<i>key 2</i>=<i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code></pre>

>[!NOTE]
>
>Sie können Daten mithilfe der [!UICONTROL DCS]`POST` Methode auch an den Benutzer senden. Die Aufrufsyntax wird in [den DCS-API-Methoden beschrieben](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Aufrufparameter {#dcs-call-parameters}

Die folgende Tabelle definiert die grundlegenden Komponenten eines einfachen [!UICONTROL DCS] Aufrufs.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Komponente </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs enthält: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Ihr Domänenalias, der von <span class="keyword"> Audience Manager zugewiesen wurde</span> (z. B. <code> my_ domain. demdex. net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Die Zieldomäne, die immer <code> demdex. net</code>lautet. Siehe <a href="../../../reference/demdex-calls.md">Aufrufe an die Domäne „demdex.net“</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dieser Teil des Aufrufs: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifiziert den Aufruf als Ereignisaufruf. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definiert den Start der URL-Zeichenfolge, die die Daten enthält, die Sie an das <span class="wintitle"> DCS senden möchten</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Schlüssel</code> </p> </td> 
   <td colname="col2"> <p>Eine eindeutige Kennung im Schlüssel-Wert-Paar. </p> <p>Diese Schlüssel/Wert-Paare verwenden ein bestimmtes Präfix, um den Datentyp zu identifizieren, den Sie an das <span class="wintitle"> DCS senden</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Ein Variablenwert, der zu einem Satz gehört, der durch einen Schlüssel im Schlüssel-Wert-Paar definiert wird. </p> <p>Bei Verwendung von Werten: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Fügen Sie Zeichenfolgendaten in doppelte Anführungszeichen ein (z. <code> B. Alter = "41 bis 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Sie können mehrere Schlüssel in einem einzelnen Wert übergeben (z. <i><code>B. Schlüssel</i>=<i>val 1, val 2, val 3</i></code></i>). </i></li> 
     </ul> </p> <p>Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatieren von Schlüssel/Wert-Paaren in DCS-Aufrufen</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb =<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionale Antwortparameter. </p> <p> Zum Senden von Daten an das <span class="wintitle"> DCS</span>sind keine Daten erforderlich. Wenn das <span class="wintitle"> DCS</span> jedoch eine Antwort zurückgeben soll, müssen Sie <code> d_ rtbd = json</code> in Ihre Anforderung einschließen. </p> <p>Siehe <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Wert-Paare.</a> </p> </td> 
  </tr>
 </tbody>
</table>

## Beispielaufruf {#dcs-sample-call}

Dieses Beispiel zeigt das fiktive Unternehmen [!DNL Acme, Inc.] , das über einen [!UICONTROL DCS][!DNL HTTP] Aufruf Daten an die Variable sendet. Beachten Sie, dass dieser Aufruf die optionalen Parameter `d_dst=1`, `d_rtbd=json``d_cb=callback`und. Diese weisen darauf hin, dass [!DNL Acme][!DNL JSON] eine Antwort von der [!UICONTROL DCS] Funktion mit einer Rückruffunktion empfangen werden soll. Denken Sie daran, dass dies nur ein Beispiel ist. Ausschneiden und Einfügen Sie diesen Code nicht.

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

## Nächste Schritte {#dcs-next-steps}

Nachdem Sie sich mit dem Senden von Daten an die Benutzer [!UICONTROL DCS]vertraut machen, sollten Sie sich überlegen, wie Sie Daten daraus abrufen und diese Informationen analysieren. Siehe [Daten vom DCS empfangen](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORE_ LIKE_ THIS]
>
>* [Wichtige Wertpaare](../../../reference/key-value-pairs-explained.md)


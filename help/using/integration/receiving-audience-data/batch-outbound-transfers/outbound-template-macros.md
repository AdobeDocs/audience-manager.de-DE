---
description: Listet die Makros auf, mit denen Sie ausgehende Vorlagen erstellen können. Dazu gehören Dateinamenmakros, Header-Makros und Inhaltsmakros.
seo-description: Listet die Makros auf, mit denen Sie ausgehende Vorlagen erstellen können. Dazu gehören Dateinamenmakros, Header-Makros und Inhaltsmakros.
seo-title: Ausgehende Vorlagenmakros
solution: Audience Manager
title: Ausgehende Vorlagenmakros
uuid: dec 082 d 3-306 b -4 ff 5-afb 2-418 bd 543 d 8 d 0
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# Ausgehende Vorlagenmakros {#outbound-template-macros}

Listet die Makros auf, mit denen Sie ausgehende Vorlagen erstellen können. Dazu gehören Dateinamenmakros, Header-Makros und Inhaltsmakros.

## Dateiname und Dateiheader-Makros {#file-name-header-macros}

In der Tabelle werden die Makros aufgelistet und beschrieben, die Sie im Dateinamen verwenden können, und um Kopfzeilenfelder zu definieren. Beispiele für Codebeispiele finden Sie unter [Ausgehende Makrobeispiele](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_ SOH </code> </p> </td> 
   <td colname="col2"> <p>Ein nicht druckbares ASCII-Zeichen. Es zeigt den Anfang einer Zeile oder einen Inhaltsabschnitt an. Sie kann auch zum Trennen von Datenspalten in einer Datei verwendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>Benutzer-ID-Schlüsseldatenanbieter-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>Bestell-/Ziel-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ ALIAS </code> </p> </td> 
   <td colname="col2"> <p>Ein Alias für eine Bestell-/Ziel-ID. </p> <p>Der Alias wird in der Admin-Benutzeroberfläche festgelegt. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Gibt die Aufteilung von ausgehenden Dateien in mehrere Teile an. Ersetzen Sie den SPLITNUM-Abschnitt im Dateinamen durch die Teil-Nummer, die Nullen voraussetzt, und stellen Sie sicher, dass mindestens drei Zeichen für den SPLITNUM-Abschnitt vorhanden sind.</p>
   <p>Das MAKTNUM-Makro muss nicht von &lt; &gt; Zeichen umgeben sein.</p><p>Beispiel: <code>&lt; SYNC_ TYPE &gt;_ &lt; ORDER_ ID &gt;_ &lt; DPID &gt;_ &lt; SYNC_ MODE &gt;_ &lt; TIMESTAMP &gt; SPLITNUM. csv</code>
<p>s 3_ 123456_ 9999_ full_ 1566906141001. csv</p> 
<p>s 3_ 123456_ 9999_ full_ 1566906141002. csv</p> 
<p>s 3_ 123456_ 9999_ full_ 1566906141003. csv</p> 
<p>Die letzten drei Ziffern (001.002.003) in den obigen Beispielen sind die SPLITNUM-ids.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Gibt den Synchronisierungstyp an und beinhaltet Folgendes: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> voll </code>: Vollständige Synchronisierung. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Inkrementelle Synchronisierung. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Gibt die Datenübertragungsmethode an und beinhaltet Folgendes: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Dieses Makro wird als Trennzeichen verwendet und fügt eine Registerkarte zwischen Feldern ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Eine 10-stellige UTC- und Unix-Zeitstempel. </p> <p>Sie kann auch als <code> &lt; TIMESTAMP; formatiert werden. format = "JJJMMDDHHMSS" &gt; </code> folgende Java-Datums-/Zeitstempelformatierungsregeln. </p> </td> 
  </tr>

</tbody> 
</table>

## Inhaltsmakros {#content-macros}

Makros zum Formatieren des Inhalts einer Datendatei. Beispiele für Codebeispiele finden Sie unter [Ausgehende Makrobeispiele](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_ CURLY_ BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Fügt ein schließende Klammernklammernzeichen ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Unique User ID des Datenanbieters </span>. </p> <p>Dies ist die ID für den Datenpartner, an den Sie Daten in einer ausgehenden Datei senden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Gibt eine Liste zurück, die mehrere IDs für einen Datenpartner enthält. Dies ist nützlich, wenn Sie eine große Organisation mit mehreren Unterteilungen oder anderen Organisationsgruppen haben, für die Sie Daten freigeben dürfen. Dieses Makro gibt eine Liste der IDs für diese untergeordneten Gruppen zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>Die Ausgabe dieses Makros ordnet die Datenanbieter-ID (DPID) den eindeutigen Benutzer-IDs (DPUUID) zu. Dieses Makro muss über eine Formatierungszeichenfolge verfügen, um die Ausgabe zu steuern. Die Beispielausgabe würde wie folgt aussehen: </p> <p> <code> " dpids = dpid 1, dpid 2,… dpid n | maxmappings = n | format = json " </code> </p> <p>Mit der <code></code> Einstellung "maxmappings" wird festgelegt, wie viele Zuordnungen das Makro zurückgeben soll. Wenn <code> maxmappings = 0 </code>, gibt dieses Makro alle Zuordnungen für jede angegebene DPID zurück. Die Daten werden nach Zeitstempel sortiert (erster erster Wert) und gibt Ergebnisse mit dem größten Zeitstempel zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if (SEGMENT_ LIST &amp; &amp; REMOVED_ SEGMENT_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p>Diese Kombination von Makros erstellt eine bedingte Anweisung, in der die Segmente aufgeführt sind, zu denen die Benutzer gehören und aus denen entfernt wurden. Wenn beide Bedingungen nicht erfüllt sind oder keine Daten vorhanden sind, wird eine leere Zeichenfolge zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_ CURLY_ BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Fügt ein öffnendes geschweifte Klammernklammernzeichen ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_ OUT </code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. Verwenden Sie nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>Bestell- oder Ziel-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ ATTRIBUTE_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. Verwenden Sie nicht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ ATTRIBUTE_ VALUE </code> </p> </td> 
   <td colname="col2"> <p>Gibt <code> 1 </code> als statischer, hartkodierter Wert zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>Partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Ein Alias für eine Bestell-/Ziel-ID. </p> <p>Der Alias wird in der Admin-Benutzeroberfläche festgelegt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_ SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Gibt ggf. eine Liste von Segmenten zurück, die entfernt wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Gibt eine Liste von Segmenten in einer Liste zurück. Akzeptiert die folgenden optionalen Argumente: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> Segmentid </code>: Segment-ID. Herabgestuft. Verwenden <code> Sie sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: Kundensegment-ID. Herabgestuft. Verwenden <code> Sie sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: Segment-ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Gibt <code> 5 </code>, einen statischen hartkodierten Wert zurück, der Daten als Segmentdaten identifiziert. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Veraltet. Verwenden Sie nicht. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> Lastupdatetime </code>: Ein Unix-Zeitstempel, der angibt, wann ein Segment zuletzt erstellt wurde. </li> 
    </ul> <p>Setzen Sie diese Variablen nach dem Makro in geschweifte Klammern. Dieser Code trennt beispielsweise die Ergebnisse durch einen senkrechten Strich "|" Zeichen: <code> &lt; SEGMENT_ LIST: {seg|&lt; seg. type &gt;, &lt; seg. sid &gt;}; separator = "," &gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ ATTRIBUTE </code> </p> </td> 
   <td colname="col2"> <p>Gibt <code> 1 </code>als statischer hartkodierter Wert zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Gibt den Synchronisierungstyp an und beinhaltet Folgendes: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> voll </code>: Vollständige Synchronisierung. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Inkrementelle Synchronisierung. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Gibt die Datenübertragungsmethode an und beinhaltet Folgendes: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Dieses Makro wird als Trennzeichen verwendet und fügt eine Registerkarte zwischen Feldern ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Gibt eine Liste mit Eigenschaften zurück. Akzeptiert die folgenden optionalen Argumente: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifiziert Eigenschaften nach numerischen ID. Rückgabe: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> , der eine DPM-Eigenschaft kennzeichnet (offline, von einem eingehenden Auftrag aufgelöst). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> , der eine regelbasierte Eigenschaft (Echtzeit, über das DCS) identifiziert. </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> Traitid </code>: Eigenschafts-ID. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> Lastrealized </code>: Das letzte Mal, wenn die Eigenschaft das letzte Mal realisiert wurde. Unix-Zeitstempel. </li> 
    </ul> <p>Setzen Sie diese Variablen nach dem Makro in geschweifte Klammern. Dieser Code trennt beispielsweise die Ergebnisse durch einen senkrechten Strich "|" Zeichen: <code> &lt; TRAIT_ LIST: {trait|&lt; trait. Id &gt;, &lt; trait. lastrealized &gt;}; separator = "," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> -Benutzer-ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Beispiele für ausgehende Makros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)


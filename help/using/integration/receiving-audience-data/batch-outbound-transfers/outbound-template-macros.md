---
description: Listet die Makros auf, mit denen Sie ausgehende Vorlagen erstellen können. Dazu gehören Dateinamenmakros, Kopfzeilenmakros und Inhaltsmakros.
seo-description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-title: Outbound Template Macros
solution: Audience Manager
title: Ausgehende Vorlagenmakros
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
exl-id: 6988d0e5-7a99-4291-91d3-bcd3a15630fd
source-git-commit: d76505fda1ba448a1aaa3a756ef3bcf193a2718a
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# Ausgehende Vorlagenmakros {#outbound-template-macros}

Listet die Makros auf, mit denen Sie ausgehende Vorlagen erstellen können. Dazu gehören Dateinamenmakros, Kopfzeilenmakros und Inhaltsmakros.

## Dateiname und Dateikopfzeilen-Makros {#file-name-header-macros}

In der Tabelle werden die Makros aufgelistet und beschrieben, die Sie im Dateinamen verwenden können, sowie zur Definition von Kopfzeilenfeldern. Codebeispiele finden Sie unter [Beispiele für ausgehende Makros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>Ein nicht druckbares ASCII-Zeichen. Er gibt den Anfang einer Zeile oder eines Inhaltsabschnitts an. Sie kann auch zum Trennen von Datenspalten in einer Datei verwendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>Benutzer-ID-Schlüssel Datenanbieter-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Ermöglicht die Erstellung von mehrzeiligen Kopfzeilen für ausgehende Bestellungen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Bestell-/Ziel-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>Alias für eine Bestell-/Ziel-ID. </p> <p>Der Alias wird in der Administrator-Benutzeroberfläche festgelegt. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Gibt die Aufteilung der ausgehenden Dateien in mehrere Teile an. Ersetzen Sie den Abschnitt SPLITNUM im Dateinamen durch die Teilenummer, der Nullen vorangestellt sind, sodass für den Abschnitt SPLITNUM mindestens drei Zeichen erforderlich sind.</p>
   <p>Das SPLITNUM-Makro muss nicht von &lt;&gt; -Zeichen umgeben sein.</p><p>Beispiel: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_999_full_1566906141001.csv</p> 
<p>s3_123456_999_full_1566906141002.csv</p> 
<p>s3_123456_999_full_1566906141003.csv</p> 
<p>Die letzten drei Ziffern (001.002.003) in den obigen Beispielen sind die SPLITNUM-Kennungen.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Gibt den Synchronisierungstyp an und umfasst: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Vollständige Synchronisierung. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Inkrementelle Synchronisation. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Gibt die Datenübertragungsmethode an und umfasst: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Dieses Makro wird als Trennzeichen verwendet und fügt eine Registerkarte zwischen Feldern ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UTC-, Unix-Zeitstempel. </p> <p>Sie kann auch als <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> entsprechend den Java-Formatierungsregeln für Datum/Zeitstempel formatiert werden. </p> </td> 
  </tr>

</tbody> 
</table>

## Inhaltsmakros {#content-macros}

Makros zum Formatieren des Inhalts einer Datendatei. Codebeispiele finden Sie unter [Beispiele für ausgehende Makros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Fügt eine schließende geschweifte Klammer <code>}</code> ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Eindeutige Benutzerkennung für Datenanbieter </span>. </p> <p>Dies ist die ID für den Datenpartner, an den Sie Daten in einer ausgehenden Datei senden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Gibt eine Liste mit mehreren IDs für einen Datenpartner zurück. Dies ist nützlich, wenn Sie eine große Organisation mit mehreren Unterteilungen oder anderen Organisationsgruppen haben, für die Sie Daten freigeben können. Dieses Makro gibt eine Liste der IDs für diese untergeordneten Gruppen zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>Die Ausgabe dieses Makros ordnet die Datenanbieter-ID (DPID) den zugehörigen eindeutigen Benutzer-IDs (DPUUID) zu. Dieses Makro muss über eine Formatierungszeichenfolge verfügen, um seine Ausgabe zu steuern. Die Beispielausgabe würde wie folgt aussehen: </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>Die Einstellung <code> maxMappings </code> bestimmt, wie viele Zuordnungen das Makro zurückgeben soll. Wenn <code> maxMappings=0 </code>, gibt dieses Makro alle Zuordnungen für jede angegebene DPID zurück. Die Daten werden nach Zeitstempel sortiert (neueste zuerst) und geben die Ergebnisse mit dem größten Zeitstempel zuerst zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>Diese Kombination von Makros erstellt eine bedingte Anweisung, in der die Segmente aufgelistet werden, zu denen die Benutzer gehören und aus denen sie entfernt wurden. Es wird eine leere Zeichenfolge zurückgegeben, wenn beide Bedingungen nicht erfüllt sind oder keine Daten vorliegen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Fügt eine geöffnete geschweifte Klammer <code>{</code> ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. Nicht verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Bestell- oder Ziel-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Herabgestuft. Nicht verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Gibt <code> 1 </code> als statischen, fest codierten Wert zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>Partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Alias für eine Bestell-/Ziel-ID. </p> <p>Der Alias wird in der Administrator-Benutzeroberfläche festgelegt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Gibt eine Liste mit entfernten Segmenten zurück, falls vorhanden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Gibt eine Liste von Segmenten in einer Liste zurück. Akzeptiert die folgenden optionalen Argumente: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>: Segment-ID. Herabgestuft. Verwenden Sie <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: Kundensegment-ID. Herabgestuft. Verwenden Sie <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: Segment-ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Gibt <code> 5 </code> zurück, einen statischen, fest codierten Wert, der Daten als Segmentdaten identifiziert. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Veraltet. Nicht verwenden. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: Ein Unix-Zeitstempel, der angibt, wann das Segment zuletzt aktualisiert wurde. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD28"> <code> lastRealizationTime </code>: Ein Unix-Zeitstempel, der angibt, wann ein Segment zuletzt realisiert wurde. </li>
    </ul> <p>Setzen Sie diese Variablen in geschweifte Klammern hinter das Makro. Dieser Code trennt beispielsweise die Ergebnisse mit dem senkrechten Strich "|": <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Gibt <code> 1 </code> als statischen, fest codierten Wert zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Gibt den Synchronisierungstyp an und umfasst: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Vollständige Synchronisierung. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Inkrementelle Synchronisation. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Gibt die Datenübertragungsmethode an und umfasst: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Dieses Makro wird als Trennzeichen verwendet und fügt eine Registerkarte zwischen Feldern ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Gibt eine Liste von Eigenschaften zurück. Akzeptiert die folgenden optionalen Argumente: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifiziert Eigenschaftstypen anhand numerischer ID. Gibt Folgendes zurück: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> , der eine DPM-Eigenschaft angibt (offline, von einem eingehenden Auftrag integriert). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code>, der eine regelbasierte Eigenschaft identifiziert (Echtzeit, über den DCS integriert). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: Kennung der Eigenschaft. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: Das letzte Mal, dass die Eigenschaft realisiert wurde. Unix-Zeitstempel. </li> 
    </ul> <p>Setzen Sie diese Variablen in geschweifte Klammern hinter das Makro. Dieser Code trennt beispielsweise die Ergebnisse mit dem senkrechten Strich "|": <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> Benutzer-ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Beispiele für ausgehende Makros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

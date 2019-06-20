---
description: Erforderliche Felder, Syntax und Regeln, die Sie bei der Formatierung einer eingehenden Eigenschaftendatei befolgen sollten.
seo-description: Erforderliche Felder, Syntax und Regeln, die Sie bei der Formatierung einer eingehenden Eigenschaftendatei befolgen sollten.
seo-title: Inbound Data File File Syntax, Ungültige Zeichen, Variablen und Beispiele
solution: Audience Manager
title: Inbound Data File File Syntax, Ungültige Zeichen, Variablen und Beispiele
uuid: 88699 b 29-1502-4183-a 9 a 4-be 70692 a 02 bb
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


# Inhalt der eingehenden Datendatei: Syntax, Ungültige Zeichen, Variablen und Beispiele{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Erforderliche Felder, Syntax und Regeln, die Sie bei der Formatierung einer eingehenden Eigenschaftendatei befolgen sollten.

## Syntax für Dateiinhalt {#file-content-syntax}

Felder in der eingehenden Datendatei müssen in der unten stehenden Reihenfolge angezeigt werden. In diesem Beispiel wurden die `<``>` Symbole hinzugefügt, um jedes Element visuell zu trennen. Sie müssen diese nicht in Ihre Datendatei aufnehmen.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Weitere akzeptierte Dateiinhaltsformate finden Sie unter [Benutzerdefinierte Partnerintegrationen](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Wir haben eine Grenze von 200 Zeilen, die für jede Benutzer-ID in der eingehenden Datendatei verarbeitet werden können. Wenn Sie beispielsweise 300 Zeilen für eine Benutzer-ID senden, werden die ersten 200 Zeilen beibehalten und die zusätzlichen 100 Zeilen werden verworfen. Im unten stehenden Beispiel sind Sie gut, da Sie jeweils 3 Zeilen für Benutzer-ID 1 und Benutzer-ID 2 senden. Wir erzwingen keine Begrenzung der Anzahl der Eigenschaften oder Schlüssel/Wert-Paare, die Sie in eine Zeile einschließen.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Definierte Dateivariablen {#file-variables-defined}

In der Tabelle werden die Variablen aufgeführt und definiert, die in einer ordnungsgemäß formatierten Datendatei verwendet werden. Eine *kursive* Formatierung gibt einen Variablenplatzhalter an.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>Benutzer-ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Eine Benutzer-ID kann: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Eine eindeutige Benutzer-ID, die von <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> UUID des Audience Manager) </a>zugewiesen wird. </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Eine eindeutige Benutzer-ID, die in Ihrem CRM-System ( <a href="../../../reference/ids-in-aam.md"> DPUUID, Audience Manager </a>) zugewiesen wird. </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Eine mobile Android- oder ios-Geräte-ID in ihrem ursprünglichen, nicht geänderten Formular, wie vom Betriebssystem bereitgestellt. </li> 
     </ul> </p> <p>Für mobile IDs: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA-Format: IDs müssen großgeschrieben und nicht Hash sein. Beispiel: <code> 6 D 92078 A -8246-4 BA 4-AE 5 B -76104861 E 7 DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android-Format: IDs müssen kleingeschrieben und nicht Hash sein. <code> Beispiel: 97987 bca-ae 59-4 c 7 d -94 ba-ee 4 f 19 ab 8 c 21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Trennen Sie die Benutzer-ID und die IDs mit einem einzelnen Tabulatortrennzeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>Eigenschafts-ID </i></code> </p> </td> 
   <td colname="col2"> <p>Die Eigenschaft <span class="keyword"> "Zielgruppen-Manager </span> «. Wir bitten, <i>nur die eingehenden Eigenschaften</i> in eingehenden Datendateien einzuschließen. In der eingehenden Datenübertragung werden keine anderen Eigenschaften verarbeitet. </p> <p> <p>Hinweis: Die Eigenschafts-ID kann mithilfe der GET-Methode gefunden werden, die Details zu all Ihren Eigenschaften zurückgibt. Weitere Informationen finden Sie unter <a href="../../../api/rest-api-main/api-traits.md"> Eigenschaften-API-Methoden </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatieren von Eigenschafts-IDs {#formatting-trait-ids}

Die folgende Tabelle beschreibt die Präfixe, die Eigenschaften oder IDs in einer eingehenden Datendatei identifizieren. Beispiele finden Sie in Beispieldateien [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) .

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Präfix </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ sid = </code> </p> </td> 
   <td colname="col2"> <p>Das Präfix <code> d_ sid </code> teilt unserem System mit, dass es sich bei der ID um eine <span class="keyword"> Zielgruppen-ID </span> handelt. Dies ist die gleiche ID, die in der Benutzeroberfläche angezeigt wird. Sie können auch Eigenschaften-IDs mit der API <code> GET </code> -Methode zurückgeben. Siehe <a href="../../../api/rest-api-main/api-traits.md"> Eigenschaften für Eigenschaften-API </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_ unsid = </code> </p> </td> 
   <td colname="col2"> <p>Mit <code> d_ unsid </code> präfix werden Benutzer aus dieser Eigenschaft entfernt. Das Präfix <code> d_ unsid </code> wird in einer <code> Überschreibungsdatei </code> ignoriert. </p> <p>Das <code> Präfix d_ unsid = </code> gibt unserem System an, dass es sich bei der ID um eine <span class="keyword"> Zielgruppen-ID </span> handelt. Dies ist die gleiche ID, die in der Benutzeroberfläche angezeigt wird. Sie können auch Eigenschaften-IDs mit der API <code> GET </code> -Methode zurückgeben. Siehe <a href="../../../api/rest-api-main/api-traits.md"> Eigenschaften für Eigenschaften-API </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic = </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Mit Trait-Regeln </a> können Sie Kriterien für die Eigenschaftenqualifikation festlegen. Wenn Sie eine Eigenschaftsregel als <code> ic = = merkmal-ID </code>formatieren, können Sie Eigenschaften in einer einfachen, kommageformatierten Liste senden. </p> <p>Nehmen wir beispielsweise an, Sie erstellen diese 3 Trait-Regeln: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic = = "123" </code> </li>
      <li> <code> ic = = "456" </code> </li>
      <li> <code> ic = = "789" </code> </li>
     </ul> </p> <p>Diese Eigenschaften sind mit dem <code> Zeichenschlüssel </code> verknüpft. Dadurch können Sie eine einfachere Liste der Eigenschaften in der Datendatei erstellen. Außerdem müssen Sie das <code> Präfix nicht </code> einschließen. Daher könnte der Inhalt Ihrer Datendatei wie folgt aussehen: </p> <p>
     <code><i>Benutzer-ID</i> &lt; TAB &gt; 123.456.789 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schlüssel-Wert-Paare </p> </td> 
   <td colname="col2"> <p>Eigenschaftsdaten können mithilfe von alphanumerischen Zeichenfolgen als Schlüssel-Wert-Paare formatiert werden. Es gibt verschiedene Möglichkeiten, Schlüssel-Wert-Paare zu formatieren, wie unten dargestellt: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> " key " = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> " key " =" value " </code> </li> 
     </ul><code> " age " =" 32 " </code> , <code> " geschlecht " = m </code> , <code> model =" pickup truck " </code> , <code> product = tablet </code> sind alle Beispiele für korrekt formatierte Schlüssel-Wert-Paare. </p> </td> 
  </tr>
 </tbody>
</table>

## Ungültige Zeichen in Eigenschafts-IDs, Benutzer-IDs und Schlüssel-Wert-Paaren {#invalid-chars}

### Eigenschafts-IDs

Merkmal-IDs bestehen nur aus numerischen Zeichen. Wir bitten, *nur die eingehenden Eigenschaften* in eingehenden Datendateien einzuschließen. In der eingehenden Datenübertragung werden keine anderen Eigenschaften verarbeitet.

### Anwender-IDs

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID-Typ </th> 
   <th colname="col2" class="entry"> Anforderung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>Verwenden Sie</i> keinen kodierten Doppelpunkt ( <code> % 3 A </code>) oder nicht kodierte Doppelpunkte (: ) in dpuuids. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile ios- oder Android-Geräte-ID </p> </td> 
   <td colname="col2"> <p>Mobilgeräte-IDs müssen genau wie hier gezeigt formatiert werden: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA-Format: IDs müssen großgeschrieben und nicht Hash sein. Beispiel: <code> 6 D 92078 A -8246-4 BA 4-AE 5 B -76104861 E 7 DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android-Format: IDs müssen kleingeschrieben und nicht Hash sein. <code> Beispiel: 97987 bca-ae 59-4 c 7 d -94 ba-ee 4 f 19 ab 8 c 21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Schlüssel-Wert-Paare

Falsch formatierte Wertnamen in einem Schlüssel-Wert-Paar verursachen ebenfalls Probleme. Befolgen Sie diese Regeln, wenn Sie den Wert in einem Schlüssel-Wert-Paar erstellen oder benennen:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Zeichen </th> 
   <th colname="col2" class="entry"> Anforderung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Anführungszeichen (") </p> </td> 
   <td colname="col2"> <p>Sie können das Anführungszeichen im Schlüssel und im Wert des Schlüssel-Wert-Paars verwenden, z. B.: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_ city = "New York", d_ city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> " d_ city " =" New York "," d_ city " =" San Francisco " </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bindestrich (-) </p> </td> 
   <td colname="col2"> <p>Bindestriche werden am Anfang der Schlüssel ignoriert. <code> Beispiel: -product = camera </code> wird als <code> Produkt = Kamera </code>interpretiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Verwenden</i> Sie <code> anstelle </code> leerer Werte in Schlüssel/Wert-Paaren keine TAB. Verwenden Sie <code> nur TAB </code> , um Variablen in der eingehenden Datendatei zu trennen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \ n,\ t </code> </p> </td> 
   <td colname="col2"> <p>Verwenden Sie nicht die neuen Zeichen- oder Tabulatorzeichen ( <code> \ n,\ t </code>) in Schlüssel oder Werten. </p> </td> 
  </tr>
 </tbody>
</table>

## Datendateibeispiele {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datendateiformat </th> 
   <th colname="col2" class="entry"> Beschreibung und Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>mit <code> d_ sid </code> oder <code> d_ unsid </code> </p> </td> 
   <td colname="col2"> <p>Diese Datendatei zeigt einen Benutzer, der für Eigenschaften 24, 26, 27 qualifiziert ist und aus der Eigenschaft 28 und 29 entfernt wurde. </p> <p> 
     <code>5976755918126206006027887090108252 &amp; amp; nbsp; &amp; amp; nbsp; d_ sid = 24, d_ sid = 26, d_ sid = 27, d_ unsid = 28, d_ unsid = 29 </code>
  </p> <p>Hinweis:  <p>Anstatt d_ unsid zu verwenden, können Sie auch Eigenschaften aus Benutzerprofilen entfernen, indem Sie die folgende Syntax verwenden: </p> <p> 
      <code>5976755918126206006027887090108252 &amp; amp; nbsp; 28:0, &amp; amp; nbsp; 29:0 </code>
  </p> <p> 
      <code>5976755918126206006027887090108252 &amp; amp; nbsp; 28:-1, &amp; amp; nbsp; 29:-1 </code>
  </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mit <code> ic = = </code> </p> </td> 
   <td colname="col2"> <p>Diese Eigenschaften wurden einer Eigenschaftenregel mit <code></code> dem Präfix hinzugefügt. Sie können sie daher der Datendatei, die durch Kommas getrennt ist, hinzufügen. Eine Registerkarte trennt die UUID und die Eigenschafts-IDs. Das <code></code> Präfix "ic" ist in der Datei nicht erforderlich. </p> <p><b>Numerische IDs</b> </p> <p> 
     <code>Dbwfoc 3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; 30608,50354,50338,50352,30626 </code>
  </p> <p><b>Zeichenfolgenids</b> </p> <p> 
     <code>Dbwfoc 3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; ic = 52, ic = 55 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>mit Schlüssel/Wert-Paaren </p> </td> 
   <td colname="col2"> Diese Dateidaten verwenden Schlüssel-Wert-Paare, um Daten an <span class="keyword"> Audience Manager </span>weiterzugeben. <p> 
     <code>5976755918126206006027887090108252 &amp; amp; nbsp; " gender» =» weiblich», "luxury_ shopper» =» yes» </code>
  </p> </td> 
  </tr> 
 </tbody> 
</table>

[Laden Sie](assets/ftp_dpm_1234_1445374061.overwrite) die Musterdatendatei herunter, wenn Sie weitere Beispiele benötigen. Die Dateierweiterung hat eine `.overwrite` Dateierweiterung. Sie können es mit einem einfachen Texteditor öffnen.

## Beispielmatrix {#examples-matrix}

Das nachstehende Diagramm zeigt Beispiele für die korrekte Formatierung Ihrer Inbound-Dateien, abhängig vom [Typ der IDs](../../../reference/ids-in-aam.md) und der Methode, mit der Sie zu Profilen Eigenschaften hinzufügen möchten.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID-Typ/-Vorgang </th> 
   <th colname="col2" class="entry"> Verwenden Sie d_ sid, um einem Benutzerprofil Eigenschaften hinzuzufügen. </th> 
   <th colname="col3" class="entry"> Verwenden Sie d_ unsid, um Eigenschaften aus einem Benutzerprofil zu entfernen. </th> 
   <th colname="col4" class="entry"> Senden Sie Schlüssel-Wert-Paare, um einem Benutzerprofil Eigenschaften hinzuzufügen. </th> 
   <th colname="col5" class="entry"> Verwenden Sie das Präfix "ic" , um einem Benutzerprofil Eigenschaften hinzuzufügen. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Beispiel 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Beispiel 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Beispiel 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Beispiel 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Advertising ID für Android-Geräte </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Beispiel 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Beispiel 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Beispiel 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Beispiel 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA für ios-Geräte </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Beispiel 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Beispiel 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Beispiel 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Beispiel 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ihre eigene CRM-ID (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Beispiel 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Beispiel 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Beispiel 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Beispiel 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiel 1 {#example-1}

Verwenden Sie Eigenschaften-IDs, um Eigenschaften für die Eigenschaftenzuordnung für uuids von Audience Manager zu senden.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Beispiel 2 {#example-2}

Verwenden Sie Eigenschaften-IDs, um Eigenschaften für die Deaktivierung von Eigenschaften für uuids von Audience Manager zu senden.

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

oder

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

oder

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Beispiel 3 {#example-3}

Senden Sie Schlüssel-Wert-Paare, um Eigenschaften für die Eigenschaften von Audience Manager-uuids hinzuzufügen.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

oder

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Beispiel 4 {#example-4}

Verwenden Sie das Präfix &quot;ic&quot; , um Trait-Qualifizierungsinformationen für die uuids von Audience Manager zu senden.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

oder

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Beispiel 5 {#example-5}

Verwenden Sie Eigenschaften-IDs, um Eigenschaften für die Eigenschaftenzuordnung für Android-Geräte zu senden.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Beispiel 6 {#example-6}

Verwenden Sie Eigenschafts-IDs, um Eigenschaften von Eigenschaften für Android-Geräte zu senden.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

oder

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

oder

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Beispiel 7 {#example-7}

Senden Sie Schlüssel-Wert-Paare, um Eigenschaften von Eigenschaften für Android-Geräte hinzuzufügen.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

oder

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Beispiel 8 {#example-8}

Verwenden Sie das Präfix &quot;ic&quot; , um Eigenschafteninformationen für Android-Geräte zu senden.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

oder

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Beispiel 9 {#example-9}

Verwenden Sie Eigenschaften-IDs, um Eigenschaften für die Eigenschaftenzuordnung für ios-Geräte zu senden.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Beispiel 10 {#example-10}

Verwenden Sie Eigenschafts-IDs, um Eigenschaften für das Absenden von Eigenschaften für ios-Geräte zu senden.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

oder

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

oder

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Beispiel 11 {#example-11}

Senden Sie Schlüssel-Wert-Paare, um Eigenschaften von Eigenschaften für ios-Geräte hinzuzufügen.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

oder

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Beispiel 12 {#example-12}

Verwenden Sie das Präfix &quot;ic&quot; , um Trait-Qualifizierungsinformationen für ios-Geräte zu senden.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

oder

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Beispiel 13 {#example-13}

Verwenden Sie Eigenschaften-IDs, um Eigenschaftsinformationen zu Eigenschaften für dpuuids zu senden.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Beispiel 14 {#example-14}

Verwenden Sie Eigenschafts-IDs, um Eigenschaften für dpuuids zu senden.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

oder

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

oder

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Beispiel 15 {#example-15}

Senden Sie Schlüssel-Wert-Paare, um Eigenschaften für dpuuids hinzuzufügen.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

oder

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Beispiel 16 {#example-16}

Verwenden Sie das Präfix &quot;ic&quot; , um Trait-Qualifizierungsinformationen für dpuuids zu senden.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

oder

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_ LIKE_ THIS]
>
>* [Trait Builder (Eigenschaftenaufbau)](../../../features/traits/about-trait-builder.md)


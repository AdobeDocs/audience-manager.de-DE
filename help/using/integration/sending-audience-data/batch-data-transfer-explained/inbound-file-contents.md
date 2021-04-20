---
description: Erforderliche Felder, Syntax und Regeln, die Sie beim Formatieren einer eingehenden Eigenschaftendatendatei beachten sollten.
seo-description: Erforderliche Felder, Syntax und Regeln, die Sie beim Formatieren einer eingehenden Eigenschaftendatendatei beachten sollten.
seo-title: Syntax der Inbound-Datendateiinhalte, ungültige Zeichen, Variablen und Beispiele
solution: Audience Manager
title: Syntax der Inbound-Datendateiinhalte, ungültige Zeichen, Variablen und Beispiele
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '1196'
ht-degree: 4%

---

# Inhalt der eingehenden Datendatei: Syntax, ungültige Zeichen, Variablen und Beispiele {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Erforderliche Felder, Syntax und Regeln, die Sie beim Formatieren einer eingehenden Eigenschaftendatendatei beachten sollten.

## Syntax des Dateiinhalts {#file-content-syntax}

Die Felder in der eingehenden Datendatei müssen in der unten stehenden Reihenfolge angezeigt werden. In diesem Beispiel wurden die `<` `>`-Symbole hinzugefügt, um jedes Element visuell zu trennen. Sie müssen diese nicht in Ihre Datendatei aufnehmen.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Weitere akzeptierte Dateiinhaltsformate finden Sie unter [Benutzerdefinierte Partnerintegrationen](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Wir haben eine Grenze von 200 Zeilen, die wir für jede Benutzer-ID verarbeiten können, die in der eingehenden Datendatei gesendet wird. Wenn Sie beispielsweise 300 Zeilen für eine Benutzer-ID senden, werden die ersten 200 Zeilen beibehalten und die zusätzlichen 100 Zeilen verworfen. Im folgenden Beispiel sind Sie gut, weil Sie jeweils 3 Zeilen für Benutzer-ID 1 und Benutzer-ID 2 senden. Wir erzwingen keine Begrenzung der Anzahl der Eigenschaften oder Schlüssel-Wert-Paare, die Sie in eine Zeile einbeziehen.
>
>
```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Dateivariablen definiert {#file-variables-defined}

Die Tabelle Liste und definiert die Variablen, die in einer ordnungsgemäß formatierten eingehenden Datendatei verwendet werden. Eine *kursive* Formatierung gibt einen Variablenplatzhalter an.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Eine Benutzer-ID kann: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Eine eindeutige Benutzer-ID, die von <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager-UUID </a>) zugewiesen wird. </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Eine in Ihrem CRM-System zugewiesene eindeutige Benutzer-ID ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Eine mobile Android- oder iOS-Geräte-ID in ihrem ursprünglichen, unveränderten Formular, wie vom mobilen Betriebssystem verfügbar. </li> 
     </ul> </p> <p>Für mobile IDs: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA-Format: IDs müssen in Großbuchstaben und nicht mit Hashing versehen sein. Beispiel, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android-Format: IDs müssen in Kleinbuchstaben vorliegen und dürfen nicht mit Hashing versehen werden. Beispiel, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Trennen Sie die Benutzer-ID und die Eigenschaften-IDs durch ein Tabulatortrennzeichen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Die Eigenschaften-ID des <span class="keyword">-Audience Managers </span>. Wir bitten Sie, <i>nur Eigenschaften mit integriertem Inhalt</i> in Datendateien mit eingehenden Daten einzuschließen. Bei der eingehenden Datenübertragung werden keine anderen Eigenschaftsarten verarbeitet. </p> <p> <p>Hinweis:  Die Eigenschaften-ID kann mithilfe der GET gefunden werden, die Details zu all Ihren Eigenschaften zurückgibt. Weitere Informationen finden Sie unter <a href="../../../api/rest-api-main/api-traits.md"> Eigenschaften-API-Methoden </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatieren von [!UICONTROL Trait IDs] {#formatting-trait-ids}

In der folgenden Tabelle werden die Präfixe beschrieben, die [!UICONTROL trait]-Namen oder IDs in einer eingehenden Datendatei identifizieren. Beispiele finden Sie unter [Beispieldateien](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples).

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Präfix </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>Das Präfix <code> d_sid </code> weist unser System darauf hin, dass die ID eine Eigenschaft-ID des Audience Managers <span class="keyword"> ist. </span> Dies ist die gleiche ID, die auf der Benutzeroberfläche angezeigt wird. Sie können Eigenschaften-IDs auch mit der API-Methode <code> GET </code> zurückgeben. Siehe <a href="../../../api/rest-api-main/api-traits.md"> Eigenschaften-API-Methoden </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Daten mit dem Präfix <code> d_unsid </code> entfernen Benutzer aus dieser Eigenschaft. Das Präfix <code> d_unsid </code> wird in einer <code> overwrite </code>-Datei ignoriert. </p> <p>Das Präfix <code> d_unsid= </code> weist unser System darauf hin, dass die ID eine Eigenschaft-ID des Audience Managers <span class="keyword"> ist. </span> Dies ist die gleiche ID, die auf der Benutzeroberfläche angezeigt wird. Sie können Eigenschaften-IDs auch mit der API-Methode <code> GET </code> zurückgeben. Siehe <a href="../../../api/rest-api-main/api-traits.md"> Eigenschaften-API-Methoden </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Mit Eigenschaftsregeln  </a> können Sie Kriterien für die Eigenschaftsqualifikation festlegen. Wenn Sie eine Eigenschaftsregel als <code> ic == trait ID </code> formatieren, können Sie Eigenschaften in einer einfachen kommageformatierten Liste senden. </p> <p>Beispiel: Sie erstellen die folgenden 3 Eigenschaftenregeln: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Diese Eigenschaften sind mit der <code> ic </code>-Taste verknüpft. Auf diese Weise können Sie eine einfachere Liste der Eigenschaften in der Datendatei erstellen. Außerdem müssen Sie das Präfix <code> ic </code> nicht einschließen. Der Inhalt Ihrer Datendatei könnte daher wie folgt aussehen: </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schlüsselwertpaare </p> </td> 
   <td colname="col2"> <p>Eigenschaftsdaten können mithilfe alphanumerischer Zeichenfolgen als Schlüssel-Wert-Paare formatiert werden. Es gibt verschiedene Möglichkeiten, Schlüssel-Wert-Paare zu formatieren, wie nachfolgend gezeigt: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> ,  <code> "gender"=m </code>  <code> model = "pickup truck" </code>   <code> product = tablet </code> sind alle Beispiele für korrekt formatierte Schlüssel-Wert-Paare. </p> </td> 
  </tr>
 </tbody>
</table>

## Ungültige Zeichen in [!UICONTROL Trait IDs], [!UICONTROL User IDs] und Schlüsselwertpaaren {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] bestehen nur aus numerischen Zeichen. Wir bitten Sie, *nur[!UICONTROL onboarded traits]* in eingehende Datendateien einzuschließen. Wir verarbeiten keine anderen [!UICONTROL trait] Typen in der eingehenden Datenübertragung.

### [!UICONTROL User IDs]

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
   <td colname="col2"> <p><i>Verwenden Sie </i> keinen kodierten Doppelpunkt (  <code> %3A </code>) oder nicht kodierten Doppelpunkt ( : ) in DPUUIDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>iOS (IDFA) oder Android-Geräte-ID </p> </td> 
   <td colname="col2"> <p>Mobilgeräte-IDs müssen wie folgt streng formatiert sein: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA-Format: IDs müssen in Großbuchstaben und nicht mit Hashing versehen sein. Beispiel, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android-Format: IDs müssen in Kleinbuchstaben vorliegen und dürfen nicht mit Hashing versehen werden. Beispiel, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Schlüsselwertpaare

Auch falsch formatierte Wertnamen in einem Schlüssel-Wert-Paar verursachen Probleme. Beachten Sie beim Erstellen oder Benennen des Werts in einem Schlüssel-Wert-Paar die folgenden Regeln:

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
   <td colname="col2"> <p>Sie können das Anführungszeichen im Schlüssel und im Werteteil des Schlüsselwertpaars wie folgt verwenden: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bindestrich (-) </p> </td> 
   <td colname="col2"> <p>Wir ignorieren Bindestriche am Beginn der Schlüssel. Zum Beispiel wird <code> -product = camera </code> als <code> product = camera </code> interpretiert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Verwenden Sie in Schlüssel-Wert-Paaren </i> nicht  <code> TAB </code> anstelle leerer Werte. Verwenden Sie <code> TAB </code> nur, um Variablen in der eingehenden Datendatei zu trennen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>Verwenden Sie nicht die neuen Zeilen- oder Tabulatorzeichen ( <code> \n, \t </code>) in Schlüsseln oder in Werten. </p> </td> 
  </tr>
 </tbody>
</table>

## Beispiele für Datendateien {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datendateiformat </th> 
   <th colname="col2" class="entry"> Beschreibung und Beispiel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Mit <code> d_sid </code> oder <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Diese Datendatei zeigt einen Benutzer, der für die Eigenschaften 24, 26, 27 qualifiziert ist, und wurde aus den Eigenschaften 28 und 29 entfernt. </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Hinweis:  <p>Statt d_unsid zu verwenden, können Sie auch Eigenschaften aus Profilen entfernen, indem Sie die folgende Syntax verwenden: </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mit <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Diese Eigenschaften wurden einer Eigenschaftsregel mit dem Präfix <code> ic </code> hinzugefügt. Daher können Sie sie der Datendatei durch Kommas wie gezeigt hinzufügen. Eine Registerkarte trennt die UUID und die Eigenschaften-IDs. Das Präfix <code> ic </code> ist in der Datei nicht erforderlich. </p> <p><b>Numerische IDs</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>String-IDs</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mit Schlüssel-Wert-Paaren </p> </td> 
   <td colname="col2"> Diese Dateidaten verwenden Schlüssel-Wert-Paare, um Daten an <span class="keyword"> Audience Manager </span> weiterzugeben. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Wenn Sie weitere Beispiele benötigen, ](assets/ftp_dpm_1234_1445374061.overwrite) laden Sie die Musterdatendatei herunter. Die Download-Datei hat die Dateierweiterung `.overwrite`. Sie können es mit einem einfachen Texteditor öffnen.

## Beispielmatrix {#examples-matrix}

Das folgende Diagramm zeigt Beispiele für die richtige Formatierung Ihrer Inbound-Dateien, je nach dem [Typ der IDs](../../../reference/ids-in-aam.md) und der Methode, mit der Sie [!UICONTROL traits] zu Profilen hinzufügen möchten.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID-Typ/Vorgang </th> 
   <th colname="col2" class="entry"> Verwenden Sie d_sid, um Eigenschaften zu einem Profil hinzuzufügen </th> 
   <th colname="col3" class="entry"> Mit d_unsid können Sie Eigenschaften aus einem Profil entfernen </th> 
   <th colname="col4" class="entry"> Senden Sie Schlüssel-Wert-Paare, um Eigenschaften zu einem Profil hinzuzufügen </th> 
   <th colname="col5" class="entry"> Verwenden Sie das Präfix "ic", um Eigenschaften zu einem Profil hinzuzufügen </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager-UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Beispiel 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Beispiel 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Beispiel 3  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Beispiel 4  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Advertising ID für Android-Geräte </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Beispiel 5  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Beispiel 6  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Beispiel 7  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Beispiel 8  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA für iOS-Geräte </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Beispiel 9  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Beispiel 10  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Beispiel 11  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Beispiel 12  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ihre eigene CRM-ID (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Beispiel 13  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Beispiel 14  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Beispiel 15  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Beispiel 16  </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiel 1 {#example-1}

Verwenden Sie [!UICONTROL trait IDs], um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL Audience Manager] [!DNL UUIDs] zu senden.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Beispiel 2 {#example-2}

Verwenden Sie [!UICONTROL trait IDs], um [!UICONTROL trait]-Disqualifizierungsinformationen für [!DNL Audience Manager] [!DNL UUIDs] zu senden.

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

Senden Sie Schlüssel-Wert-Paare, um [!UICONTROL trait] Qualifizierungsinformationen für [!DNL Audience Manager] [!DNL UUIDs] hinzuzufügen.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

oder

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Beispiel 5 {#example-4}

Verwenden Sie das Präfix `ic`, um [!UICONTROL trait] Qualifizierungsinformationen für [!DNL Audience Manager] [!DNL UUIDs] zu senden.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

oder

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Beispiel 4 {#example-5}

Verwenden Sie [!UICONTROL trait IDs], um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL Android]-Geräte zu senden.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Beispiel 6 {#example-6}

Verwenden Sie [!UICONTROL trait IDs], um [!UICONTROL trait]-Disqualifizierungsinformationen für [!DNL Android]-Geräte zu senden.

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

Senden Sie Schlüssel-Wert-Paare, um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL Android]-Geräte hinzuzufügen.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

oder

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Beispiel 8 {#example-8}

Verwenden Sie das Präfix `ic`, um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL Android]-Geräte zu senden.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

oder

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Beispiel 9 {#example-9}

Verwenden Sie [!UICONTROL trait IDs], um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL iOS]-Geräte zu senden.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Beispiel 10 {#example-10}

Verwenden Sie [!UICONTROL trait IDs], um [!UICONTROL trait]-Disqualifizierungsinformationen für [!DNL iOS]-Geräte zu senden.

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

Senden Sie Schlüssel-Wert-Paare, um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL iOS]-Geräte hinzuzufügen.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

oder

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Beispiel 12 {#example-12}

Verwenden Sie das Präfix `ic`, um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL iOS]-Geräte zu senden.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

oder

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Beispiel 13 {#example-13}

Verwenden Sie [!UICONTROL trait IDs], um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL DPUUIDs] zu senden.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Beispiel 14 {#example-14}

Verwenden Sie [!UICONTROL trait IDs], um [!UICONTROL trait]-Disqualifizierungsinformationen für [!DNL DPUUIDs] zu senden.

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

Senden Sie Schlüssel-Wert-Paare, um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL DPUUIDs] hinzuzufügen.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

oder

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Beispiel 16 {#example-16}

Verwenden Sie das Präfix `ic`, um [!UICONTROL trait]-Qualifizierungsinformationen für [!DNL DPUUIDs] zu senden.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

oder

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Trait Builder ](../../../features/traits/about-trait-builder.md)


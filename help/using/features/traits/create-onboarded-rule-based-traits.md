---
description: Beschreibt die Einrichtung von Schritten und Funktionen, die spezifisch für den regelbasierten und den integrierten Prozess zur Erstellung von Eigenschaften gelten.
keywords: Eigenschaften erstellen;Eigenschaften erstellen
seo-description: Beschreibt die Einrichtung von Schritten und Funktionen, die spezifisch für den regelbasierten und den integrierten Prozess zur Erstellung von Eigenschaften gelten.
seo-title: Erstellen regelbasierter oder integrierter Eigenschaften
solution: Audience Manager
title: Erstellen regelbasierter oder integrierter Eigenschaften
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 8%

---


# Erstellen[!UICONTROL Rules-Based] oder [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Beschreibt die Einrichtung von Schritten und Funktionen, die spezifisch für die Erstellung der Eigenschaften [!UICONTROL rules-based] und [!UICONTROL onboarded] sind.

<!-- c_tb_rules_traits.xml -->

## Grundlegende Informationen für Eigenschaften {#basics}

Mit den [!UICONTROL Trait Builder]-Einstellungen können Sie neue [!UICONTROL Basic Information] erstellen oder vorhandene [!UICONTROL traits] bearbeiten. Die [!UICONTROL Basic Information]-Einstellungen sind für [!UICONTROL rules-based], [!UICONTROL onboarded] und [!UICONTROL algorithmic traits] gleich. Um ein neues [!UICONTROL trait] zu erstellen, geben Sie einen Namen (ohne Sonderzeichen), ein [!UICONTROL data source] ein und wählen Sie ein [!UICONTROL storage folder]. Andere [!UICONTROL Basic Information]-Felder sind optional.

<!-- c_tb_basics.xml -->

![create-property](assets/create-trait.png)

### Grundlegende Informationsfelder definiert

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Oberflächenelement </th> 
   <th colname="col2" class="entry"> Erklärung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Name</span></b> </td> 
   <td colname="col2"> <p>Der Eigenschaftsname. Erforderlich. </p> <p>Höchstlänge: 255 Zeichen. </p> <p> <p>Hinweis: Vermeiden Sie beim Benennen von Eigenschaften die folgenden Sonderzeichen: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Striche </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Hyphen </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Registerkarten </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Vertikales Strich- oder Senkrechteck </li> 
      </ul> </p> </p> <p>Auf diese Weise können Verarbeitungsfehler beim Einrichten einer <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> eingehenden Datendateiübertragung</a> reduziert werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Beschreibung</span></b> </td> 
   <td colname="col2"> Ein paar Worte, die helfen, den Zweck oder die Funktion der Eigenschaft zu beschreiben. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datenquelle</span></b> </td> 
   <td colname="col2"> Ordnet die Eigenschaft einem bestimmten Datenanbieter zu. Erforderlich. <p>Verwenden Sie das erste Dropdownmenü, um zwischen Audience Manager-Datenquellen, Adobe Analytics-Report Suites oder beiden zu filtern. Wählen Sie dann im zweiten Dropdownmenü die Datenquelle aus.</p><p> Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die Datenquellenauswahl deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen eingestellt.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ereignistyp</span></b> </td> 
   <td colname="col2"> Weist die Eigenschaft einem Typ oder einer Kategorie zu, in der Regel entsprechend der Funktion (z. B. Konversion, Site-Besucher, Partner, Ansicht der Seite usw.). Optional. <p> Informationen zum Erstellen von Konversionseigenschaften finden Sie im Audience Manager <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Erstellen von Konversionseigenschaften</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Integrations-Code</span></b> </td> 
   <td colname="col2"> Ein Feld für eine ID, SKU oder einen anderen Wert, der von Ihren internen Geschäftsprozessen verwendet wird. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kommentare</span></b> </td> 
   <td colname="col2"> Allgemeine Hinweise zu einer Eigenschaft. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Store in</span></b> </td> 
   <td colname="col2"> Legt fest, zu welcher Datenspeicherung der Eigenschaftsordner gehört. Erforderlich. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kategorie der Daten</span></b> </td> 
   <td colname="col2"> Klassifiziert Eigenschaften nach allgemein verständlichen Kategorien. <p>Hinweis:  Eigenschaften gehören nur zu einer Kategorie. Optional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Festlegen eines [!UICONTROL Trait] Ablaufintervalls {#set-expiration-interval}

In [!UICONTROL Trait Builder] können Sie mit dem [!UICONTROL Advanced Options]-Intervall ein Live-Intervall ([!DNL TTL]) für ein [!UICONTROL trait] festlegen. [!DNL TTL] legt fest, wie viele Tage ein qualifizierter Besucher in einem Zeitraum von  [!UICONTROL trait] (standardmäßig 120 Tagen) verbleibt. Bei Festlegung auf 0 läuft die [!UICONTROL trait]-Mitgliedschaft nie ab.

<!-- t_tb_ttl.xml -->

### TTL für ein [!UICONTROL trait] festlegen

1. Erweitern Sie den Abschnitt [!UICONTROL Advanced Options] und geben Sie eine Zahl ein, um einen [!DNL TTL]-Wert für [!UICONTROL trait] festzulegen.
1. Klicken **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Erläuterung der Segmentzeit bis zur Live-Übertragung](../../features/traits/segment-ttl-explained.md)


---
description: Beschreibt die Einrichtung von Schritten und Funktionen, die spezifisch für den regelbasierten und integrierten Erstellungsprozess von Eigenschaften sind.
keywords: Eigenschaften erstellen; Eigenschaften erstellen
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Erstellen regelbasierter oder integrierter Eigenschaften
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 2%

---

# Erstellen Sie [!UICONTROL Rules-Based] oder [!UICONTROL Onboarded Traits] {#create-rules-based-or-onboarded-traits}

Beschreibt Schritte und Funktionen, die für die Erstellung von [!UICONTROL rules-based] und [!UICONTROL onboarded] Eigenschaften spezifisch sind.

<!-- c_tb_rules_traits.xml -->

## Grundlegende Informationen für Eigenschaften {#basics}

In [!UICONTROL Trait Builder] können Sie mit den [!UICONTROL Basic Information] -Einstellungen neue erstellen oder vorhandene [!UICONTROL traits] bearbeiten. Die [!UICONTROL Basic Information]-Einstellungen sind für [!UICONTROL rules-based], [!UICONTROL onboarded] und [!UICONTROL algorithmic traits] identisch. Um einen neuen [!UICONTROL trait] zu erstellen, geben Sie einen Namen (Sonderzeichen vermeiden), einen [!UICONTROL data source] und wählen Sie einen [!UICONTROL storage folder] aus. Andere [!UICONTROL Basic Information] -Felder sind optional.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Definierte grundlegende Informationsfelder

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schnittstellenelement </th> 
   <th colname="col2" class="entry"> Erklärung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Name</span></b> </td> 
   <td colname="col2"> <p>Der Eigenschaftsname. Erforderlich. </p> <p>Maximale Länge: 255 Zeichen. </p> <p> <p>Hinweis: Vermeiden Sie beim Benennen von Eigenschaften die folgenden Sonderzeichen: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Dashes </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Bindestriche </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Registerkarten </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Vertikaler Balken oder Senkrechtstrich </li> 
      </ul> </p> </p> <p>Dies hilft, Verarbeitungsfehler beim Einrichten einer <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> eingehenden Datendateiübertragung</a> zu reduzieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">Beschreibung</span></b> </td> 
   <td colname="col2"> Ein paar Worte, die helfen, den Zweck oder die Funktion der Eigenschaft zu beschreiben. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Data Source</span></b> </td> 
   <td colname="col2"> Verbindet die Eigenschaft mit einem bestimmten Datenanbieter. Erforderlich. <p>Verwenden Sie das erste Dropdown-Menü, um zwischen Audience Manager-Datenquellen, Adobe Analytics-Report Suites oder beidem zu filtern. Wählen Sie dann im zweiten Dropdown-Menü Ihre Datenquelle aus.</p><p> Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die Datenquellenauswahl deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen festgelegt.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ereignistyp</span></b> </td> 
   <td colname="col2"> Weist die Eigenschaft einem Typ oder einer Kategorie zu, in der Regel entsprechend der Funktion (z. B. Konversion, Site-Besucher, Partner, Seitenansicht usw.). Optional. <p> Informationen zum Erstellen von Konversionseigenschaften finden Sie im Video <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">Erstellen von Konversionseigenschaften in Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Integrationscode</span></b> </td> 
   <td colname="col2"> Ein Feld für eine ID, SKU oder einen anderen Wert, der von Ihren internen Geschäftsprozessen verwendet wird. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kommentare</span></b> </td> 
   <td colname="col2"> Allgemeine Hinweise zu einer Eigenschaft. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Store in</span></b> </td> 
   <td colname="col2"> Bestimmt, zu welchem Speicherordner die Eigenschaft gehört. Erforderlich. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datenkategorie</span></b> </td> 
   <td colname="col2"> Klassifiziert Eigenschaften nach allgemein verständlichen Kategorien. <p>Hinweis: Eigenschaften gehören nur zu einer Kategorie. Optional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Festlegen eines Ablaufintervalls für [!UICONTROL Trait] {#set-expiration-interval}

In [!UICONTROL Trait Builder] können Sie mit dem [!UICONTROL Advanced Options] ein Time-to-Live-Intervall ([!DNL TTL]) für einen [!UICONTROL trait] festlegen. [!DNL TTL] definiert, wie viele Tage ein qualifizierter Besucher in einer [!UICONTROL trait] verbleibt (standardmäßig 120 Tage). Wenn der Wert auf 0 gesetzt ist, läuft die Mitgliedschaft von [!UICONTROL trait] nie ab.

<!-- t_tb_ttl.xml -->

### TTL für [!UICONTROL trait] festlegen

1. Erweitern Sie den Abschnitt [!UICONTROL Advanced Options] und geben Sie eine Zahl ein, um einen [!DNL TTL] -Wert für die [!UICONTROL trait] festzulegen.
1. Klicken Sie auf **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Segmentzeit bis zum Live - Erklärung](../../features/traits/segment-ttl-explained.md)

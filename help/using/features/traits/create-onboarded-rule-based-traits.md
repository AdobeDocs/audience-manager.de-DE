---
description: Beschreibt die Einrichtungsschritte und -funktionen, die für den regelbasierten und integrierten Prozess zur Erstellung von Eigenschaften spezifisch sind.
keywords: Eigenschaft erstellen;Eigenschaften erstellen
seo-description: Describes set up steps and features specific to the rules-based and onboarded trait creation process.
seo-title: Create Rules-Based or Onboarded Traits
solution: Audience Manager
title: Erstellen von regelbasierten oder integrierten Eigenschaften
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
feature: Traits
exl-id: cad318ee-93b2-4afa-8a2f-a67b068eec0a
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 2%

---

# [!UICONTROL Rules-Based] oder [!UICONTROL Onboarded Traits] erstellen {#create-rules-based-or-onboarded-traits}

Beschreibt die Einrichtungsschritte und -funktionen, die für den Prozess der Erstellung von [!UICONTROL rules-based] und [!UICONTROL onboarded]-Eigenschaften spezifisch sind.

<!-- c_tb_rules_traits.xml -->

## Grundlegende Informationen zu Eigenschaften {#basics}

In [!UICONTROL Trait Builder] können Sie mit den [!UICONTROL Basic Information] Einstellungen neue [!UICONTROL traits] erstellen oder vorhandene bearbeiten. Die [!UICONTROL Basic Information] Einstellungen für [!UICONTROL rules-based], [!UICONTROL onboarded] und [!UICONTROL algorithmic traits] sind identisch. Um ein neues [!UICONTROL trait] zu erstellen, geben Sie einen Namen (vermeiden Sie Sonderzeichen) und ein [!UICONTROL data source] an und wählen Sie ein [!UICONTROL storage folder] aus. Andere [!UICONTROL Basic Information] sind optional.

<!-- c_tb_basics.xml -->

![create-trait](assets/create-trait.png)

### Felder für grundlegende Informationen definiert

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
   <td colname="col2"> <p>Der Eigenschaftsname. Erforderlich. </p> <p>Maximale Länge: 255 Zeichen. </p> <p> <p>Hinweis: Vermeiden Sie beim Benennen von Eigenschaften diese Sonderzeichen: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Bindestriche </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Bindestriche </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Registerkarten </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Vertikales Balken- oder Rohrsymbol </li> 
      </ul> </p> </p> <p>Auf diese Weise werden Verarbeitungsfehler beim Einrichten einer <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> eingehenden Datendateiübertragung </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">Beschreibung</span></b> </td> 
   <td colname="col2"> Ein paar Worte, um den Zweck oder die Funktion des Merkmals zu beschreiben. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Data Source</span></b> </td> 
   <td colname="col2"> Ordnet das Merkmal einem bestimmten Datenanbieter zu. Erforderlich. <p>Verwenden Sie das erste Dropdown-Menü, um zwischen Audience Manager-Datenquellen, Adobe Analytics Report Suites oder beidem zu filtern. Wählen Sie dann im zweiten Dropdown-Menü Ihre Datenquelle aus.</p><p> Wenn Sie keine Adobe Analytics Report Suites verwenden, ist die Datenquellentyp-Auswahl deaktiviert und standardmäßig nur auf Audience Manager-Datenquellen festgelegt.</p>  </td> 
  </tr>
   <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ereignistyp</span></b> </td> 
   <td colname="col2"> Weist das Merkmal einem Typ oder einer Kategorie zu, normalerweise entsprechend der Funktion (z. B. Konversion, Site-Besucher, Partner, Seitenansicht usw.). Optional. <p> Informationen zum Erstellen von Konversionseigenschaften finden Sie im Video <a href="https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html?lang=de">Erstellen von Konversionseigenschaften in Audience Manager</a>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Integrations-Code</span></b> </td> 
   <td colname="col2"> Ein Feld für eine ID, eine SKU oder einen anderen Wert, der von Ihren internen Geschäftsprozessen verwendet wird. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kommentare</span></b> </td> 
   <td colname="col2"> Allgemeine Hinweise zu einer Eigenschaft. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Store in</span></b> </td> 
   <td colname="col2"> Legt fest, zu welchem Speicherordner die Eigenschaft gehört. Erforderlich. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datenkategorie</span></b> </td> 
   <td colname="col2"> Klassifiziert Eigenschaften nach allgemein verständlichen Kategorien. <p>Hinweis: Eigenschaften gehören nur zu einer einzigen Kategorie. Optional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Festlegen eines [!UICONTROL Trait] Ablaufintervalls {#set-expiration-interval}

[!UICONTROL Trait Builder] können Sie mit dem [!UICONTROL Advanced Options] ein Time-to-Live ([!DNL TTL])-Intervall für eine [!UICONTROL trait] festlegen. [!DNL TTL] definiert, wie viele Tage ein qualifizierter Besucher in einem [!UICONTROL trait] verbleibt (standardmäßig 120 Tage). Bei einer Einstellung von 0 läuft [!UICONTROL trait] Mitgliedschaft nie ab.

<!-- t_tb_ttl.xml -->

### Festlegen der TTL für eine [!UICONTROL trait]

1. Erweitern Sie den Abschnitt [!UICONTROL Advanced Options] und geben Sie eine Zahl ein, um einen [!DNL TTL] für die [!UICONTROL trait] festzulegen.
1. Klicken Sie auf **[!UICONTROL Save]**.

   ![](assets/TTL.png)

>[!MORELIKETHIS]
>
>* [Erklärung: Segment Time to Live](../../features/traits/segment-ttl-explained.md)

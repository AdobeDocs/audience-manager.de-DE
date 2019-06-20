---
description: Beschreibt die Schritte und Funktionen, die spezifisch für regelbasierte und onboarded Trait-Erstellung gelten.
keywords: Eigenschaft erstellen; Eigenschaften erstellen
seo-description: Beschreibt die Schritte und Funktionen, die spezifisch für regelbasierte und onboarded Trait-Erstellung gelten.
seo-title: Regelbasierte oder Onboardanmerkungen erstellen
solution: Audience Manager
title: Regelbasierte oder Onboardanmerkungen erstellen
uuid: 4243 e 09 f -1 f 96-443 a -864 a-d 6 e 6918079 fa
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Regelbasierte oder Onboardanmerkungen erstellen {#create-rules-based-or-onboarded-traits}

Beschreibt die Schritte und Funktionen, die speziell für die [!UICONTROL rules-based] Erstellung und [!UICONTROL onboarded] Erstellung von Eigenschaften gelten.

<!-- c_tb_rules_traits.xml -->

## Grundlegende Informationen zu Eigenschaften {#basics}

In können [!UICONTROL Trait Builder]Sie in den [!UICONTROL Basic Information] Einstellungen neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. Die [!UICONTROL Basic Information] Einstellungen gelten für regelbasierte, detaillierte und algorithmische Eigenschaften. Um eine neue Eigenschaft zu erstellen, geben Sie einen Namen (Sonderzeichen vermeiden), eine Datenquelle und einen Speicherordner ein. Andere [!UICONTROL Basic Information] Felder sind optional.

<!-- c_tb_basics.xml -->

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
   <td colname="col1"> <b><span class="uicontrol">Name</span></b> </td> 
   <td colname="col2"> <p>Der Eigenschaftsname. Erforderlich. </p> <p>Maximale Länge: 255 Zeichen. </p> <p> <p>Hinweis: Vermeiden Sie die folgenden Sonderzeichen, wenn Sie Eigenschaften benennen: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Bindestriche </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Bindestriche </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Registerkarten </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Vertikalbalken- oder Senkrechtstrich </li> 
      </ul> </p> </p> <p>Dadurch können Verarbeitungsfehler reduziert werden, wenn Sie eine <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> eingehende Datendateiübertragung einrichten</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Beschreibung</span></b> </td> 
   <td colname="col2"> Einige Wörter, die den Zweck oder die Funktion des Merkmals beschreiben. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ereignistyp</span></b> </td> 
   <td colname="col2"> Weist einem Typ oder einer Kategorie die Eigenschaft zu, normalerweise entsprechend der Funktion (z. B. Umrechnung, Site-Besucher, Partner, Seitenansicht usw.). Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datenquelle</span></b> </td> 
   <td colname="col2"> Verbindet die Eigenschaft mit einem bestimmten Datenanbieter. Erforderlich. </td> 
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
   <td colname="col1"> <b><span class="uicontrol"> Gespeichert in</span></b> </td> 
   <td colname="col2"> Legt fest, zu welchem Speicherordner die Eigenschaft gehört. Erforderlich. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datenkategorie</span></b> </td> 
   <td colname="col2"> Klassifiziert Eigenschaften nach häufig verständlichen Kategorien. <p>Hinweis: Eigenschaften gehören nur zu einer Kategorie. Optional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Festlegen eines Eigenschaftsablaufintervalls {#set-expiration-interval}

In [!UICONTROL Trait Builder]können [!UICONTROL Advanced Options] Sie ein Zeitintervall ([!DNL TTL]) für eine Eigenschaft festlegen. [!DNL TTL] definiert, wie viele Tage ein qualifizierter Besucher in einer Eigenschaft verbleibt (120 Tage ist Standard). Bei Festlegung auf 0 läuft die Trait-Mitgliedschaft nie ab.

<!-- t_tb_ttl.xml -->

### TTL für eine Eigenschaft festlegen

1. Erweitern Sie den [!UICONTROL Advanced Options] Abschnitt und geben Sie eine Zahl ein, um einen [!DNL TTL] Wert für die Eigenschaft festzulegen.
1. Klicken Sie auf **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_ LIKE_ THIS]
>
>* [Segmentzeit zu Live erklärt](../../features/traits/segment-ttl-explained.md)


---
description: Beschreibt die Einrichtung von Schritten und Funktionen, die spezifisch für den regelbasierten und den integrierten Prozess zur Erstellung von Eigenschaften sind.
keywords: Eigenschaften erstellen;Eigenschaften erstellen
seo-description: Beschreibt die Einrichtung von Schritten und Funktionen, die spezifisch für den regelbasierten und den integrierten Prozess zur Erstellung von Eigenschaften sind.
seo-title: Erstellen regelbasierter oder Onboarded-Eigenschaften
solution: Audience Manager
title: Erstellen regelbasierter oder Onboarded-Eigenschaften
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Erstellen regelbasierter oder Onboarded-Eigenschaften {#create-rules-based-or-onboarded-traits}

Beschreibt die Einrichtung von Schritten und Funktionen, die für den Erstellungsprozess [!UICONTROL rules-based] und die Erstellung von [!UICONTROL onboarded] Eigenschaften spezifisch sind.

<!-- c_tb_rules_traits.xml -->

## Grundlegende Informationen zu Eigenschaften {#basics}

In [!UICONTROL Trait Builder]den [!UICONTROL Basic Information] Einstellungen können Sie neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. Die [!UICONTROL Basic Information] Einstellungen sind für regelbasierte, integrierte und algorithmische Eigenschaften identisch. Um eine neue Eigenschaft zu erstellen, geben Sie einen Namen (ohne Sonderzeichen), eine Datenquelle und einen Speicherordner an. Andere [!UICONTROL Basic Information] Felder sind optional.

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
   <td colname="col2"> <p>Der Eigenschaftsname. Erforderlich. </p> <p>Höchstlänge: 255 Zeichen. </p> <p> <p>Hinweis: Vermeiden Sie beim Benennen von Eigenschaften die folgenden Sonderzeichen: 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">Kommas </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">Striche </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">Hyphen </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">Registerkarten </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">Vertikales Strich- oder Senkrechteck </li> 
      </ul> </p> </p> <p>Auf diese Weise können Sie Verarbeitungsfehler beim Einrichten einer <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> eingehenden Datendateitransaktion</a>reduzieren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Beschreibung</span></b> </td> 
   <td colname="col2"> Ein paar Worte, die helfen, den Zweck oder die Funktion der Eigenschaft zu beschreiben. Optional. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Ereignistyp</span></b> </td> 
   <td colname="col2"> Weist die Eigenschaft einem Typ oder einer Kategorie zu, in der Regel entsprechend der Funktion (z. B. Konversion, Site-Besucher, Partner, Seitenansicht usw.). Optional. <p> Informationen zum Erstellen von Konversionseigenschaften finden Sie im Video<a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">zum </a>Erstellen von Konversionseigenschaften in Audience Manager. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Datenquelle</span></b> </td> 
   <td colname="col2"> Ordnet die Eigenschaft einem bestimmten Datenanbieter zu. Erforderlich. </td> 
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
   <td colname="col2"> Klassifiziert Eigenschaften nach allgemein verständlichen Kategorien. <p>Hinweis:  Eigenschaften gehören nur zu einer Kategorie. Optional. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ablaufintervall für Eigenschaften festlegen {#set-expiration-interval}

In [!UICONTROL Trait Builder]der [!UICONTROL Advanced Options] können Sie ein Intervall für die Live-Wiedergabe ([!DNL TTL]) für eine Eigenschaft festlegen. [!DNL TTL] definiert, wie viele Tage ein qualifizierter Besucher in einer Eigenschaft bleibt (standardmäßig 120 Tage). Bei Festlegung auf 0 läuft die Mitgliedschaft bei Eigenschaften nie ab.

<!-- t_tb_ttl.xml -->

### TTL für eine Eigenschaft festlegen

1. Erweitern Sie den [!UICONTROL Advanced Options] Abschnitt und geben Sie eine Zahl ein, um einen [!DNL TTL] Wert für die Eigenschaft festzulegen.
2. Klicken Sie auf **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_LIKE_THIS]
>
>* [Erläuterung der Segmentzeit bis zur Live-Übertragung](../../features/traits/segment-ttl-explained.md)


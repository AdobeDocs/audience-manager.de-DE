---
description: Spaltenüberschriften definiert.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Tools für die Massenverwaltung - Glossar
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# Tools für die Massenverwaltung - Glossar{#bulk-management-tools-glossary}

Spaltenüberschriften definiert.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support durch die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[In der Benutzeroberfläche von [!DNL Audience Manager] zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Spaltenüberschrift </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>Die ID einer <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datenquelle</a>, die stapelweise zurückgegeben oder zugewiesen werden soll. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>Eine <a href="../../features/derived-signals.md"> abgeleitete Signal</a>-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>Eine kurze, informative Beschreibung, die Sie einem Objekt geben können. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>Die ID des <a href="../../features/destinations/destinations.md"> Ziels</a>, das Sie zuordnen oder löschen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>Eine spezielle ID, die einem Segment zugewiesen wird, wenn es einem Ziel zugeordnet wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>Die ID Ihres Segments- oder Eigenschaftsordners. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Der Name des Objekts, mit dem Sie arbeiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>Die ID eines Segments oder Eigenschaftsordners, das andere Ordner enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>Segment-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Signale sind Datenbits, die basierend auf der Benutzeraktivität an <span class="keyword"> Audience Manager</span> übergeben werden. Diese werden als <a href="../../reference/key-value-pairs-explained.md"> Schlüssel-Wert-Paare</a> übertragen. Der Quellschlüssel ist eine Konstante, die sich nicht ändert. Dies hilft, den Quellwert zu kategorisieren, der sich ändern kann. Siehe <a href="../../features/derived-signals.md"> Abgeleitete Signale</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>Der Quellwert ist eine Variable, die als Teil eines <a href="../../reference/key-value-pairs-explained.md"> Schlüssel-Wert-Paares</a> übergeben wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Gibt an, wann ein Segment an ein Ziel gesendet werden kann. Verwendet das Format <i>jjj-mm-tt</i> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">Der im abgeleiteten Signal verwendete Schlüssel. Siehe <a href="../../features/derived-signals.md"> Abgeleitete Signale</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>Der mit einem abgeleiteten Signalschlüssel übergebene Wert. Siehe <a href="../../features/derived-signals.md"> Abgeleitete Signale</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>Eine ID, die an ein nicht Cookie-basiertes Ziel übergeben wird. Bei einem Cookie-basierten Ziel ist dies der Schlüssel in einem <a href="../../reference/key-value-pairs-explained.md"> Schlüssel-Wert-Paar</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule/segmentRule</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Eigenschaft oder Segmentregel, die zur Datenerfassung verwendet wird. Eine Massenanforderung gibt die Regeln zurück, die im <span class="keyword"> Audience Manager</span> mit dem <a href="../../features/traits/about-trait-builder.md"> Trait Rule Builder</a> oder dem <a href="../../features/segments/segment-builder.md"> Segment Rule Builder</a> erstellt wurden. Sie können diese Tools auch verwenden, um Regeln zu erstellen und sie beim Aktualisieren eines Segments oder einer Eigenschaft stapelweise anzuwenden. </p> <p>Siehe auch <a href="../../reference/bulk-management-tools/bulk-rules.md"> Erstellen oder Aktualisieren von Eigenschaftsregeln und Segmentregeln</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>Eine Zeichenfolge, die den Eigenschaftstyp angibt. Zu den Optionen zählen: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel, das durch DIL ausgelöst wird, wenn ein Benutzer sich für ein Segment qualifiziert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>Der Schlüssel in einem <a href="../../reference/key-value-pairs-explained.md"> Schlüssel-Wert-Paar</a>, der an ein Cookie-Ziel übergeben wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

---
description: Spaltenkopfzeilenbeschriftungen definiert.
seo-description: Spaltenkopfzeilenbeschriftungen definiert.
seo-title: Bulk Management-Tools-Glossar
solution: Audience Manager
title: Bulk Management-Tools-Glossar
uuid: 4658 a 6 bc -9515-4 d 31-9715-0084760 b 0 cea
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Management-Tools-Glossar{#bulk-management-tools-glossary}

Spaltenkopfzeilenbeschriftungen definiert.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>Die Variable [!UICONTROL Bulk Management Tools]*wird nicht* unterstützt [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. Für Massenänderungen wird empfohlen, stattdessen mit den [Audience Manager-apis](../../api/rest-api-main/aam-api-getting-started.md) zu arbeiten. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Spaltenüberschrift </th> 
   <th colname="col2" class="entry"> Definition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Datasourceid</span> </p> </td> 
   <td colname="col2"> <p>Die ID einer <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datenquelle</a> , die Sie zurückgeben oder stapelweise zuweisen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Derivedsignalid</span> </p> </td> 
   <td colname="col2"> <p>Eine <a href="../../features/derived-signals.md"> abgeleitete Signal</a> -ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Beschreibung</span> </p> </td> 
   <td colname="col2"> <p>Eine kurze, informative Beschreibung, die Sie einem Objekt geben können. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Destinationid</span> </p> </td> 
   <td colname="col2"> <p>Die ID des <a href="../../features/destinations/destinations.md"> Ziels</a> , das Sie zuordnen oder löschen möchten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Destinationmappingid</span> </p> </td> 
   <td colname="col2"> <p>Eine spezielle ID, die einem Segment zugewiesen wird, wenn es einem Ziel zugeordnet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Folderid</span> </p> </td> 
   <td colname="col2"> <p>Die ID Ihres Segment- oder Eigenschaftenordners. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>Der Name des Objekts, mit dem Sie arbeiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Parentfolderid</span> </p> </td> 
   <td colname="col2"> <p>Die ID eines Segment- oder Eigenschaftenordners, der andere Ordner enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>Segment-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcekey</span> </p> </td> 
   <td colname="col2"> <p>Signale sind Datenbits, die basierend auf der Benutzeraktivität an <span class="keyword"> Audience Manager</span> weitergegeben werden. Diese werden als <a href="../../reference/key-value-pairs-explained.md"> Schlüssel-Wert-Paare übertragen</a>. Der Quellschlüssel ist eine Konstante, die sich nicht ändert. Sie hilft dabei, den Quellwert zu kategorisieren, der sich ändern kann. Siehe <a href="../../features/derived-signals.md"> Abgeleitete Signale</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcevalue</span> </p> </td> 
   <td colname="col2"> <p>Der Quellwert ist eine Variable, die als Teil- <a href="../../reference/key-value-pairs-explained.md"> Wert</a>-Paar weitergegeben wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Gibt an, wann ein Segment an ein Ziel gesendet werden kann. Verwendet <tt>das Format JJJJ-MM</tt> -TT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetkey</span> </p> </td> 
   <td colname="col2">Der im abgeleiteten Signal verwendete Schlüssel. Siehe <a href="../../features/derived-signals.md"> Abgeleitete Signale</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetvalue</span> </p> </td> 
   <td colname="col2"> <p>Der Wert, der mit einem abgeleiteten Signaturschlüssel weitergegeben wird. Siehe <a href="../../features/derived-signals.md"> Abgeleitete Signale</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitalias</span> </p> </td> 
   <td colname="col2"> <p>Eine an ein nicht-Cookie-basiertes Ziel übergebene ID. Für ein Cookie-basiertes Ziel ist dies der Schlüssel in einem <a href="../../reference/key-value-pairs-explained.md"> Schlüssel-Wert-Paar</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitrule/segmentrule</span> </p> </td> 
   <td colname="col2"> <p>Die tatsächliche Eigenschaft oder Segmentregel, die zur Datenerfassung verwendet wird. Eine Massenanforderung gibt die in <span class="keyword"> Audience Manager erstellten Regeln</span> mit dem <a href="../../features/traits/about-trait-builder.md"> Eigenschaftenregelaufbau</a> oder dem <a href="../../features/segments/segment-builder.md"> Segmentregelaufbau zurück</a>. Sie können diese Tools auch verwenden, um Regeln zu erstellen und sie stapelweise anzuwenden, wenn Sie ein Segment oder eine Eigenschaft aktualisieren. </p> <p>Siehe <a href="../../reference/bulk-management-tools/bulk-rules.md"> auch Erstellen oder Aktualisieren von Trait-Regeln und Segmentregeln</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traittype</span> </p> </td> 
   <td colname="col2"> <p>Eine Zeichenfolge, die den Eigenschaftstyp angibt. Zu den Optionen zählen: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_ BASED_ TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_ BOARDED_ TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel, das von DIL ausgelöst wird, wenn sich ein Benutzer für ein Segment qualifiziert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Valuealias</span> </p> </td> 
   <td colname="col2"> <p>Der Schlüssel in einem <a href="../../reference/key-value-pairs-explained.md"> Schlüssel-Wert-Paar, der</a> an ein Cookie-Ziel übergeben wird. </p> </td> 
  </tr> 
 </tbody> 
</table>


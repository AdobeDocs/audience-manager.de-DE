---
description: Ansicht einer Liste der derzeit konfigurierten Datenquellen, Hinzufügen neuer Datenquellen und Bearbeiten vorhandener Quellen.
seo-description: Ansicht einer Liste der derzeit konfigurierten Datenquellen, Hinzufügen neuer Datenquellen und Bearbeiten vorhandener Quellen.
seo-title: Liste und Einstellungen für Data Sources
solution: Audience Manager
title: Liste und Einstellungen für Data Sources
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
translation-type: tm+mt
source-git-commit: 6b55441c2bdde6cf2333852fd59fbe87f4e531eb
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---


# Liste und Einstellungen für Data Sources {#data-sources-list-and-settings}

Ansicht einer Liste der derzeit konfigurierten Datenquellen, Hinzufügen neuer Datenquellen und Bearbeiten vorhandener Quellen.

<!-- c_datasources.xml -->

Sie können Datenquellen auch mit [!DNL API] Methoden verwalten. Weitere Informationen finden Sie unter [Datenquellen-API-Methoden](../api/rest-api-main/aam-api-data-sources.md).

## Ansicht der Data Sources-Liste {#list-view}

Das [!UICONTROL Data Sources] Dashboard ist ein zentralisierter Arbeitsbereich zur Verwaltung von Datenquellen.

<!-- c_datasources_list.xml -->

Das [!UICONTROL Data Sources] Dashboard (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) enthält Funktionen und Werkzeuge, mit denen Sie:

* Zeigen Sie alle vorhandenen Datenquellen an, einschließlich der Beschreibung und des Status jeder Datenquelle und ob es sich um [!UICONTROL Inbound], [!UICONTROL Outbound]beide oder eine [!UICONTROL Shared Provider]Datenquelle handelt.
* Suche nach Datenquellen anhand des Namens.
* Erstellen, bearbeiten und löschen Sie Datenquellen.

## Datenquelleneinstellungen und Menüoptionen {#settings-menu-options}

Die Einstellungen in den verschiedenen Bereichen der [!UICONTROL Data Source] Verwaltungsoberfläche identifizieren Ihre Datenquelle, legen fest, wie sie verwendet oder freigegeben wird, und ermöglichen Ihnen die Aktivierung des Berichte für den Fehler [!UICONTROL Onboarding Status Report].

## Datenquellendetails {#details}

<!-- datasource-settings-definitions.xml -->

Zusätzlich zu den Textfeldern enthält der [!UICONTROL Data Source Details] Abschnitt die unten aufgeführten Steuerelemente und Optionen.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wenn </th> 
   <th colname="col2" class="entry"> Menüoptionen </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-Typ</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: Die Cookie-ID, die ein Gerät identifiziert. Wählen Sie diese Option, wenn Ihre Datenquelle ein Webbrowser ist oder wenn Sie mit anonymen Daten oder Daten arbeiten, die nicht mit einer einzigen Person verknüpft werden können. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Geräte-Werbe-ID</span></b>: Die Mobilgerät-ID. Wählen Sie diese Option, wenn Ihre Datenquelle ein Mobilgerät oder ein internetfähiges Gerät ist. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Geräteübergreifend</span></b>: Eine vom Kunden bereitgestellte, authentifizierte ID. Wählen Sie diese Option, wenn Sie Folgendes erstellen möchten: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Eine geräteübergreifende Datenquelle und Erstellen einer <span class="wintitle"> Profil Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Eine Datenquelle, die Links verwendet, die von der <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud-Gerätekooperation</a> oder einem anderen Gerätediagramm eines Drittanbieters bereitgestellt werden, das in <span class="keyword"> Audience Manager</span>integriert ist. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-Definition</span></b> </p> </td> 
   <td colname="col2"> <p>Die Optionen für die <b><span class="uicontrol"> ID-Definition</span></b> definieren die Beziehung, die eine Datenquelle zu einer <span class="keyword"> Audience Manager</span> -Benutzer-ID (UUID) und den zugehörigen Geräten hat, die mit der <span class="keyword"> Adobe Experience Cloud Device Co-op</span> oder einem anderen Gerätediagramm eines Drittanbieters verknüpft sind, das in <span class="keyword"> Audience Manager</span>integriert ist. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Person:</span></b> Die ID, mit der eine einzelne Person definiert wird. Diese ID kann mehreren <span class="keyword"> Audience Manager</span> -IDs zugeordnet werden. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Haushalt:</span></b> Die ID, mit der eine Gruppe von Personen definiert wird. Diese ID kann mehreren Audience Manager-IDs zugeordnet werden. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datenexportkontrolle {#export-controls}

[Data Export Controls](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Exportbeschränkungen funktionieren nur, wenn Sie eine entsprechende Exportbeschriftung für ein Ziel festlegen.

Zu den Optionen zählen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

Das [!UICONTROL Data Source Settings] enthält die unten aufgeführten Steuerelemente und Optionen. Einige dieser Einstellungen verfügen über zusätzliche Unteroptionen und Menüelemente, die Sie zum Ändern einer Datenquelle auswählen können.

### Einstellungen für eingehende Datenquelle

Aktivieren Sie das **[!UICONTROL Inbound]** Kontrollkästchen, wenn Ihre Datenquelle für den Empfang von Eingangsdaten entwickelt wurde. Wenn Sie das **[!UICONTROL Inbound]** Kontrollkästchen aktivieren, stehen Ihnen 2 weitere Kontrollgruppen zur Verfügung, die nachfolgend beschrieben werden.

>[!NOTE]
>
>Das **[!UICONTROL Inbound]** Kontrollkästchen dient nur zum Anzeigen oder Ausblenden der unten beschriebenen Datenquellen-Steuerelemente. Die Aufhebung der **[!UICONTROL Inbound]** Option hat keinerlei Auswirkungen auf die Datenerfassung. Ihre eingebetteten Daten werden unabhängig von der aktivierten Option verarbeitet.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wenn </th> 
   <th colname="col2" class="entry"> Menüoptionen </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-Typ</span></b> </p> </td> 
   <td colname="col2"> <p>Für die Option " <b><span class="uicontrol"> Inbound</span></b> "ist ein ID-Typ erforderlich. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Kunden-ID</span></b>: Identifiziert eingehende Daten mit einer Kunden-ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Audience Manager</span> -ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Experience Cloud</span> -ID. See <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Fehlerbehebung beim Dateiformat</span></b> </p> </td> 
   <td colname="col2"> <p>Wählen Sie <b><span class="uicontrol"> Dateifehlerberechnung</span></b> aktivieren, wenn Sie Probleme bei der Verarbeitung eingehender Dateien beheben müssen. Diese Funktion erzeugt einen Fehlerbeispielbericht, der Ihnen Dateiformat- und Syntaxfehler anzeigt. </p> <p>Siehe <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding-Statusbericht: Info</a> für Informationen zum Berichte und zur Fehlerberechnung. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Andere Datenquelleneinstellungen

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wenn </th> 
   <th colname="col2" class="entry"> Wann auswählen </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ausgehend</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle sendet Daten an ein Ziel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigeben aktiviert</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle kann für andere Partner freigegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als authentifiziertes Profil verwenden</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre geräteübergreifende Datenquelle enthält eine authentifizierte ID. Eine authentifizierte ID wird gesammelt und mit einer <span class="keyword"> Audience Manager</span> -ID synchronisiert, während ein Authentifizierungs-Ereignis stattfindet (z. B. wenn sich ein Benutzer vor Ort, in der App usw. anmeldet). Die authentifizierte ID kann für Daten aus anderen Quellen verwendet werden, die diese ID speichern. Es kann auch verwendet werden, um mehrere Geräte-IDs in <span class="wintitle"> Profil Link</span>zu verknüpfen. </p> <p>Diese Option zeigt ein Textfeld an, in dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Namen der Datenquelle und erscheint in den Optionen <span class="wintitle"> für</span> authentifizierte Profil, wenn Sie eine Profil-Zusammenführungsregel <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"></a>erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als Gerätediagramm verwenden</span></b> </p> </td> 
   <td colname="col2"> <p>Erstellt eine Datenquelle als Gerätediagramm, das Sie anderen <span class="keyword"> Audience Manager</span> -Kunden bereitstellen können. Bevor Sie diese Option auswählen, teilen Sie Ihrem <span class="keyword"> Audience Manager</span> -Berater mit, für welche Kunden diese <span class="wintitle"> Datenquelle</span> freigegeben werden soll. Ihr Berater muss diese Firmen im Rahmen unserer internen Verfahren bereitstellen. </p> <p>Diese Option zeigt ein Textfeld an, in dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, setzt dieser neue Name den Namen der Datenquelle außer Kraft und erscheint in den <span class="wintitle"> Geräteoptionen</span> , wenn Sie eine Profil Merge-Regel <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"></a>erstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigeben der zugehörigen Besucher- oder Geräte-IDs für bestimmte Audience Manager-Kunden</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre geräteübergreifende Datenquelle enthält IDs aus einem Gerätediagramm. Ein Gerätediagramm ist eine Sammlung von IDs, die einem Cluster eine oder mehrere <span class="keyword"> Audience Manager</span> -IDs zuordnen. Dieser Cluster repräsentiert normalerweise eine Person oder eine größere Gruppe im Haushalt. Nur für Konten verfügbar, die als "Datenanbieter"aufgeführt sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigeben von zugehörigen Besucher- oder Geräte-IDs über die Audience Manager-Plattform</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle enthält Besucher- oder Geräte-IDs, die für andere <span class="keyword"> Experience Cloud</span> -Lösungen freigegeben werden können. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Datenaufbewahrung für inaktive Kunden-IDs</span></b> </p> </td> 
   <td colname="col2"> <p>Ermöglicht Ihnen das Festlegen der Datenaufbewahrungszeit für inaktive Kunden-IDs. Dadurch wird bestimmt, wie lange Audience Manager Kunden-IDs in unserer Datenbank aufbewahrt, nachdem sie zuletzt auf der Audience Manager-Plattform angezeigt wurden.</p> <p>Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, ist 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen.</p> <p>Audience Manager führt einen Prozess aus, bei dem inaktive Kunden-IDs einmal wöchentlich gelöscht werden, entsprechend der für inaktive Kunden-IDs festgelegten Datenaufbewahrung.</p> <p>Audience Manager führt einen Prozess aus, bei dem inaktive Kunden-IDs einmal wöchentlich gelöscht werden, entsprechend der für inaktive Kunden-IDs festgelegten Datenaufbewahrung.</p> <p><b>Hinweis</b>: Diese Steuerung ist nur für geräteübergreifende Datenquellen verfügbar. Siehe auch <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Erstellen einer geräteübergreifenden Datenquelle </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unique Trait Integration Codes</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Eigenschaften derselben Datenquelle nicht denselben Integrationscode haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eindeutige Segmentintegrationscodes</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Segmente aus derselben Datenquelle nicht denselben Integrationscode haben. </p> </td> 
  </tr>
 </tbody>
</table>

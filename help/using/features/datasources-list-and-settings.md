---
description: Zeigen Sie eine Liste Ihrer derzeit konfigurierten Datenquellen an, fügen Sie neue Datenquellen hinzu und bearbeiten Sie vorhandene Quellen.
seo-description: Zeigen Sie eine Liste Ihrer derzeit konfigurierten Datenquellen an, fügen Sie neue Datenquellen hinzu und bearbeiten Sie vorhandene Quellen.
seo-title: Datenquellen-Liste und -einstellungen
solution: Audience Manager
title: Datenquellen-Liste und -einstellungen
uuid: 280 a 6 acd-fef 0-4737-a 96 d -9 e 22 fbc 8 bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Datenquellen-Liste und -einstellungen {#data-sources-list-and-settings}

Zeigen Sie eine Liste Ihrer derzeit konfigurierten Datenquellen an, fügen Sie neue Datenquellen hinzu und bearbeiten Sie vorhandene Quellen.

<!-- c_datasources.xml -->

Sie können Datenquellen auch mithilfe [!DNL API] von Methoden verwalten. Weitere Informationen finden Sie unter [Datenquellen-API-Methoden](../api/rest-api-main/aam-api-data-sources.md).

## Datenquellen-Listenansicht {#list-view}

Das [!UICONTROL Data Sources] Dashboard ist ein zentraler Arbeitsbereich zur Verwaltung von Datenquellen.

<!-- c_datasources_list.xml -->

Das [!UICONTROL Data Sources] Dashboard (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) enthält Funktionen und Tools, die Ihnen dabei helfen:

* Alle Ihre vorhandenen Datenquellen, einschließlich der Beschreibung der einzelnen Datenquellen, Status und ob es sich um [!UICONTROL Inbound]eine [!UICONTROL Outbound], beides [!UICONTROL Shared Provider]oder einen Wert handelt.
* Suchen Sie nach Datenquellen nach Name.
* Erstellen, bearbeiten und löschen Sie Datenquellen.

## Datenquelleneinstellungen und Menüoptionen {#settings-menu-options}

Die Einstellungen in den verschiedenen Abschnitten der [!UICONTROL Data Source] Verwaltungsoberfläche bestimmen Ihre Datenquelle, bestimmen die Verwendung oder Freigabe und ermöglichen die Aktivierung von Fehlerberichten für [!UICONTROL Onboarding Status Report]die.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: Die Cookie-ID, die ein Gerät kennzeichnet. Sie würden dies auswählen, wenn Ihre Datenquelle ein Webbrowser ist oder wenn Sie mit anonymen Daten oder Daten arbeiten, die nicht mit einer Person verknüpft werden können. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Gerätewerbung-ID</span></b>: Die Kennung des Mobilgeräts. Wählen Sie dies aus, wenn Ihre Datenquelle ein mobilgerät oder ein internetfähiges Gerät ist. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Cross Device</span></b>: A customer-provided, authenticated ID. Wählen Sie diese Option, wenn Sie Folgendes erstellen möchten: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">eine geräteübergreifende Datenquelle und eine Regel <span class="wintitle"></span>zum Profilzusammenführen </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Eine Datenquelle, die Links verwendet, die von der <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> oder einem anderen, in <span class="keyword"> Audience Manager integrierten Gerätediagramm verwendet</span>werden. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-Definition</span></b> </p> </td> 
   <td colname="col2"> <p>Die <b><span class="uicontrol"> ID-Definitionsoptionen</span></b> definieren die Beziehung einer Datenquelle zu einer <span class="keyword"> Audience Manager</span> -Benutzer-ID (UUID) und verknüpften Geräten, die durch das <span class="keyword"> Adobe Experience Cloud Device Co-op</span> oder ein anderes, in <span class="keyword"> Audience Manager integriertes Gerätediagramm verknüpft sind</span>. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Person:</span></b> Die ID, mit der eine einzelne Person definiert wird. Diese ID kann mehreren <span class="keyword"> Audience Manager</span> -IDs zugeordnet werden. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Haushalt:</span></b> Die ID, mit der eine Gruppe von Personen definiert wird. Diese ID kann mehreren Audience Manager-IDs zugeordnet werden. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datenexportkontrolle {#export-controls}

[Datenexportsteuerelemente](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion einen Datenschutz verletzt oder Vereinbarung verwendet. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Exporteinschränkungen funktionieren nur, wenn Sie eine übereinstimmende Exportbeschriftung auf einem Ziel festlegen.

Zu den Optionen zählen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Datenquelleneinstellungen {#data-source-settings}

Enthält [!UICONTROL Data Source Settings] die unten aufgeführten Steuerelemente und Optionen. Einige dieser Einstellungen verfügen über zusätzliche Unteroptionen und Menüelemente, die Sie zum Ändern einer Datenquelle auswählen können.

### Inbound Data Source - Einstellungen

Aktivieren Sie das **[!UICONTROL Inbound]** Kontrollkästchen, wenn die Datenquelle für den Empfang gebundener Daten bestimmt ist. Wenn Sie das **[!UICONTROL Inbound]** Kontrollkästchen aktivieren, werden zwei zusätzliche Gruppen von Steuerelementen bereitgestellt, die unten beschrieben werden.

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
   <td colname="col2"> <p>Für <b><span class="uicontrol"> die</span></b> Option "Inbound" ist ein ID-Typ erforderlich. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Kunden-ID</span></b>: Identifiziert eingehende Daten mit einer Kunden-ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Audience Manager</span> -ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Experience Cloud</span> ID. Siehe <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies und die Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Fehlerbehebung für Dateiformat</span></b> </p> </td> 
   <td colname="col2"> <p>Wählen <b><span class="uicontrol"> Sie Dateifehlerstichproben aktivieren,</span></b> wenn Sie Probleme mit der Verarbeitung von Inbound-Dateien beheben müssen. Diese Funktion generiert einen Fehlerbeispielbericht, der Ihnen Dateiformat und Syntaxfehler anzeigt. </p> <p>Siehe <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding-Statusbericht: Informationen</a> zu Fehlerberichten und Fehlerstichproben. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Andere Datenquelleneinstellungen

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wenn </th> 
   <th colname="col2" class="entry"> Wählen Sie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ausgehende</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle sendet Daten an ein Ziel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigeben aktiviert</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle kann für andere Partner freigegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als authentifizierte Profil verwenden</span></b> </p> </td> 
   <td colname="col2"> <p>Die geräteübergreifende Datenquelle enthält eine Authentifizierte ID. Während eines Authentifizierungsereignisses wird eine authentifizierte ID erfasst und mit <span class="keyword"> einer Audience Manager</span> -ID synchronisiert (z. B. sich ein Benutzer auf der Website, In-App usw. anmeldet). Die Authentifizierte ID kann für Daten aus anderen Quellen verwendet werden, die diese ID speichern. Sie kann auch verwendet werden, um mehrere Geräte-IDs im <span class="wintitle"> Profillink zu verknüpfen</span>. </p> <p>Mit dieser Option wird ein Textfeld verfügbar, mit dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Namen der Datenquelle und wird in <span class="wintitle"> den Authentifizierungsprofiloptionen</span> angezeigt, wenn Sie <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> eine Regel zum Profilzusammenführen erstellen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als Gerätediagramm verwenden</span></b> </p> </td> 
   <td colname="col2"> <p>Erstellt eine Datenquelle als Gerätediagramm, die Sie anderen <span class="keyword"> Audience Manager</span> -Kunden bereitstellen können. Bevor Sie diese Option auswählen, teilen Sie Ihrem <span class="keyword"> Audience Manager</span> Consultant mit, mit welchem Kunden diese <span class="wintitle"> Datenquelle</span> geteilt werden soll. Ihr Berater muss diese Unternehmen über unsere internen Prozesse bereitstellen. </p> <p>Mit dieser Option wird ein Textfeld verfügbar, mit dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Namen der Datenquelle und wird in den <span class="wintitle"> Geräteoptionen</span> angezeigt, wenn Sie <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> eine Regel zum Profilzusammenführen erstellen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigegebene Besucher- oder Geräte-IDs für bestimmte Audience Manager-Kunden freigeben</span></b> </p> </td> 
   <td colname="col2"> <p>Die geräteübergreifende Datenquelle enthält IDs aus einem Gerätediagramm. Ein Gerätediagramm ist eine Sammlung von IDs, die einem oder mehreren <span class="keyword"> Audience Manager</span> -IDs einem Cluster zugeordnet sind. Dieser Cluster stellt in der Regel eine Person oder größere Budgetgruppe dar. Nur für Konten verfügbar, die als "Datenanbieter" aufgeführt sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigegebene Besucher oder Geräte-IDs über die Audience Manager-Plattform freigeben</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle enthält Besucher- oder Geräte-IDs, die für andere <span class="keyword"> Experience Cloud</span> -Lösungen freigegeben werden können. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Datenaufbewahrung für inaktive Kunden-IDs</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermit können Sie die Datenaufbewahrungsdauer für inaktive Kunden-IDs festlegen. Dies legt fest, wie lange Audience Manager Kunden-IDs in unserer Datenbank beibehält, nachdem sie zuletzt auf der Audience Manager-Plattform gesehen wurden.</p> <p>Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, beträgt 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen.</p> <p>Audience Manager führt einen Prozess, der inaktive Kunden-IDs einmal wöchentlich löscht, gemäß der Datenaufbewahrung aus, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p>Audience Manager führt einen Prozess, der inaktive Kunden-IDs einmal wöchentlich löscht, gemäß der Datenaufbewahrung aus, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p><b>Hinweis</b>: Dieses Steuerelement ist nur für geräteübergreifende Datenquellen verfügbar. Siehe <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> auch Geräteübergreifende Datenquelle </a>erstellen.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Integrationscodes für eindeutige Eigenschaften</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Eigenschaften aus derselben Datenquelle nicht denselben Integrationscode haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eindeutige Segmentintegrationscodes</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Segmente aus derselben Datenquelle nicht über denselben Integrationscode verfügen. </p> </td> 
  </tr>
 </tbody>
</table>

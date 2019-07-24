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


# Data Sources List and Settings {#data-sources-list-and-settings}

Zeigen Sie eine Liste Ihrer derzeit konfigurierten Datenquellen an, fügen Sie neue Datenquellen hinzu und bearbeiten Sie vorhandene Quellen.

<!-- c_datasources.xml -->

You can also manage data sources using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## Data Sources List View {#list-view}

The [!UICONTROL Data Sources] dashboard is a centralized workspace for managing data sources.

<!-- c_datasources_list.xml -->

The [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**) contains features and tools that help you:

* See all your existing data sources, including each data source's description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* Suchen Sie nach Datenquellen nach Name.
* Erstellen, bearbeiten und löschen Sie Datenquellen.

## Data Source Settings and Menu Options {#settings-menu-options}

The settings in the different sections of the [!UICONTROL Data Source] management interface identify your data source, determine how it is used or shared, and let you enable error reporting for the [!UICONTROL Onboarding Status Report].

## Data Source Details {#details}

<!-- datasource-settings-definitions.xml -->

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

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
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Geräteübergreifend: Eine vom Kunden bereitgestellte, authentifizierte ID. </span></b> Wählen Sie diese Option, wenn Sie Folgendes erstellen möchten: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-Definition</span></b> </p> </td> 
   <td colname="col2"> <p>The <b><span class="uicontrol"> ID Definition</span></b> options define the relationship a data source has to an <span class="keyword"> Audience Manager</span> user ID (UUID) and associated devices linked by the <span class="keyword"> Adobe Experience Cloud Device Co-op</span> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Person:</span></b> Die ID, mit der eine einzelne Person definiert wird. This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Haushalt:</span></b> Die ID, mit der eine Gruppe von Personen definiert wird. Diese ID kann mehreren Audience Manager-IDs zugeordnet werden. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datenexportkontrolle {#export-controls}

[Datenexportsteuerelemente](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion einen Datenschutz verletzt oder Vereinbarung verwendet. Skip this section if you do not use [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Exporteinschränkungen funktionieren nur, wenn Sie eine übereinstimmende Exportbeschriftung auf einem Ziel festlegen.

Zu den Optionen zählen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

The [!UICONTROL Data Source Settings] contains the controls and options listed below. Einige dieser Einstellungen verfügen über zusätzliche Unteroptionen und Menüelemente, die Sie zum Ändern einer Datenquelle auswählen können.

### Inbound Data Source - Einstellungen

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL Inbound]** check box exposes 2 additional groups of controls described below.

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
   <td colname="col2"> <p>The <b><span class="uicontrol"> Inbound</span></b> option requires an ID type. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Kunden-ID</span></b>: Identifiziert eingehende Daten mit einer Kunden-ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Audience Manager</span> -ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Experience Cloud</span> ID. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Fehlerbehebung für Dateiformat</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. Diese Funktion generiert einen Fehlerbeispielbericht, der Ihnen Dateiformat und Syntaxfehler anzeigt. </p> <p>See <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
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
   <td colname="col2"> <p>Die geräteübergreifende Datenquelle enthält eine Authentifizierte ID. An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). Die Authentifizierte ID kann für Daten aus anderen Quellen verwendet werden, die diese ID speichern. It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>Mit dieser Option wird ein Textfeld verfügbar, mit dem Sie die Datenquelle mit einem Alias umbenennen können. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als Gerätediagramm verwenden</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. Ihr Berater muss diese Unternehmen über unsere internen Prozesse bereitstellen. </p> <p>Mit dieser Option wird ein Textfeld verfügbar, mit dem Sie die Datenquelle mit einem Alias umbenennen können. If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigegebene Besucher- oder Geräte-IDs für bestimmte Audience Manager-Kunden freigeben</span></b> </p> </td> 
   <td colname="col2"> <p>Die geräteübergreifende Datenquelle enthält IDs aus einem Gerätediagramm. A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. Dieser Cluster stellt in der Regel eine Person oder größere Budgetgruppe dar. Nur für Konten verfügbar, die als "Datenanbieter" aufgeführt sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigegebene Besucher oder Geräte-IDs über die Audience Manager-Plattform freigeben</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Datenaufbewahrung für inaktive Kunden-IDs</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermit können Sie die Datenaufbewahrungsdauer für inaktive Kunden-IDs festlegen. Dies legt fest, wie lange Audience Manager Kunden-IDs in unserer Datenbank beibehält, nachdem sie zuletzt auf der Audience Manager-Plattform gesehen wurden.</p> <p>Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, beträgt 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen.</p> <p>Audience Manager führt einen Prozess, der inaktive Kunden-IDs einmal wöchentlich löscht, gemäß der Datenaufbewahrung aus, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p>Audience Manager führt einen Prozess, der inaktive Kunden-IDs einmal wöchentlich löscht, gemäß der Datenaufbewahrung aus, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p><b>Hinweis</b>: Dieses Steuerelement ist nur für geräteübergreifende Datenquellen verfügbar. See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
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

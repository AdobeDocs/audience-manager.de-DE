---
description: Zeigen Sie eine Liste Ihrer derzeit konfigurierten Datenquellen an, fügen Sie neue Datenquellen hinzu und bearbeiten Sie vorhandene Quellen.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Data Sources-Liste und -Einstellungen
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# [!UICONTROL Data Sources] Liste und Einstellungen {#data-sources-list-and-settings}

Zeigen Sie eine Liste Ihrer derzeit konfigurierten [!UICONTROL data sources] an, fügen Sie neue [!UICONTROL data sources] hinzu und bearbeiten Sie vorhandene [!UICONTROL data sources].

Sie können auch [!UICONTROL data sources] mit den Methoden [!DNL API] verwalten. Weitere Informationen finden Sie unter [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Listenansicht {#list-view}

Das Dashboard [!UICONTROL Data Sources] ist ein zentralisierter Arbeitsbereich zur Verwaltung von Datenquellen.

Das Dashboard [!UICONTROL Data Sources] (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) enthält Funktionen und Tools, die Ihnen helfen,

* Sehen Sie sich all Ihre vorhandenen [!UICONTROL data sources] an, einschließlich der Beschreibung und des Status jeder Datenquelle und ob es sich um [!UICONTROL Inbound], [!UICONTROL Outbound], beide oder eine [!UICONTROL Shared Provider] handelt.
* Suchen Sie nach &quot;[!UICONTROL data sources]&quot;anhand des Namens.
* Erstellen, bearbeiten und löschen Sie [!UICONTROL data sources].

## [!DNL Data Source] Einstellungen und Menüoptionen {#settings-menu-options}

Die Einstellungen in den verschiedenen Abschnitten der Verwaltungsoberfläche von [!UICONTROL Data Source] identifizieren Ihren [!DNL data source], bestimmen, wie er verwendet oder freigegeben wird, und ermöglichen Ihnen die Aktivierung der Fehlerberichte für den [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Details {#details}

Zusätzlich zu den Textfeldern enthält der Abschnitt [!UICONTROL Data Source Details] die unten aufgeführten Steuerelemente und Optionen.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: Die Cookie-ID, die ein Gerät identifiziert. Wählen Sie diese Option aus, wenn Ihre Datenquelle ein Webbrowser ist oder wenn Sie mit anonymen Daten oder Daten arbeiten, die nicht einer einzelnen Person zugeordnet werden können. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Geräte-Advertising-ID</span></b>: Die Kennung des Mobilgeräts. Wählen Sie diese Option aus, wenn Ihre Datenquelle ein Mobilgerät oder ein internetfähiges Gerät ist. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Geräteübergreifend</span></b>: Eine vom Kunden bereitgestellte, authentifizierte ID. Wählen Sie diese Option aus, wenn Sie Folgendes erstellen möchten: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Eine geräteübergreifende Datenquelle und erstellen Sie eine <span class="wintitle"> Profilzusammenführungsrichtlinie</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Eine Datenquelle, die Links verwendet, die von einem Gerätediagramm eines Drittanbieters bereitgestellt werden, das in <span class="keyword"> Audience Manager</span> integriert ist. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-Definition</span></b> </p> </td> 
   <td colname="col2"> <p>Die Optionen für die <b><span class="uicontrol"> ID-Definition</span></b> definieren die Beziehung, die eine Datenquelle zu einer <span class="keyword"> Audience Manager</span>-Benutzer-ID (UUID) und zugehörigen Geräten hat, die durch ein Gerätediagramm eines Drittanbieters verknüpft sind, das mit <span class="keyword"> Audience Manager</span> integriert ist. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Person:</span></b> Die ID, die zur Definition einer einzelnen Person verwendet wird. Diese ID kann mehreren <span class="keyword"> Audience Manager</span> -IDs zugeordnet werden. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Haushalt:</span></b> Die ID, mit der eine Personengruppe definiert wird. Diese ID kann mehreren Audience Manager-IDs zugeordnet werden. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Datenexportkontrollen](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine [!UICONTROL data source] und eine [!UICONTROL destination] anwenden können. Sie verhindern, dass Sie Daten an eine [!UICONTROL destination] senden, wenn diese Aktion eine Datenschutz- oder Nutzungsvereinbarung verletzt. Überspringen Sie diesen Abschnitt, wenn Sie nicht [!UICONTROL Data Export Controls] verwenden.

>[!IMPORTANT]
>
>Exportbeschränkungen funktionieren nur, wenn Sie eine entsprechende Exportbeschriftung auf &quot;[!UICONTROL destination]&quot;festlegen.

Zu den Optionen zählen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Einstellungen {#data-source-settings}

Der [!UICONTROL Data Source Settings] enthält die unten aufgeführten Steuerelemente und Optionen. Einige dieser Einstellungen verfügen über zusätzliche Unteroptionen und Menüelemente, mit denen Sie eine Datenquelle ändern können.

### [!UICONTROL Inbound Data Source] Einstellungen

Aktivieren Sie das Kontrollkästchen **[!UICONTROL Inbound]** , wenn Ihre Datenquelle für den Empfang eingehender Daten entwickelt wurde. Wenn Sie das Kontrollkästchen **[!UICONTROL Inbound]** aktivieren, werden 2 weitere Gruppen von Steuerelementen angezeigt, die nachfolgend beschrieben werden.

>[!NOTE]
>
>Das Kontrollkästchen **[!UICONTROL Inbound]** dient nur dazu, die unten beschriebenen [!UICONTROL data source]-Steuerelemente ein- oder auszublenden. Das Deaktivieren der Option **[!UICONTROL Inbound]** wirkt sich in keiner Weise auf die Datenerfassung aus. Ihre integrierten Daten werden unabhängig von der aktivierten Option verarbeitet.

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
   <td colname="col2"> <p>Für die Option <b><span class="uicontrol"> Inbound</span></b> ist ein ID-Typ erforderlich. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Kunden-ID</span></b>: Identifiziert eingehende Daten mit einer Kunden-ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Audience Manager-ID</span>. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Experience Cloud</span> ID. Siehe <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies und die Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Fehlerbehebung bei Dateiformat</span></b> </p> </td> 
   <td colname="col2"> <p>Wählen Sie <b><span class="uicontrol"> Enable file error sampling</span></b> , wenn Sie Probleme mit der Verarbeitung eingehender Dateien beheben müssen. Diese Funktion erzeugt einen Fehlerbeispielbericht, der Ihnen Dateiformat- und Syntaxfehler anzeigt. </p> <p>Informationen zu Fehlerberichten und Fehlerproben finden Sie unter <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding-Statusbericht: Info über </a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

### Andere [!UICONTROL Data Source] Einstellungen

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wenn </th> 
   <th colname="col2" class="entry"> Auswählen, wann </th> 
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
   <td colname="col2"> <p>Ihre geräteübergreifende Datenquelle enthält eine Authentifizierte ID. Eine authentifizierte ID wird erfasst und mit einer <span class="keyword"> Audience Manager</span>-ID synchronisiert, während eines Authentifizierungsereignisses (z. B. Anmeldung vor Ort, in der App usw.). Die authentifizierte ID kann verwendet werden, um Daten aus anderen Quellen zu integrieren, die diese ID speichern. Sie kann auch verwendet werden, um mehrere Geräte-IDs in <span class="wintitle"> Profil-Link</span> zu verknüpfen. </p> <p>Diese Option zeigt ein Textfeld an, in dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Datenquellennamen und wird in den <span class="wintitle"> Authentifizierten Profiloptionen</span> angezeigt, wenn Sie <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> eine Profilzusammenführungsregel erstellen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als Gerätediagramm verwenden</span></b> </p> </td> 
   <td colname="col2"> <p>Erstellt eine Datenquelle als Gerätediagramm, das Sie für andere <span class="keyword"> Audience Manager</span>-Kunden bereitstellen können. Bevor Sie diese Option auswählen, teilen Sie Ihrem <span class="keyword"> Audience Manager</span>-Berater mit, für welche Kunden diese <span class="wintitle"> Data Source</span> freigegeben werden soll. Ihr Berater muss diese Unternehmen über unsere internen Prozesse bereitstellen. </p> <p>Diese Option zeigt ein Textfeld an, in dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Datenquellennamen und wird in den <span class="wintitle"> Geräteoptionen</span> angezeigt, wenn Sie <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> eine Profilzusammenführungsregel erstellen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zugeordnete Besucher- oder Geräte-IDs für bestimmte Audience Manager-Kunden freigeben</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre geräteübergreifende Datenquelle enthält IDs aus einem Gerätediagramm. Ein Gerätediagramm ist eine Sammlung von IDs, die einem Cluster eine oder mehrere <span class="keyword"> Audience Manager</span> -IDs zuordnen. Dieser Cluster stellt normalerweise eine Person oder eine größere Gruppe von Haushalten dar. Nur für Konten verfügbar, die als "Datenanbieter"aufgeführt sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Teilen Sie zugeordnete Besucher- oder Geräte-IDs über die Audience Manager-Plattform hinweg.</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle enthält Besucher- oder Geräte-IDs, die für andere <span class="keyword"> Experience Cloud</span> -Lösungen freigegeben werden können. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Datenbeibehaltung für inaktive Kunden-IDs</span></b> </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Festlegung des Aufbewahrungszeitraums für inaktive Kunden-IDs. Dadurch wird bestimmt, wie lange der Audience Manager Kunden-IDs in unserer Datenbank aufbewahrt, nachdem sie zuletzt auf der Audience Manager-Plattform angezeigt wurden.</p> <p>Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, ist 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen.</p> <p>Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich löscht. Dies entspricht der Datenaufbewahrung, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p>Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich löscht. Dies entspricht der Datenaufbewahrung, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p><b>Hinweis</b>: Dieses Steuerelement ist nur für geräteübergreifende Datenquellen verfügbar. Siehe auch <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Erstellen einer geräteübergreifenden Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unique Trait-Integrationscodes </span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Eigenschaften aus derselben Datenquelle nicht denselben Integrationscode aufweisen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Eindeutige Segmentintegrationscodes</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Segmente aus derselben Datenquelle nicht denselben Integrationscode haben. </p> </td> 
  </tr>
 </tbody>
</table>

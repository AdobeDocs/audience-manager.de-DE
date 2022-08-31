---
description: Zeigen Sie eine Liste Ihrer derzeit konfigurierten Datenquellen an, fügen Sie neue Datenquellen hinzu und bearbeiten Sie vorhandene Quellen.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Liste der Data Sources und Einstellungen
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---

# [!UICONTROL Data Sources] Liste und Einstellungen {#data-sources-list-and-settings}

Anzeigen einer Liste Ihrer derzeit konfigurierten [!UICONTROL data sources], neue hinzufügen [!UICONTROL data sources]und vorhandene bearbeiten [!UICONTROL data sources].

Sie können auch [!UICONTROL data sources] using [!DNL API] -Methoden. Weitere Informationen finden Sie unter [API-Methoden für Datenquellen](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources]Listenansicht {#list-view}

Die [!UICONTROL Data Sources] Dashboard ist ein zentralisierter Arbeitsbereich zur Verwaltung von Datenquellen.

Die [!UICONTROL Data Sources] Dashboard (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) enthält Funktionen und Tools, die Ihnen bei Folgendem helfen:

* Alle vorhandenen anzeigen [!UICONTROL data sources], einschließlich der Beschreibung, des Status und der Frage, ob es sich um eine Datenquelle handelt [!UICONTROL Inbound], [!UICONTROL Outbound], beides oder ein [!UICONTROL Shared Provider].
* Suchen Sie nach [!UICONTROL data sources] nach Namen.
* Erstellen, Bearbeiten und Löschen [!UICONTROL data sources].

## [!DNL Data Source] Einstellungen und Menüoptionen {#settings-menu-options}

Die Einstellungen in den verschiedenen Abschnitten der [!UICONTROL Data Source] Management-Oberfläche zur Identifizierung von [!DNL data source], bestimmen Sie, wie es verwendet oder freigegeben wird, und aktivieren Sie die Fehlerberichterstellung für die [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Details {#details}

Zusätzlich zu den Textfeldern wird die [!UICONTROL Data Source Details] enthält die unten aufgeführten Steuerelemente und Optionen.

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
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Eine Datenquelle, die Links verwendet, die von einem Gerätediagramm eines Drittanbieters bereitgestellt werden, das in <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-Definition</span></b> </p> </td> 
   <td colname="col2"> <p>Die <b><span class="uicontrol"> ID-Definition</span></b> Optionen definieren die Beziehung, die eine Datenquelle zu einer <span class="keyword"> Audience Manager</span> Benutzer-ID (UUID) und zugehörige Geräte, die durch ein Gerätediagramm eines Drittanbieters verknüpft sind, das mit <span class="keyword"> Audience Manager</span>. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Person:</span></b> Die ID, die zur Definition einer einzelnen Person verwendet wird. Diese ID kann mehreren <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Haushalt:</span></b> Die ID, die zur Definition einer Personengruppe verwendet wird. Diese ID kann mehreren Audience Manager-IDs zugeordnet werden. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Datenexportkontrollen](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine [!UICONTROL data source] und [!UICONTROL destination]. Sie verhindern das Senden von Daten an eine [!UICONTROL destination] wenn diese Aktion eine Datenschutz- oder Nutzungsvereinbarung verletzt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Exportbeschränkungen funktionieren nur, wenn Sie eine entsprechende Exportbezeichnung auf einer [!UICONTROL destination].

Zu den Optionen zählen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Einstellungen {#data-source-settings}

Die [!UICONTROL Data Source Settings] enthält die unten aufgeführten Steuerelemente und Optionen. Einige dieser Einstellungen verfügen über zusätzliche Unteroptionen und Menüelemente, mit denen Sie eine Datenquelle ändern können.

### [!UICONTROL Inbound Data Source] Einstellungen

Wählen Sie die **[!UICONTROL Inbound]** aktivieren, wenn Ihre Datenquelle für den Empfang eingehender Daten entwickelt wurde. Auswählen der **[!UICONTROL Inbound]** Kontrollkästchen stellt 2 weitere, unten beschriebene Kontrollgruppen bereit.

>[!NOTE]
>
>Die **[!UICONTROL Inbound]** das Kontrollkästchen nur zum Anzeigen oder Verbergen der [!UICONTROL data source] Steuerelemente, die nachfolgend beschrieben werden. Deaktivieren Sie die **[!UICONTROL Inbound]** hat keinerlei Auswirkungen auf die Datenerfassung. Ihre integrierten Daten werden unabhängig von der aktivierten Option verarbeitet.

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
   <td colname="col2"> <p>Die <b><span class="uicontrol"> Eingehend</span></b> -Option einen ID-Typ erfordert. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Kunden-ID</span></b>: Identifiziert eingehende Daten mit einer Kunden-ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Audience Manager</span> Kennung. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud-ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Experience Cloud</span> Kennung. Siehe <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies und die Experience Cloud-ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Fehlerbehebung bei Dateiformaten</span></b> </p> </td> 
   <td colname="col2"> <p>Auswählen <b><span class="uicontrol"> Dateifehlerberechnung aktivieren</span></b> wenn Sie Probleme mit der Verarbeitung eingehender Dateien beheben müssen. Diese Funktion erzeugt einen Fehlerbeispielbericht, der Ihnen Dateiformat- und Syntaxfehler anzeigt. </p> <p>Siehe <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding-Statusbericht: Info</a> für Informationen zu Fehlerberichten und Fehlerstichproben. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Sonstiges [!UICONTROL Data Source] Einstellungen

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
   <td colname="col2"> <p>Ihre geräteübergreifende Datenquelle enthält eine Authentifizierte ID. Eine authentifizierte ID wird erfasst und mit einer <span class="keyword"> Audience Manager</span> ID während eines Authentifizierungsereignisses (z. B. Anmeldung eines Benutzers vor Ort, in der App usw.). Die authentifizierte ID kann verwendet werden, um Daten aus anderen Quellen zu integrieren, die diese ID speichern. Sie kann auch verwendet werden, um mehrere Geräte-IDs in <span class="wintitle"> Profillink</span>. </p> <p>Diese Option zeigt ein Textfeld an, in dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Datenquellennamen und erscheint im <span class="wintitle"> Authentifizierte Profiloptionen</span> wenn Sie <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> Erstellen einer Profilzusammenführungsregel</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als Gerätediagramm verwenden</span></b> </p> </td> 
   <td colname="col2"> <p>Erstellt eine Datenquelle als Gerätediagramm, das Sie für andere bereitstellen können <span class="keyword"> Audience Manager</span> -Kunden. Bevor Sie diese Option auswählen, informieren Sie über <span class="keyword"> Audience Manager</span> -Berater, der diese <span class="wintitle"> Datenquelle</span> sollte für freigegeben werden. Ihr Berater muss diese Unternehmen über unsere internen Prozesse bereitstellen. </p> <p>Diese Option zeigt ein Textfeld an, in dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Datenquellennamen und erscheint im <span class="wintitle"> Geräteoptionen</span> wenn Sie <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> Erstellen einer Profilzusammenführungsregel</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zugeordnete Besucher- oder Geräte-IDs für bestimmte Audience Manager-Kunden freigeben</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre geräteübergreifende Datenquelle enthält IDs aus einem Gerätediagramm. Ein Gerätediagramm ist eine Sammlung von IDs, die einer oder mehreren <span class="keyword"> Audience Manager</span> IDs zu einem Cluster. Dieser Cluster stellt normalerweise eine Person oder eine größere Gruppe von Haushalten dar. Nur für Konten verfügbar, die als "Datenanbieter"aufgeführt sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zugeordnete Besucher- oder Geräte-IDs über die Audience Manager Platform freigeben</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle enthält Besucher- oder Geräte-IDs, die für andere freigegeben werden können. <span class="keyword"> Experience Cloud</span> Lösungen. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Datenbeibehaltung für inaktive Kunden-IDs</span></b> </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Festlegung des Aufbewahrungszeitraums für inaktive Kunden-IDs. Dadurch wird bestimmt, wie lange der Audience Manager Kunden-IDs in unserer Datenbank aufbewahrt, nachdem sie zuletzt auf der Audience Manager-Plattform angezeigt wurden.</p> <p>Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, ist 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen.</p> <p>Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich löscht. Dies entspricht der Datenaufbewahrung, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p>Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich löscht. Dies entspricht der Datenaufbewahrung, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p><b>Hinweis</b>: Diese Steuerung ist nur für geräteübergreifende Datenquellen verfügbar. Siehe auch <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Geräteübergreifende Datenquelle erstellen </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unique Trait-Integrationscodes</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Eigenschaften aus derselben Datenquelle nicht denselben Integrationscode aufweisen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unique Segment-Integrationscodes</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Segmente aus derselben Datenquelle nicht denselben Integrationscode haben. </p> </td> 
  </tr>
 </tbody>
</table>

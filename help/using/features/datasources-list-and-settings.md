---
description: Zeigen Sie eine Liste Ihrer derzeit konfigurierten Datenquellen an, fügen Sie neue Datenquellen hinzu und bearbeiten Sie vorhandene Quellen.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Datenquellenliste und Einstellungen
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# [!UICONTROL Data Sources] und Einstellungen {#data-sources-list-and-settings}

Zeigen Sie eine Liste Ihrer derzeit konfigurierten [!UICONTROL data sources] an, fügen Sie neue [!UICONTROL data sources] hinzu und bearbeiten Sie vorhandene [!UICONTROL data sources].

Sie können [!UICONTROL data sources] auch mit [!DNL API] Methoden verwalten. Weitere Informationen finden Sie unter [Data Source-API-Methoden](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Listenansicht {#list-view}

Das [!UICONTROL Data Sources]-Dashboard ist ein zentralisierter Arbeitsbereich für die Verwaltung von Datenquellen.

Das [!UICONTROL Data Sources]-Dashboard (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) enthält Funktionen und Tools, die Ihnen bei Folgendem helfen:

* Zeigen Sie alle vorhandenen [!UICONTROL data sources] an, einschließlich der Beschreibung, des Status jeder Datenquelle und ob es sich um [!UICONTROL Inbound], [!UICONTROL Outbound], beides oder eine [!UICONTROL Shared Provider] handelt.
* Nach [!UICONTROL data sources] anhand des Namens suchen.
* Erstellen, Bearbeiten und Löschen von [!UICONTROL data sources].

## [!DNL Data Source] Einstellungen und Menüoptionen {#settings-menu-options}

Die Einstellungen in den verschiedenen Abschnitten der [!UICONTROL Data Source]-Verwaltungsoberfläche identifizieren Ihre [!DNL data source], legen fest, wie sie verwendet oder freigegeben wird, und ermöglichen es Ihnen, die Fehlerberichterstattung für die [!UICONTROL Onboarding Status Report] zu aktivieren.

## [!DNL Data Source] {#details}

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: Die Cookie-ID, die ein Gerät identifiziert. Sie können diese Option auswählen, wenn Ihre Datenquelle ein Webbrowser ist oder wenn Sie mit anonymen Daten oder Daten arbeiten, die nicht mit einer einzelnen Person verknüpft werden können. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Advertising-ID</span></b>: Die Kennung des Mobilgeräts. Wählen Sie diese Option aus, wenn es sich bei Ihrer Datenquelle um ein Mobilgerät oder ein internetfähiges Gerät handelt. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Cross Device</span></b>: Eine vom Kunden bereitgestellte, authentifizierte ID. Wählen Sie diese Option aus, wenn Sie Folgendes erstellen möchten: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Erstellen Sie eine geräteübergreifende Datenquelle und eine <span class="wintitle"> Profilzusammenführungsregel</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Eine Datenquelle, die Links verwendet, die von einem in <span class="keyword"> Audience Manager integrierten Gerätediagramm eines Drittanbieters bereitgestellt </span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-Definition</span></b> </p> </td> 
   <td colname="col2"> <p>Die Optionen <b><span class="uicontrol">-ID</span></b> definieren die Beziehung einer Datenquelle zu einer <span class="keyword"> Audience Manager</span>-Benutzer-ID (UUID) und den zugehörigen Geräten, die durch ein in <span class="keyword"> Audience Manager integriertes Gerätediagramm eines Drittanbieters verknüpft sind</span>. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Person</span></b> Die ID, die zur Definition einer einzelnen Person verwendet wird. Diese ID kann mehreren <span class="keyword"> Audience Manager</span> IDs zugeordnet werden. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Haushalt</span></b> Die ID, die zum Definieren einer Gruppe von Personen verwendet wird. Diese ID kann mehreren Audience Manager-IDs zugeordnet werden. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Datenexportsteuerelemente](../features/data-export-controls.md) sind optionale Klassifizierungsregeln, die Sie auf eine [!UICONTROL data source] und [!UICONTROL destination] anwenden können. Sie verhindern, dass Sie Daten an einen [!UICONTROL destination] senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

>[!IMPORTANT]
>
>Exportbeschränkungen funktionieren nicht, es sei denn, Sie legen eine entsprechende Exportkennzeichnung für eine [!UICONTROL destination] fest.

Zu den Optionen zählen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] {#data-source-settings}

Die [!UICONTROL Data Source Settings] enthält die unten aufgeführten Steuerelemente und Optionen. Einige dieser Einstellungen verfügen über zusätzliche Unteroptionen und Menüelemente, die Sie auswählen können, um eine Datenquelle zu ändern.

### [!UICONTROL Inbound Data Source]

Aktivieren Sie das Kontrollkästchen **[!UICONTROL Inbound]** , wenn Ihre Datenquelle für den Empfang eingehender Daten entwickelt wurde. Wenn Sie das Kontrollkästchen **[!UICONTROL Inbound]** aktivieren, werden zwei zusätzliche Gruppen von Steuerelementen angezeigt, die unten beschrieben werden.

>[!NOTE]
>
>Das Kontrollkästchen **[!UICONTROL Inbound]** dient nur dazu, die unten beschriebenen [!UICONTROL data source] ein- oder auszublenden. Wenn Sie die Option **[!UICONTROL Inbound]** deaktivieren, wirkt sich dies in keiner Weise auf die Datenaufnahme aus. Ihre integrierten Daten werden unabhängig von der Aktivierung dieser Option verarbeitet.

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
   <td colname="col2"> <p>Die Option <b><span class="uicontrol">Inbound</span></b> erfordert einen ID-Typ. Zu den Optionen zählen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Kunden-</span></b>: Identifiziert eingehende Daten mit einer Kunden-ID. </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Audience Manager</span> ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: Identifiziert eingehende Daten mit einer <span class="keyword"> Experience Cloud</span> ID. Siehe <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=de" format="https" scope="external"> Cookies und die Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Fehlerbehebung bei <b><span class="uicontrol">-Dateiformaten</span></b> </p> </td> 
   <td colname="col2"> <p>Wählen Sie <b><span class="uicontrol"> Enable file error sampling</span></b>, wenn Sie Probleme bei der Verarbeitung eingehender Dateien beheben müssen. Diese Funktion generiert einen Fehlerbeispielbericht, der Ihnen Dateiformat- und Syntaxfehler zeigt. </p> <p>Weitere Informationen zu Fehlerberichten und <a href="../reporting/onboarding-status-report.md#onboarding-status-about">-Stichproben finden Sie unter </a> Onboarding-Statusbericht: Über. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Andere [!UICONTROL Data Source]

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Wenn </th> 
   <th colname="col2" class="entry"> Auswählen, wenn </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ausgehend</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle sendet Daten an ein Ziel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigabe aktiviert</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle kann für andere Partner freigegeben werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Verwendung als authentifiziertes Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre geräteübergreifende Datenquelle enthält eine authentifizierte ID. Eine authentifizierte ID wird erfasst und mit einer <span class="keyword"> Audience Manager</span> ID während eines Authentifizierungsereignisses synchronisiert (z. B. Benutzeranmeldung vor Ort, In-App-Anmeldung usw.). Mit der authentifizierten ID können Daten aus anderen Quellen integriert werden, in denen diese ID gespeichert ist. Es kann auch verwendet werden, um mehrere Geräte-IDs in <span class="wintitle"> Profillink zu verknüpfen</span>. </p> <p>Diese Option stellt ein Textfeld bereit, mit dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Datenquellennamen und wird in den <span class="wintitle"> Optionen für authentifizierte Profile angezeigt</span> wenn Sie eine Profilzusammenführungsregel erstellen <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"></a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Verwendung als Gerätediagramm</span></b> </p> </td> 
   <td colname="col2"> <p>Erstellt eine Datenquelle als Gerätediagramm, das Sie anderen <span class="keyword"> Audience Manager</span>-Kunden bereitstellen können. Bevor Sie diese Option auswählen, teilen Sie Ihrem <span class="keyword"> Audience Manager</span> Berater mit, für welche Kunden diese <span class="wintitle"> Data Source </span> werden soll. Ihr Berater muss diese Unternehmen über unsere internen Prozesse bereitstellen. </p> <p>Diese Option stellt ein Textfeld bereit, mit dem Sie die Datenquelle mit einem Alias umbenennen können. Wenn Sie einen Alias verwenden, überschreibt dieser neue Name den Datenquellennamen und wird in den <span class="wintitle"> Geräteoptionen angezeigt</span> wenn Sie eine Profilzusammenführungsregel erstellen <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"></a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigeben von zugehörigen Besucher- oder Geräte-IDs für bestimmte Audience Manager-Kunden</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre geräteübergreifende Datenquelle enthält IDs aus einem Gerätediagramm. Ein Gerätediagramm ist eine Sammlung von IDs, die einem oder mehreren <span class="keyword"> Audience Manager</span>IDs einem Cluster zugeordnet sind. Dieser Cluster stellt normalerweise eine Person oder eine größere Haushaltsgruppe dar. Nur für als „Datenanbieter“ aufgeführte Konten verfügbar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Freigeben von zugehörigen Besucher- oder Geräte-IDs in der Audience Manager-Plattform</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre Datenquelle enthält Besucher- oder Geräte-IDs, die über andere <span class="keyword"> Experience Cloud</span>-Lösungen hinweg freigegeben werden können. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> der Datenaufbewahrung für inaktive Kunden-IDs</span></b> </p> </td> 
   <td colname="col2"> <p>Ermöglicht die Festlegung des Zeitraums für die Datenaufbewahrung für inaktive Kunden-IDs. Dadurch wird bestimmt, wie lange Audience Manager Kunden-IDs in unserer Datenbank speichert, nachdem sie zuletzt auf der Audience Manager-Plattform gesehen wurden.</p> <p>Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie festlegen können, ist 1 Monat und der Höchstwert ist 5 Jahre. Beachten Sie, dass wir alle Monate als 30-Tage zählen.</p> <p>Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich gemäß der Datenaufbewahrung löscht, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p>Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich gemäß der Datenaufbewahrung löscht, die Sie für inaktive Kunden-IDs festgelegt haben.</p> <p><b>Hinweis</b>: Dieses Steuerelement ist nur für geräteübergreifende Datenquellen verfügbar. Siehe auch <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Erstellen einer geräteübergreifenden Daten-Source-</a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> eindeutigen Codes für die Eigenschaftsintegration</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten sicherstellen, dass zwei Eigenschaften aus derselben Datenquelle nicht denselben Integrations-Code haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> eindeutige Segmentintegrations-Codes</span></b> </p> </td> 
   <td colname="col2"> <p>Sie möchten erzwingen, dass zwei Segmente aus derselben Datenquelle nicht denselben Integrations-Code haben. </p> </td> 
  </tr>
 </tbody>
</table>

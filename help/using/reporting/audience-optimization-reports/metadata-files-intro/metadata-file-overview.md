---
description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen in den verschiedenen Berichtoptionsmenüs lesbare Namen an.
seo-description: Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen in den verschiedenen Berichtoptionsmenüs lesbare Namen an.
seo-title: Übersicht und Zuordnungen für Metadatendateien
solution: Audience Manager
title: Übersicht und Zuordnungen für Metadatendateien
uuid: 70 df 7 f 11-69 c 5-4873-a 69 d -8 f 93 f 9837
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Übersicht und Zuordnungen für Metadatendateien{#overview-and-mappings-for-metadata-files}

Eine Metadatendatei verknüpft numerische IDs mit Namen, die Sie lesen und verstehen können. Die Berichte zur Zielgruppenoptimierung zeigen in den verschiedenen Berichtoptionsmenüs lesbare Namen an.

## Überblick {#overview}

Eine Überprüfung der Metadaten und deren Verwendung. Eine Metadatendatei muss von einer Datendatei begleitet werden. Der Inhalt der Metadatendatei stimmt mit Datendateiinformationen zu verwandten, menschen lesbaren Beschriftungen in den Berichtmenüs überein. Weitere Informationen finden Sie unter [Datendateien für Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md).

### Metadatendateien enthalten Daten zu anderen Daten

Eine Metadatendatei enthält Informationen zu anderen Datentypen. Um zu verstehen, wie dies funktioniert, sehen wir uns an, wie Daten [!DNL Audience Manager] empfangen werden.

[!DNL Audience Manager] Empfängt während eines Impressions- oder Klickereignisses Daten in einer URL-Zeichenfolge, die als *Ereignisaufruf bezeichnet*wird.

Der Ereignisaufruf gliedert Informationen in Gruppen definierter Schlüssel-Wert-Paare. Die Werte in einem Schlüssel-Wert-Paar enthalten numerische Daten. Die Metadatendatei enthält Namen und andere lesbare Informationen, die der ID in jedem Schlüssel-Wert-Paar entsprechen.

### Metadaten-Link-IDs zu lesbaren Namen

Die Metadatendatei ist erforderlich, um eine numerische ID mit einem lesbaren Namen zu verknüpfen. Beispiel: Ein Ereignisaufruf enthält eine Creative ID in einem Schlüssel-Wert-Paar wie folgt: `d_creative:1234`. Ohne Metadatendatei würde dieses kreative Element in einem Optionsmenü als 1234 angezeigt.

Eine ordnungsgemäß formatierte Metadatendatei kann dieses kreative Element jedoch mit einem echten Namen wie &quot;Advertiser Creative A&quot; verknüpfen. Dies ist ein Name, den Sie in einem Bericht lesen und erkennen können.

### Wann benötigen Sie eine Metadatendatei?

Zunächst sind eine Metadatendatei und alle unten aufgeführten Parameter in einem Ereignisaufruf erforderlich, wenn Sie die [Zielgruppenoptimierungsberichte verwenden möchten](../../../reporting/audience-optimization-reports/audience-optimization-reports.md).

Zweitens benötigen Sie eine Metadatendatei, wenn Sie Ihre eigenen Daten senden [!DNL Audience Manager] oder Daten in den Berichten anderer Anbieter anzeigen möchten, in die wir nicht integriert sind. Beispiel: [!DNL Audience Manager] Eine Integration mit Google [Doppelklicken auf Kampagnen-Manager](../../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) (DCM). Aufgrund dieser Beziehung [!DNL Audience Manager] können Sie IDs mit Namen und Beschreibungen verbinden, die von den Berichtoptionen verwendet werden. Ohne Integration können wir trotzdem Daten erfassen, aber die Berichtsoptionen zeigen numerische IDs anstelle von beschreibendem Namen an.

![](assets/metadata_menu.png)

## Dateizuordnungen {#file-mappings}

Die folgende Tabelle listet die Schlüssel/Wert-Paare auf, die von den [!UICONTROL Audience Optimization] Berichten verwendete Daten enthalten. Wenn Sie eine Metadatendatei verwenden müssen, enthält sie lesbare Informationen, die den Werten in diesen Schlüssel/Wert-Paaren entsprechen. Die Werte für diese Schlüssel akzeptieren nur Ganzzahlen (Datentyp INT). Hinweis: *Kursiv* zeigt einen Variablenplatzhalter an. Andere Elemente sind Konstanten oder Schlüssel und ändern sich nicht.

>[!IMPORTANT]
>
>Wenn Sie die [!UICONTROL Audience Optimization] Berichte verwenden, *sind* alle diese Werte im Ereignisaufruf erforderlich.

<table id="table_B2C8C493080E449CA71C4EF07D9476BD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Berichtsoption </th> 
   <th colname="col2" class="entry"> Metadaten-Schlüssel-Wert-Paare </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Advertiser </p> </td> 
   <td colname="col2"> <p> <code>d_ adsrc = <i>Datenquellen-ID oder Integrationscode</i></code> </p> <p>Dies ist die Datenquellen-ID oder der Integrationscode des Werbenden, die beim Erstellen einer Datenquelle bereitgestellt werden. Siehe <a href="../../../features/manage-datasources.md#create-data-source"> Erstellen einer Datenquelle</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Geschäftseinheit (BU) </p> </td> 
   <td colname="col2"> <p> <code>d_ bu = <i>Geschäftsentitäts-ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kampagne </p> </td> 
   <td colname="col2"> <p> <code>d_ campaign = <i>Kampagnen-ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kreativ </p> </td> 
   <td colname="col2"> <p> <code>d_ creative = <i>creative id</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exchange- </p> </td> 
   <td colname="col2"> <p>Akzeptiert zwei verschiedene Schlüssel/Wert-Paare: </p> 
    <ul id="ul_3B3B751A8A134096B0912E81A0983B9D"> 
     <li id="li_57BAC45A7B274AB695945E174A4D8A35"> <code>d_ exchange = <i>ID für den Austausch, der die Anzeige diente</i></code> </li> 
     <li id="li_CCDF00DE59D3451C8EF590DD3E1A806D"> <code>d_ site = <i>ID für die Site, auf der eine Anzeige bereitgestellt wird</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Einfügereihenfolge (IO) </p> </td> 
   <td colname="col2"> <p> <code>d_ io = <i>Einfügereibestellungs-ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plattform </p> </td> 
   <td colname="col2"> <p> <code>d_ src = <i>Datenquellen-ID</i></code> </p> <p>Dies ist die <a href="../../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datenquellen</a> -ID für die Plattform, die Metadateninformationen bereitstellt (z. B. DFA, Atlas, GBM, mediamath usw.). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Taktik </p> </td> 
   <td colname="col2"> <p> <code>d_ tactic = <i>taktic id</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vertikal </p> </td> 
   <td colname="col2"> <p> <code>d_ vert = <i>vertikale ID</i></code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## How Event Call IDS Shape File Names, Contents, and Delivery Paths {#how-ids-shape-file-names}

Die von diesen Schlüsselwertpaaren weitergeleiteten IDs helfen dabei, den Metadatendateinamen und dessen Inhalt zu erstellen. Die folgenden Abschnitte und Abbildungen zeigen, wie dies funktioniert. Diese Beispiele erstellen eine Datei, die den Namen eines kreativen Elements in einer Kampagne enthält, aber andere Kombinationen sind möglich.

### Ereignisaufruf

In diesem Beispiel erstellen wir eine Metadatendatei, die kreative Namen in einen [!UICONTROL Audience Optimization] Bericht einbringt. Hierfür müssen wir kreative, Kampagnen- und Datenquellen-IDs aus einem Ereignisaufruf extrahieren.

![](assets/metadata_file_event.png)

### Dateiname

Der Dateiname basiert auf den Kreativen, Kampagnen- und Datenquellen-IDs. Vergleichen Sie in diesem Fall die Unterschiede zwischen den Schlüsselwertdaten in einem Ereignisaufruf und deren Verwendung in einem Dateinamen.

In einem Dateinamen:

* Die Schlüssel der Datenquelle ändern sich `dpid` von `d_src`.

* Die kreativen und Kampagnen-IDs stellen eine Kategorie statt einer tatsächlichen Kennung dar.

![](assets/metadata_file_name.png)

Siehe [Namenskonventionen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md).

### Dateiinhalt

In diesem Beispiel spiegelt der Dateiinhalt die in dem Ereignisaufruf weitergeleiteten kreativen und Kampagnen-IDs wider. Das neue Element hier ist ein lesbarer Name. Nach der Verarbeitung wird der Name in dieser Datei als eine Option im Menü des kreativen Elements eines [!UICONTROL Audience Optimization] Berichts angezeigt.

![](assets/metadata_file_contents.png)

Siehe [Inhaltsformat für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md).

### Dateiauslieferung

Nachdem Sie Daten vergeben und einer Datei Daten hinzugefügt haben, senden Sie sie an einen von [!DNL Audience Manager]Ihnen bereitgestellten Amazon S 3-Speicherordner. Siehe [Bereitstellungsmethoden für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-delivery-methods.md) und [Statusaktualisierungen für Metadatendateien](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md).

>[!MORE_ LIKE_ THIS]
>
>* [Datendateien für Zielgruppenoptimierungsberichte](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md)
>* [Erfassen von Kampagnenklickdaten über Pixelaufrufe](../../../integration/media-data-integration/click-data-pixels.md)
>* [Erfassen von Kampagnenimpressionsdaten über Pixelabrufe](../../../integration/media-data-integration/impression-data-pixels.md)


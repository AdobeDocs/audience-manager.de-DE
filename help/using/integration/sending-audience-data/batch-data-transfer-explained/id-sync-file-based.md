---
description: Beschreibt die erforderlichen Felder, Syntax und Benennungskonventionen für die dateibasierte ID-Synchronisierung. Benennen und organisieren Sie Ihre Dateiinhalte entsprechend den Spezifikationen.
seo-description: Beschreibt die erforderlichen Felder, Syntax und Benennungskonventionen für die dateibasierte ID-Synchronisierung. Benennen und organisieren Sie Ihre Dateiinhalte entsprechend den Spezifikationen.
seo-title: Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien
solution: Audience Manager
title: Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Übertragungen von Inbound-Daten
translation-type: tm+mt
source-git-commit: de1483763998027c4fc7694223c39dd7a37e87ab
workflow-type: tm+mt
source-wordcount: '873'
ht-degree: 6%

---


# Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien {#name-and-content-requirements-for-id-synchronization-files}

Beschreibt die erforderlichen Felder, Syntax und Benennungskonventionen für die dateibasierte ID-Synchronisierung. Benennen und organisieren Sie Ihre Dateiinhalte entsprechend den Spezifikationen.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument Codeelemente und Optionen angeben. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Syntax und Beispiele für Dateinamen {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID-Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>Ein statisches Präfix, das die Datei als ID-Synchronisierungsdatei identifiziert. Verwenden Sie dieses Präfix, wenn Sie Geräte-IDs mit anderen Geräte-IDs oder Kunden-IDs (DPUUIDs) abgleichen.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Ein statisches Präfix, das die Datei als ID-Synchronisierungsdatei für benutzerbasierte Ziele identifiziert. Verwenden Sie dieses Präfix, wenn Sie Kunden-IDs (DPUUIDs) mit Hash-E-Mail-Adressen für volksbasierte Ziele verknüpfen.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>Die Übergeordnet-Datenanbieter-ID ist die übergeordnete ID der DPIDs im Dateinamen. Außerdem entspricht die erste Benutzer-ID in der Datendatei der Übergeordnet-ID. Die nachfolgenden DPIDs sind andere IDs, die zum Übergeordnete gehören. Bei der Synchronisierung werden DPIDs im Dateinamen UUIDs in der Datei zugeordnet.</p> <p>Diese DPID darf nur Geräte-IDs wie AAM UUID, GAID, IDFA usw. enthalten. Es darf keine DPUUIDs enthalten. Dies kann zu einer fehlerhaften Synchronisierung führen.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-IDs. Diese IDs stellen Entitäten oder Datenquellen dar, die mit der Übergeordnet DPID verknüpft sind. Bei der Synchronisierung werden DPIDs im Dateinamen UUIDs in der Datei zugeordnet. </p> <p>Die Anzahl der DPIDs im Dateinamen muss mit der Anzahl der UUIDs in der Datendatei übereinstimmen. Angenommen, Ihr Dateiname enthält eine Übergeordnet-DPID und 3 DPIDs. Ihre Datendatei muss vier entsprechende Spalten von UUIDs enthalten, die wie im Abschnitt Dateiinhalt unten beschrieben formatiert sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UNIX-Zeitstempel in Sekunden. Der Zeitstempel hilft, jeden Dateinamen eindeutig zu machen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Gibt eine normale, vollständige Synchronisierung an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere kleinere Dateien aufteilen. Dadurch wird die Verarbeitungszeit verkürzt. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. Siehe Beispiele für Dateinamen unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gibt an, dass Ihre Datei mit einer optionalen gzip-Komprimierung komprimiert wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiele für Dateinamen

Die folgenden Beispiele zeigen korrekt formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Informationen zur Benennung der ID-Synchronisierungsdatei (c2c-Präfix) für benutzerspezifische Ziele finden Sie unter [Workflow A - Personalisierung auf Basis der gesamten Online-Aktivität kombiniert mit Offline-Daten](../../../features/destinations/people-based-destinations-workflow-combined.md) oder [Workflow B - Personalisierung auf Basis von Offline-Daten](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Syntax und Beispiele für Dateiinhalte {#file-content-syntax}

Der Inhalt einer ID-Datei umfasst die folgenden Elemente:

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

Die Datei enthält Benutzer-IDs ([!DNL UUID]). Trennen Sie die IDs in jeder Zeile durch eine Registerkarte. Das folgende Beispiel zeigt eine korrekt formatierte ID-Datei. Ihr Inhalt könnte ähnlich aussehen.

```
abc123 def456 ghi789 xyz987
```

### Überlegungen zum Dateiinhalt {#considerations}

Stellen Sie beim Erstellen Ihrer eingehenden Dateien sicher, dass die erste Spalte nur mit Geräte-IDs wie [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA] usw. gefüllt wird. Eine ausführliche Erläuterung der von Audience Manager unterstützten IDs finden Sie unter [IDs in Audience Manager](../../../reference/ids-in-aam.md).

>[!IMPORTANT]
>
>Verwenden Sie nicht [DPUUIDs](../../../reference/ids-in-aam.md) in der ersten Spalte. Dies kann zu einer fehlerhaften Synchronisierung führen.

## Synchronisierung stimmt mit DPUUIDs mit UUIDs ab {#sync-matches-dpuuids-uuids}

Der Zweck einer ID-Synchronisierungsdatei besteht darin, die [DPUUIDs](../../../reference/ids-in-aam.md) aus Ihren eigenen Datenquellen mit [!DNL Audience Manager]-UUIDs zu synchronisieren. Die Synchronisierung ordnet die [!DNL DPUUID]s aus dem Übergeordnet [!DNL DPID] und die zugehörigen [!DNL DPID]s den [!DNL Audience Manager] [!DNL UUID]s zu. Wo Sie die IDs in den Dateinamen setzen und der Haupttext bestimmt, wie diese IDs einander zugeordnet werden. Nehmen Sie beispielsweise die beiden folgenden Beispieldateien:

* **Datei 1:** `adobe_id_0_12345_1476312152.sync`

* **Datei 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Bei Verwendung des Beispielnamens und des Beispielinhalts ordnen die IDs wie folgt zusammen:

**Datei 1**  ( [Beispieldatei](assets/adobe_id_0_12345_1476312152.sync) herunterladen)

| DPID 0 = Adobe Audience Manager UUIDs | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 6618477822667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

{style=&quot;table-layout:auto&quot;}

Schritt 1: Der ID-Synchronisierungsprozess synchronisiert die [!DNL DPUUID]s von [!DNL DPID] 12345 mit den [!DNL Audience Manager] [!DNL UUID]s in der linken Spalte. Beachten Sie, dass [!DNL DPID] &quot;0&quot;im Dateinamen [!DNL Audience Manager] [!DNL UUID]s darstellt.
<br/>

**Datei 2**  ( [Beispieldatei](assets/adobe_id_12345_67890_1477846458.sync) herunterladen)

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

{style=&quot;table-layout:auto&quot;}

Schritt 2: die [!DNL DPUUID]s von [!DNL DPID] 12345 wurden in Schritt 1 mit dem Audience Manager [!DNL UUID]s synchronisiert. Diese ID-Synchronisierung synchronisiert die [!DNL DPUUID]s von [!DNL DPID] 67890 mit dem Audience Manager [!DNL UUID]s aus Schritt 1.

<br/>

## Weitere Formatanforderungen {#other-format-reqs}

Benutzer-IDs können nicht:

* Haben Sie Registerkarten in der ID selbst. Tabs werden nur zur Trennung einzelner IDs in der Datendatei verwendet.
* Enthält personenbezogene Daten ([!UICONTROL PII]).
* Verwenden Sie die Kodierung [!DNL URL]. Geben Sie nur nicht kodierte IDs ein.

Zeilen, die mit Tabulatoren oder Leerzeichen enden, werden nicht verarbeitet oder realisiert. Achten Sie in der Regel darauf, das Ende der Zeilen frei zu halten.
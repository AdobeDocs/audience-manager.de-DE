---
description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Benennen und organisieren Sie Ihre Dateiinhalte entsprechend den Spezifikationen.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien
solution: Audience Manager
title: Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
translation-type: tm+mt
source-git-commit: 4bc3d7c0a34619e556f58b39b7812a5612050f7f

---


# Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien {#name-and-content-requirements-for-id-synchronization-files}

Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) in this document indicate code elements and options. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## File Name Syntax and Examples {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID file names contain the following required and optional elements:

*`[adobe_id_]`* _DPID_DPID.gz *`[c2c_id_]`*`MASTERDPID_DPID`*[]*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*[]

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
   <td colname="col2"> <p>A static prefix that identifies the file as an ID synchronization file. Use this prefix when matching device IDs to other device IDs or customer IDs (DPUUIDs).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>A static prefix that identifies the file as an ID synchronization file for People-Based Destinations. Use this prefix when matching customer IDs (DPUUIDs) to hashed email addresses for People-Based Destinations.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> Die Master-Datenanbieter-ID ist die übergeordnete ID der DPIDs im Dateinamen. Außerdem entspricht die erste Benutzer-ID in der Datendatei der Master-ID. Die folgenden DPIDs sind andere IDs, die zum Master gehören. Bei der Synchronisierung werden DPIDs im Dateinamen UUIDs in der Datei zugeordnet. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-IDs. Diese IDs stellen Entitäten oder Datenquellen dar, die mit der Master-DPID verknüpft sind. Bei der Synchronisierung werden DPIDs im Dateinamen UUIDs in der Datei zugeordnet. </p> <p>Die Anzahl der DPIDs im Dateinamen muss mit der Anzahl der UUIDs in der Datendatei übereinstimmen. Angenommen, Ihr Dateiname enthält eine Master-DPID und 3 DPIDs. Ihre Datendatei muss vier entsprechende Spalten von UUIDs enthalten, die wie im Abschnitt Dateiinhalt unten beschrieben formatiert sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UNIX-Zeitstempel in Sekunden. Mit dem Zeitstempel wird jeder Dateiname eindeutig. </p> </td> 
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

The following examples show properly formatted files names. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_145442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Informationen zur Benennung der ID-Synchronisierungsdatei (c2c-Präfix) für benutzerbasierte Ziele finden Sie unter [Workflow A - Personalisierung auf Basis aller Online-Aktivitäten in Kombination mit Offline-Daten](../../../features/destinations/people-based-destinations-workflow-combined.md) oder [Workflow B - Personalisierung auf Basis von Nur-Offline-Daten](../../../features/destinations/people-based-destinations-workflow-offline.md).

## File Content Syntax and Examples {#file-content-syntax}

The contents of an ID file include the following elements:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

The file contains user IDs (). [!DNL UUID] In each row, separate the IDs with a tab. The following example shows a properly formatted ID file. Your contents could look similar.

```
abc123 def456 ghi789 xyz987
```

## Synchronization Matches DPUUIDs to UUIDs {#sync-matches-dpuuids-uuids}

The purpose of an ID sync file is to sync the DPUUIDs from your own Data Sources with  UUIDs. [](../../../reference/ids-in-aam.md)[!DNL Audience Manager] Synchronization maps the s from the master  and its related s to the  s. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. [!DNL DPUUID][!DNL DPID][!DNL DPID][!DNL Audience Manager][!DNL UUID] For example, take the two sample files shown here:

* **File 1:** `adobe_id_0_12345_1476312152.sync`

* **File 2:**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Given the sample name and contents, the IDs map together like this:

**File 1 ( Download sample file)**[](assets/adobe_id_0_12345_1476312152.sync)

| DPID 0 = Adobe Audience Manager UUIDs | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Schritt 1: Der ID-Synchronisierungsprozess synchronisiert die [!DNL DPUUID]s aus [!DNL DPID] 12345 mit den [!DNL Audience Manager] [!DNL UUID]s in der linken Spalte. Beachten Sie, dass die [!DNL DPID] 0 im Dateinamen [!DNL Audience Manager] [!DNL UUID]s darstellt.
<br/>

**Datei 2** ( [Beispieldatei](assets/adobe_id_12345_67890_1477846458.sync)herunterladen)

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Schritt 2: die [!DNL DPUUID]s aus [!DNL DPID] 12345 wurden in Schritt 1 mit den Audience Manager- [!DNL UUID]Dateien synchronisiert. Diese ID-Synchronisierung synchronisiert die [!DNL DPUUID]s aus [!DNL DPID] 67890 mit den Audience Manager- [!DNL UUID]Dateien aus Schritt 1.

<br/>

## Weitere Formatanforderungen {#other-format-reqs}

Benutzer-IDs können nicht:

* Haben Sie Registerkarten in der ID selbst. Tabs werden nur zur Trennung einzelner IDs in der Datendatei verwendet.
* enthält personenbezogene Daten ([!UICONTROL PII]).
* Verwenden Sie die [!DNL URL] Kodierung. Nur nicht kodierte IDs übergeben.

Zeilen, die mit Tabulatoren oder Leerzeichen enden, werden nicht verarbeitet oder realisiert. Achten Sie in der Regel darauf, das Ende der Zeilen frei zu halten.
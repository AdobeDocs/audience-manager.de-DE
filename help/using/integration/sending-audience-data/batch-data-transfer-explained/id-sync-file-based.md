---
description: Beschreibt die erforderlichen Felder, Syntax und Benennungskonventionen, die für die dateibasierte ID-Synchronisierung verwendet werden. Benennen und organisieren Sie Ihren Dateiinhalt gemäß diesen Spezifikationen.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 3%

---

# Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien {#name-and-content-requirements-for-id-synchronization-files}

Beschreibt die erforderlichen Felder, Syntax und Benennungskonventionen, die für die dateibasierte ID-Synchronisierung verwendet werden. Benennen und organisieren Sie Ihren Dateiinhalt gemäß diesen Spezifikationen.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )` usw.) in diesem Dokument Code-Elemente und -Optionen angeben. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

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
   <td colname="col2"> <p>Ein statisches Präfix, das die Datei als ID-Synchronisierungsdatei angibt. Verwenden Sie dieses Präfix bei der Zuordnung von Geräte-IDs zu anderen Geräte-IDs oder Kunden-IDs (DPUUIDs).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Ein statisches Präfix, das die Datei als ID-Synchronisierungsdatei für People-basierte Ziele angibt. Verwenden Sie dieses Präfix bei der Zuordnung von Kunden-IDs (DPUUIDs) zu Hash-E-Mail-Adressen für personenbasierte Ziele.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>Die Master-Datenanbieter-ID ist die übergeordnete ID der DPIDs im Dateinamen. Außerdem entspricht die erste Benutzer-ID in der Datendatei der Master-ID. Die nachfolgenden DPIDs sind andere IDs, die zum Master gehören. Bei der Synchronisierung werden DPIDs im Dateinamen UUIDs in der Datei zugeordnet.</p> <p>Diese DPID darf nur Geräte-IDs wie AAM UUID, GAID, IDFA usw. enthalten. Sie darf keine DPUUIDs enthalten. Dies kann zu einer falschen Synchronisierung führen.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-IDs. Diese IDs stellen Entitäten oder Datenquellen dar, die mit der Master-DPID verknüpft sind. Bei der Synchronisierung werden DPIDs im Dateinamen UUIDs in der Datei zugeordnet. </p> <p>Die Anzahl der DPIDs im Dateinamen muss mit der Anzahl der UUIDs in der Datendatei übereinstimmen. Angenommen, Ihr Dateiname enthält eine Master-DPID und 3 DPIDs. Ihre Datendatei muss 4 entsprechende Spalten von UUIDs enthalten, die wie im Abschnitt Dateiinhalt unten beschrieben formatiert sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UNIX-Zeitstempel in Sekunden. Der Zeitstempel hilft dabei, jeden Dateinamen eindeutig zu machen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Gibt eine normale vollständige Synchronisierung an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere kleinere Dateien aufteilen. Dies trägt zur Verbesserung der Verarbeitungszeiten bei. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. Siehe Beispiele für Dateinamen unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gibt an, dass Ihre Datei mit optionaler gzip-Komprimierung komprimiert ist. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiele für Dateinamen

Die folgenden Beispiele zeigen ordnungsgemäß formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Informationen zur Benennung der ID-Synchronisierungsdatei (c2c-Präfix) für personenbasierte Ziele finden Sie unter [Workflow A - Personalization based on All Online Activity Combined with Offline Data](../../../features/destinations/people-based-destinations-workflow-combined.md) oder [Workflow B - Personalization Based on Offline-Data](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Syntax und Beispiele für Dateiinhalte {#file-content-syntax}

Der Inhalt einer ID-Datei umfasst die folgenden Elemente:

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

Die Datei enthält Benutzer-IDs ([!DNL UUID]). Trennen Sie die IDs in jeder Zeile durch eine Registerkarte. Das folgende Beispiel zeigt eine ordnungsgemäß formatierte ID-Datei. Ihre Inhalte könnten ähnlich aussehen.

```
abc123 def456 ghi789 xyz987
```

### Überlegungen zum Dateiinhalt {#considerations}

Stellen Sie beim Erstellen Ihrer eingehenden Dateien sicher, dass in der ersten Spalte nur Geräte-IDs wie [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA] usw. enthalten sind. Eine ausführliche Erläuterung der vom Audience Manager unterstützten IDs finden Sie unter [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) .

>[!IMPORTANT]
>
>Verwenden Sie nicht [DPUUIDs](../../../reference/ids-in-aam.md) in der ersten Spalte. Dies kann zu einer falschen Synchronisierung führen.

## Synchronisierung stimmt mit DPUUIDs mit UUIDs überein {#sync-matches-dpuuids-uuids}

Eine ID-Synchronisierungsdatei dient der Synchronisierung der [DPUUIDs](../../../reference/ids-in-aam.md) aus Ihren eigenen Data Sources mit [!DNL Audience Manager] UUIDs. Bei der Synchronisierung werden die [!DNL DPUUID]s vom Master [!DNL DPID] und die zugehörigen [!DNL DPID]s den [!DNL Audience Manager] [!DNL UUID]s zugeordnet. Wenn Sie die IDs in den Dateinamen setzen, bestimmt der Hauptteil, wie diese IDs einander zugeordnet werden. Nehmen Sie beispielsweise die beiden folgenden Beispieldateien:

* **Datei 1:** `adobe_id_0_12345_1476312152.sync`

* **Datei 2:** `adobe_id_12345_67890_1476312876.sync`

<br/>

Unter Berücksichtigung des Beispielnamens und der Inhalte ordnen die IDs wie folgt zu:

**Datei 1** ( [Beispieldatei herunterladen](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = Adobe Audience Manager UUIDs | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Schritt 1: Der ID-Synchronisierungsprozess synchronisiert die [!DNL DPUUID]s von [!DNL DPID] 12345 mit den [!DNL Audience Manager] [!DNL UUID]s in der linken Spalte. Beachten Sie, dass die [!DNL DPID] &quot;0&quot;im Dateinamen [!DNL Audience Manager] [!DNL UUID]s darstellt.
<br/>

**Datei 2** ( [Beispieldatei herunterladen](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Schritt 2: Die [!DNL DPUUID]s von [!DNL DPID] 12345 wurden in Schritt 1 mit dem Audience Manager [!DNL UUID]s synchronisiert. Diese ID-Synchronisierung synchronisiert die [!DNL DPUUID]s von [!DNL DPID] 67890 mit dem Audience Manager [!DNL UUID]s aus Schritt 1.

<br/>

## Weitere Formatanforderungen {#other-format-reqs}

Benutzer-IDs können nicht:

* Fügen Sie die Kennung selbst mit Registerkarten hinzu. Registerkarten werden nur zum Trennen einzelner IDs in der Datendatei verwendet.
* Personenbezogene Informationen ([!UICONTROL PII]) enthalten.
* Verwenden Sie die Kodierung [!DNL URL] . Nur nicht kodierte IDs übergeben.

Alle Zeilen, die mit Tabulatoren oder Leerzeichen enden, werden nicht verarbeitet oder realisiert. Achten Sie in der Regel darauf, dass das Ende der Zeilen klar ist.

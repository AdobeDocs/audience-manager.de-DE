---
description: Beschreibt die erforderlichen Felder, Syntax und Benennungskonventionen für die dateibasierte ID-Synchronisierung. Benennen und organisieren Sie Ihren Dateiinhalt gemäß diesen Spezifikationen.
seo-description: Beschreibt die erforderlichen Felder, Syntax und Benennungskonventionen für die dateibasierte ID-Synchronisierung. Benennen und organisieren Sie Ihren Dateiinhalt gemäß diesen Spezifikationen.
seo-title: Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien
solution: Audience Manager
title: Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien
uuid: bfe 42 af 9-9149-4 da 3-830 e-f 227 c 4 e 610 c 2
translation-type: tm+mt
source-git-commit: 5624eac36a7f2b8892136688f89fc22af241fc3a

---


# Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien {#name-and-content-requirements-for-id-synchronization-files}

Beschreibt die erforderlichen Felder, Syntax und Benennungskonventionen für die dateibasierte ID-Synchronisierung. Benennen und organisieren Sie Ihren Dateiinhalt gemäß diesen Spezifikationen.

>[!NOTE]
>
>Die Textstile (`monospaced text`, *kursiv*, Klammern `[ ]` `( )`usw.) In diesem Dokument stehen Codeelemente und -optionen zur Verfügung. Weitere Informationen finden Sie unter [Stilkonventionen für Code und Textelemente](../../../reference/code-style-elements.md).

## Syntax und Beispiele von Dateinamen {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID-Dateinamen enthalten die folgenden erforderlichen und optionalen Elemente:

`adobe_id_`*`[c2c_id_]`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_ id</code> </p> </td> 
   <td colname="col2"> <p>Ein statisches Präfix, das die Datei als ID-Synchronisierungsdatei kennzeichnet. Verwenden Sie dieses Präfix, wenn Geräte-IDs mit anderen Geräte-IDs oder Kunden-IDs (dpuuids) übereinstimmen.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c 2 c_ id</code> </p> </td> 
   <td colname="col2"> <p>Ein statisches Präfix, das die Datei als ID-Synchronisierungsdatei für benutzerbasierte Ziele kennzeichnet. Verwenden Sie dieses Präfix, wenn Kunden-IDs (dpuuids) mit Hash-E-Email-Adressen für benutzerbasierte Ziele übereinstimmen.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> Die Master-Datenanbieter-ID ist die übergeordnete ID der dpids im Dateinamen. Die erste Benutzer-ID in der Datendatei entspricht der Master-ID. Die nachfolgenden dpids sind andere Bezeichner, die zum Master gehören. Die Synchronisierung ordnet dpids in der Datei den uuids zu. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Datenanbieter-IDs. Diese IDs stellen Entitäten oder Datenquellen dar, die mit der Master-DPID verknüpft sind. Die Synchronisierung ordnet dpids in der Datei den uuids zu. </p> <p>Die Anzahl der dpids im Dateinamen muss mit der Anzahl der uuids in der Datendatei übereinstimmen. Angenommen, Ihr Dateiname enthält eine Master-DPID und 3 dpids. Ihre Datendatei muss vier entsprechende Spalten von uuids enthalten, die wie im Abschnitt Dateiinhalt unten beschrieben formatiert sind. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Ein 10-stelliger UNIX-Zeitstempel in Sekunden. Der Zeitstempel trägt dazu bei, jeden Dateinamen eindeutig zu machen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> . sync</code> </p> </td> 
   <td colname="col2"> <p>Gibt eine normale vollständige Synchronisierung an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>. SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Eine Ganzzahl. Wird verwendet, wenn Sie große Dateien in mehrere kleinere Dateien aufteilen. Dies hilft bei der Verbesserung der Verarbeitungszeiten. Die Zahl gibt an, welcher Teil der Originaldatei Sie senden. Siehe Beispiele für Dateinamen unten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Legt fest, dass die Datei mit optionaler GZIP-Komprimierung komprimiert wird. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiele für Dateiname

Die folgenden Beispiele zeigen ordnungsgemäß formatierte Dateinamen. Ihre Dateinamen könnten ähnlich aussehen.

<ul class="simplelist"> 
 <li> <code> adobe_ id_ 111_ 222_ 333_ 444_ 1454442149. sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Informationen zur Benennung von ID-Synchronisierungsdateien (c 2 c-Präfix) für benutzerbasierte Ziele finden Sie unter [Workflow A - Personalisierung basierend auf allen Online-Aktivitäten, kombiniert mit Offline-Daten](../../../features/destinations/people-based-destinations-workflow-combined.md) oder [Arbeitsabläufen B - Personalisierung basierend auf Offline-Daten](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Syntax und Beispiele von Dateiinhalten {#file-content-syntax}

Der Inhalt einer ID-Datei enthält die folgenden Elemente:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

Die Datei enthält Benutzer-IDs ([!DNL UUID]). Trennen Sie die IDs in jeder Zeile mit einer Registerkarte. Das folgende Beispiel zeigt eine ordnungsgemäß formatierte ID-Datei. Ihr Inhalt könnte ähnlich aussehen.

```
abc123 def456 ghi789 xyz987
```

## Synchronisierung stimmt mit dpuuids zu uuids überein {#sync-matches-dpuuids-uuids}

Der Zweck einer ID-Synchronisierungsdatei besteht darin, die [dpuuids](../../../reference/ids-in-aam.md) aus Ihren eigenen Datenquellen mit [!DNL Audience Manager] uuids zu synchronisieren. Die Synchronisierung ordnet die [!DNL DPUUID]s dem Master [!DNL DPID] und den zugehörigen s [!DNL DPID]den [!DNL Audience Manager][!DNL UUID]s zu. Wenn Sie die IDs in den Dateinamen und den Haupttext setzen, bestimmt dies, wie diese ids zueinander zugeordnet werden. Nehmen Sie beispielsweise die beiden folgenden Beispieldateien vor:

* **Datei 1:**`adobe_id_0_12345_1476312152.sync`

* **Datei 2:**`adobe_id_12345_67890_1476312876.sync`

<br/>

Anhand des Beispielnamens und Inhalts werden die IDs wie folgt zugeordnet:

**Datei 1** (Beispieldatei [herunterladen](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = Adobe Audience Manager uuids | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 |
| 67412682083411995725538770443620307584 | XYZ 3017 BBR 4 dafjwfm 6 D 4 Gb 4 lN_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 |
| 89159024796760343733111707646026765593 | XYZ 3017 prypid 8 tzfhkee-GE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm |
| 66552757407517449462805881945288602094 | XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 M |
| 66184778222667870903738139438735041506 | XYZ 3017 q 9 r 60 kuhpoca_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw |

Schritt 1: der ID-Synchronisierungsprozess synchronisiert die [!DNL DPUUID]s von [!DNL DPID] 12345 mit den [!DNL Audience Manager][!DNL UUID]s in der linken Spalte. Beachten Sie, dass der [!DNL DPID] Dateiname "0" im [!DNL Audience Manager][!DNL UUID]Dateinamen steht.<br/>


**Datei 2** (Beispieldatei [herunterladen](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 | 4598060374 |
| XYZ 3017 BBR 4 dafjwfm 6 D 4 Gb 4 lN_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 | 4581274262 |
| XYZ 3017 prypid 8 tzfhkee-GE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm | 4392434426 |
| XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 M | 2351382994 |
| XYZ 3017 q 9 r 60 kuhpoca_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw | 4601584763 |

Schritt 2: die [!DNL DPUUID]s von [!DNL DPID] 12345 in Schritt 1 mit Audience Manager [!DNL UUID]synchronisiert wurden. Was diese ID synchronisiert, wird die s [!DNL DPUUID]von 67890 [!DNL DPID] mit dem Audience Manager [!DNL UUID]aus Schritt 1 synchronisieren.

<br/>

## Andere Formatanforderungen {#other-format-reqs}

Benutzer-IDs können nicht:

* Weisen Sie Registerkarten in der ID selbst zu. Registerkarten werden nur verwendet, um einzelne IDs in der Datendatei zu trennen.
* Persönliche Informationen enthalten ([!UICONTROL PII]).
* Verwenden [!DNL URL] Sie die Kodierung. Geben Sie nur nicht kodierte IDs an.

Alle Zeilen, die mit Tabulatoren oder Leerzeichen enden, werden nicht verarbeitet oder umgewandelt. Stellen Sie sicher, dass das Ende der Zeilen unverändert bleibt.
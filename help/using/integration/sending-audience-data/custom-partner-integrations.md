---
description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-title: Benutzerspezifische Partnerintegrationen
solution: Audience Manager
title: Benutzerspezifische Partnerintegrationen
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.

## Oracle Data Cloud {#oracle-data-cloud}

**Beschreibung**

Audience Manager übernimmt mithilfe von eingehenden Datendateien Cookie-Daten und mobile IDs aus der Oracle Data Cloud für Audience Marketplace. Die unten beschriebenen benutzerdefinierten Integrationsspezifikationen beziehen sich nur auf eingehende Datendateien mit mobilen IDs (IDFA- und Android-Geräte-IDs).

<br> 

**Integrationsdetails**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Die unten hervorgehobenen Elemente sind zusätzlich zu den Standard-Implementierungsfeldern für eingehende Datendateien erforderlich. Beschreibungen aller anderen Standardfelder und Dateinamenelemente finden Sie unter Dateinamensyntax und Dateiinhaltssyntax in den beiden oben verknüpften Seiten.

<br> 

**Dateibenennung**

ODC-Dateinamen sind strukturiert:

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

The `odc` file name element identifies the file as being imported from the Oracle Data Cloud and instructs the Audience Manager inbound file validator to process it as such.

<br> 

**Dateiinhalt**

Felder in der ODC-eingehenden Datendatei müssen in der unten stehenden Reihenfolge angezeigt werden:

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

The `ID type` can be:

* IDFA
* Android-Geräte-ID

>[!IMPORTANT]
>
>Senden Sie IDFA- und Android-Geräte-IDs nicht in derselben Inbound-Datendatei.

<br> 

**Beispiel für ODC-Inbound-Datei**

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Diese Datei qualifiziert mehrere idfas für die Merkmal-ID 38838. Sie können diese Datei in einem Standardtexteditor oder Code-Editor öffnen.
---
description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-title: Benutzerdefinierte Partnerintegrationen
solution: Audience Manager
title: Benutzerdefinierte Partnerintegrationen
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Benutzerdefinierte Partnerintegrationen {#custom-partner-integrations}

Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.

## Oracle Data Cloud {#oracle-data-cloud}

**Beschreibung**

Audience Manager übernimmt mithilfe von eingehenden Datendateien Cookie-Daten und mobile IDs aus der Oracle Data Cloud für Audience Marketplace. Die unten beschriebenen benutzerdefinierten Integrationsspezifikationen beziehen sich nur auf eingehende Datendateien mit mobilen IDs (IDFA- und Android-Geräte-IDs).

<br> 

**Integrationsspezifikationen**

Von der Oracle Data Cloud empfangene Inbound-Datendateien unterscheiden sich von der in [Amazon S3-Anforderungen an Name und Dateigröße für Inbound-Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) beschriebenen Standardsyntax für den Inbound-Dateiinhalt und von der in [Inbound-Datendateiinhalt beschriebenen Syntax: Syntax, ungültige Zeichen, Variablen und Beispiele](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Die unten hervorgehobenen Elemente sind zusätzlich zu den standardmäßigen Implementierungsfeldern für eingehende Datendateien erforderlich. Beschreibungen aller anderen Standardfelder und Dateinamenelemente finden Sie unter Syntax für Dateinamen und Syntax für Dateiinhalte auf den beiden oben verknüpften Seiten.

<br> 

**Dateibenennung**

ODC-Dateinamen sind wie folgt strukturiert:

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

Das `odc` Dateinamenelement identifiziert die Datei als aus der Oracle Data Cloud importiert und weist den Audience Manager-Validator an, sie als solche zu verarbeiten.

<br> 

**Dateiinhalt**

Die Felder in der ODC-Eingangsdatendatei müssen in der folgenden Reihenfolge angezeigt werden:

<pre>&lt;<b>ID-Typ</b>&gt;&lt;TAB&gt;&lt;Benutzer-ID&gt;&lt;TAB&gt;&lt;Eigenschaften-ID&gt;,&lt;Eigenschaften-ID&gt;,&lt;Eigenschaften-ID&gt;,...</pre>

Die `ID type` können sein:

* IDFA
* Android-Geräte-ID

>[!IMPORTANT]
>
>Senden Sie keine IDFA- und Android-Geräte-IDs in derselben eingehenden Datendatei.

<br> 

**ODC-Eingangsdatei**

Laden Sie die [Beispieldatei](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)herunter. Diese Datei qualifiziert mehrere IDFAs für die Eigenschaften-ID 38838. Sie können diese Datei in einem Standard-Texteditor oder Codeeditor öffnen.
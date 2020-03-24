---
description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-title: Benutzerdefinierte Partnerintegrationen
solution: Audience Manager
title: Benutzerdefinierte Partnerintegrationen
translation-type: tm+mt
source-git-commit: c069c901df6d8737f611d27ce7dffd4072e50adf

---


# Benutzerdefinierte Partnerintegrationen {#custom-partner-integrations}

Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.

## Oracle Data Cloud {#oracle-data-cloud}

### Beschreibung

Audience Manager übernimmt mithilfe von eingehenden Datendateien Cookie-Daten und mobile IDs aus der Oracle Data Cloud für Audience Marketplace. Die unten beschriebenen benutzerdefinierten Integrationsspezifikationen beziehen sich nur auf eingehende Datendateien mit mobilen IDs (IDFA- und Android-Geräte-IDs).

### Integrationsspezifikationen

Von der Oracle Data Cloud empfangene Inbound-Datendateien unterscheiden sich von der in [Amazon S3-Anforderungen an Name und Dateigröße für Inbound-Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) beschriebenen Standardsyntax für den Inbound-Dateiinhalt und von der in [Inbound-Datendateiinhalt beschriebenen Syntax: Syntax, ungültige Zeichen, Variablen und Beispiele](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Die unten hervorgehobenen Elemente sind zusätzlich zu den standardmäßigen Implementierungsfeldern für eingehende Datendateien erforderlich. Beschreibungen aller anderen Standardfelder und Dateinamenelemente finden Sie unter Syntax für Dateinamen und Syntax für Dateiinhalte auf den beiden oben verknüpften Seiten.

### Dateibenennung

ODC-Dateinamen sind wie folgt strukturiert:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Das `odc` Dateinamenelement identifiziert die Datei als aus der Oracle Data Cloud importiert und weist den Audience Manager-Validator an, sie als solche zu verarbeiten.

### Dateiinhalt

Die Felder in der ODC-Eingangsdatendatei müssen in der folgenden Reihenfolge angezeigt werden:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

Die `ID type` können sein:

* IDFA
* Android-Geräte-ID

>[!IMPORTANT]
>
>Senden Sie keine IDFA- und Android-Geräte-IDs in derselben eingehenden Datendatei.

## ODC-Eingangsdatei

Laden Sie die [Beispieldatei](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)herunter. Diese Datei qualifiziert mehrere IDFAs für die Eigenschaften-ID 38838. Sie können diese Datei in einem Standard-Texteditor oder Codeeditor öffnen.
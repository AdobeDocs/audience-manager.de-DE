---
description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-title: Benutzerdefinierte Partnerintegrationen
solution: Audience Manager
title: Benutzerdefinierte Partnerintegrationen
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 22%

---


# Benutzerdefinierte Partnerintegrationen {#custom-partner-integrations}

Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.

## Oracle Data Cloud {#oracle-data-cloud}

### Beschreibung

Audience Manager übernimmt mithilfe von eingehenden Datendateien Cookie-Daten und mobile IDs aus der Oracle Data Cloud für Audience Marketplace. Die unten beschriebenen benutzerdefinierten Integrationsspezifikationen beziehen sich nur auf eingehende Datendateien mit mobilen IDs (IDFA- und Android-Geräte-IDs).

### Integrationsspezifikationen

Die von der Oracle Data Cloud empfangenen Inbound-Datendateien unterscheiden sich von der Standardsyntax für eingehende Datendateien, die unter [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) beschrieben wird, und von der Standardsyntax für den Inbound-Dateiinhalt, die unter [Inbound Data File Contents beschrieben wird: Syntax, Ungültige Zeichen, Variablen und Beispiele](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Die unten hervorgehobenen Elemente sind zusätzlich zu den standardmäßigen Implementierungsfeldern für eingehende Datendateien erforderlich. Beschreibungen aller anderen Standardfelder und Dateinamenelemente finden Sie unter Syntax für Dateinamen und Syntax für Dateiinhalte auf den beiden oben verknüpften Seiten.

### Dateibenennung

ODC-Dateinamen sind wie folgt strukturiert:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Das `odc`-Dateinamenelement identifiziert die Datei als aus der Oracle Data Cloud importiert und weist den Audience Manager-Validator an, sie als solche zu verarbeiten.

### Dateiinhalt

Die Felder in der ODC-Eingangsdatendatei müssen in der folgenden Reihenfolge angezeigt werden:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

Das `ID type` kann:

* IDFA
* Android-Geräte-ID

>[!IMPORTANT]
>
>Senden Sie keine IDFA- und Android-Geräte-IDs in derselben eingehenden Datendatei.

## ODC-Eingangsdatei

Laden Sie die Beispieldatei [a1/> herunter. ](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync) Diese Datei qualifiziert mehrere IDFAs für die Eigenschaften-ID 38838. Sie können diese Datei in einem Standard-Texteditor oder Codeeditor öffnen.
---
description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Benutzerdefinierte Partnerintegrationen
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 15%

---

# Benutzerdefinierte Partnerintegrationen {#custom-partner-integrations}

Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.

## Oracle Data Cloud {#oracle-data-cloud}

### Beschreibung

Audience Manager übernimmt mithilfe von eingehenden Datendateien Cookie-Daten und mobile IDs aus der Oracle Data Cloud für Audience Marketplace. Die unten beschriebenen benutzerdefinierten Integrationsspezifikationen beziehen sich nur auf eingehende Datendateien, die mobile IDs (IDFA- und Android-Geräte-IDs) enthalten.

### Besonderheiten der Integration

Eingehende Datendateien, die von Oracle Data Cloud empfangen werden, unterscheiden sich von der standardmäßigen Namenssyntax für eingehende Dateien, die unter [Amazon S3-Namens- und Dateigrößenanforderungen für eingehende Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) beschrieben ist, und von der standardmäßigen Inhaltssyntax für eingehende Dateien, die unter [Inhalte eingehender Datendateien: Syntax, ungültige Zeichen, Variablen und Beispiele](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) beschrieben ist.

Die unten hervorgehobenen Elemente sind zusätzlich zu den Standardimplementierungsfeldern für eingehende Datendateien erforderlich. Beschreibungen aller anderen Standardfelder und Dateinamenelemente finden Sie unter Dateinamensyntax und Dateiinhaltssyntax auf den beiden oben verlinkten Seiten.

### Benennung der Datei

ODC-Dateinamen sind wie folgt strukturiert:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Das `odc` Dateinamenelement identifiziert die Datei als aus der Oracle Data Cloud importiert und weist den Audience Manager-Validator für eingehende Dateien an, sie als solche zu verarbeiten.

### Dateiinhalte

Die Felder in der eingehenden ODC-Datendatei müssen in der unten angegebenen Reihenfolge angezeigt werden:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

Die `ID type` kann sein:

* IDFA
* Android-Geräte-ID

>[!IMPORTANT]
>
>Senden Sie keine IDFA- und Android-Geräte-IDs in derselben eingehenden Datendatei.

## Beispiel für ODC-Eingangsdatei

Laden Sie die [Beispieldatei) &#x200B;](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Diese Datei qualifiziert mehrere IDFAs für die Eigenschaft-ID 38838. Sie können diese Datei in einem standardmäßigen Texteditor oder Codeeditor öffnen.

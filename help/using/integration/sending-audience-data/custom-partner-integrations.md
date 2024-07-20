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

Audience Manager übernimmt mithilfe von eingehenden Datendateien Cookie-Daten und mobile IDs aus der Oracle Data Cloud für Audience Marketplace. Die unten beschriebenen benutzerdefinierten Integrationsspezifikationen beziehen sich nur auf eingehende Datendateien, die mobile IDs (IDFA und Android-Geräte-IDs) enthalten.

### Integrationsspezifikationen

Die von der Oracle Data Cloud empfangenen eingehenden Datendateien unterscheiden sich von der in [Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Dateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) beschriebenen Syntax für den Standardnamen der eingehenden Datei und von der in [Inhalt der eingehenden Datendatei: Syntax, ungültige Zeichen, Variablen und Beispiele](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) beschriebenen Syntax für den Standardinhalt der eingehenden Datei.

Zusätzlich zu den standardmäßigen Implementierungsfeldern für eingehende Datendateien sind die unten hervorgehobenen Elemente erforderlich. Beschreibungen aller anderen Standardfelder und Dateinamenelemente finden Sie unter Syntax für Dateinamen und Syntax des Dateiinhalts auf den beiden oben verlinkten Seiten.

### Dateibenennung

ODC-Dateinamen sind wie folgt strukturiert:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Das Dateinamenelement `odc` identifiziert die aus der Oracle Data Cloud importierte Datei und weist den Audience Manager-Validator an, sie als solche zu verarbeiten.

### Dateiinhalt

Die Felder in der eingehenden ODC-Datendatei müssen in der folgenden Reihenfolge angezeigt werden:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

Der `ID type` kann sein:

* IDFA
* Android-Geräte-ID

>[!IMPORTANT]
>
>Senden Sie keine IDFA- und Android-Geräte-IDs in derselben eingehenden Datendatei.

## ODC-Eingehende Beispieldatei

Laden Sie die [Beispieldatei](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync) herunter. Diese Datei qualifiziert mehrere IDFAs für die Eigenschaften-ID 38838. Sie können diese Datei in einem standardmäßigen Texteditor oder Code-Editor öffnen.

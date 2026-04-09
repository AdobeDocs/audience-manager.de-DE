---
description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Benutzerdefinierte Partnerintegrationen
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
TQID: https://experienceleague.adobe.com/0QvyTQOmjkES1ZO47uu7JTh07-5--uHIgCbJ9iAYfrE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: d8f86c1e-15ad-457f-9d6f-5e756573fad4
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 271
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

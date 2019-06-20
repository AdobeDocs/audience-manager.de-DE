---
description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-description: Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.
seo-title: Benutzerspezifische Partnerintegrationen
solution: Audience Manager
title: Benutzerspezifische Partnerintegrationen
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Benutzerspezifische Partnerintegrationen {#custom-partner-integrations}

Diese Seite enthält benutzerdefinierte Integrationen zwischen Audience Manager und Datenpartnern.

## Oracle Data Cloud {#oracle-data-cloud}

**Beschreibung**

Audience Manager übernimmt mithilfe von eingehenden Datendateien Cookie-Daten und mobile IDs aus der Oracle Data Cloud für Audience Marketplace. Die unten beschriebenen benutzerdefinierten Integrationsspezifikationen beziehen sich nur auf eingehende Datendateien mit mobilen IDs (IDFA- und Android-Geräte-IDs).

<br> 

**Integrationsdetails**

Von der Oracle Data Cloud empfangene Inbound-Datendateien unterscheiden sich von der standardsyntax für eingehende Inbound File-Dateien, die in [den Amazon S 3-Namen und den Dateigrößenanforderungen für eingehende Datendateien](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) beschrieben werden, sowie von der standardsyntax für eingehende Inbound-Dateidateien, die in [Inbound Data File Contents beschrieben werden: Syntax, Ungültige Zeichen, Variablen und Beispiele](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Die unten hervorgehobenen Elemente sind zusätzlich zu den Standard-Implementierungsfeldern für eingehende Datendateien erforderlich. Beschreibungen aller anderen Standardfelder und Dateinamenelemente finden Sie unter Dateinamensyntax und Dateiinhaltssyntax in den beiden oben verknüpften Seiten.

<br> 

**Dateibenennung**

ODC-Dateinamen sind strukturiert:

<pre>ftp_ dpm_<b>odc</b>_ DPID [_ DPID_ TARGET_ DATA_ OWNER]_ TIMESTAMP (. sync |. overwrite) [. SPLIT_ NUMBER] [.gz]</pre>

Das `odc` Dateinamenelement identifiziert die Datei als importierte Datei aus der Oracle Data Cloud und weist den Validator des Audience Manager an, sie als solche zu verarbeiten.

<br> 

**Dateiinhalt**

Felder in der ODC-eingehenden Datendatei müssen in der unten stehenden Reihenfolge angezeigt werden:

<pre>&lt;<b>ID-Typ</b>&gt; &lt; TAB &gt; &lt; Benutzer-ID &gt; &lt; TAB &gt; &lt; Merkmal-ID &gt;, &lt; Merkmal-ID &gt;, &lt; Merkmal-ID &gt;,…</pre>

Das `ID type` kann sein:

* IDFA
* Android-Geräte-ID

>[!IMPORTANT]
>
>Senden Sie IDFA- und Android-Geräte-IDs nicht in derselben Inbound-Datendatei.

<br> 

**Beispiel für ODC-Inbound-Datei**

Laden Sie die [Beispieldatei herunter](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Diese Datei qualifiziert mehrere idfas für die Merkmal-ID 38838. Sie können diese Datei in einem Standardtexteditor oder Code-Editor öffnen.
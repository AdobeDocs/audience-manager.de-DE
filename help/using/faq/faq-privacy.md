---
description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-title: Häufig gestellte Fragen zum Datenschutz und zur Datenaufbewahrung
solution: Audience Manager
title: Häufig gestellte Fragen zum Datenschutz und zur Datenaufbewahrung
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 3a4f23bc853a2324a4c91c6e65b14455293a5b1b

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.

<!-- faq_privacy.xml -->

##  Datenschutz FAQ {#privacy-faq}

>[!TIP]
>
>Weitere Informationen finden Sie im [Adobe Privacy Center](https://www.adobe.com/privacy.html) .

**Wie verwendet Audience Manager Cookies und welche Cookies werden gesetzt?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**Können Audience Manager-Kunden in den USA Benutzer auf EU-Eigenschaften ausrichten?**

Ja. Audience Manager arbeitet mit Kunden mit internationalen Eigenschaften und Beständen. Die EU hat strenge Datenschutzvorschriften, aber Audience Manager verfügt über Kunden, die Erstanbieter-Daten für Zielgruppen-Targeting in Europa verwenden. Audience Manager kann das Targeting für EU-Zielgruppen unterstützen, aber es liegt in Ihrer Verantwortung, die lokalen Datenschutzbestimmungen einzuhalten.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Häufig gestellte Fragen zur Datenaufbewahrung {#data-retention-faq}

In der folgenden Tabelle sind die Aufbewahrungszeiten für verschiedene Datentypen und Speichersysteme aufgeführt.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datentyp, Quelle oder Speicher </th> 
   <th colname="col2" class="entry"> Datenaufbewahrungsdauer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Back-End-Server </p> </td> 
   <td colname="col2"> <p>120-days. </p> <p> Audience Manager löscht Benutzerdaten von unseren Back-End-Servern 120 Tage nach der letzten Anzeige eines Benutzers auf der Audience Manager-Plattform. Wenn <span class="keyword"> Audience Manager</span> die Benutzeraktivität innerhalb dieses 120-Tage-Zyklus aufzeichnet, behalten wir diese Daten weitere 120 Tage bei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-Server </p> </td> 
   <td colname="col2"> <p> 14-days. </p> <p>Audience Manager löscht Benutzerdaten von unseren Edge-Servern 14 Tage nach der letzten Anzeige eines Benutzers auf der Audience Manager-Plattform. Wenn <span class="keyword"> Audience Manager</span> die Benutzeraktivität innerhalb dieses 14-Tage-Zyklus aufzeichnet, behalten wir diese Daten weitere 14 Tage bei. If the user becomes active again after the 14-day period, there will be a delay between that first new page view and when the user becomes actionable. It takes 6-18 hours to get the full profile back out to the edge center after more than 14-days of inactivity. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Raw logs </p> </td> 
   <td colname="col2"> <p>180-days (removed after 180-days of no activity). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server Logs </p> </td> 
   <td colname="col2"> <p><b>Berichterstellung</b> </p> <p>Log files are retained for reporting purposes for up to 30 days. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and  Audience Manager ID) in our backend storage, and matched logs stored in  Amazon S3 are retained for up to 30 days.<span class="keyword"></span><span class="keyword"></span> </p> <p><b>Actionable Log Files</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-level profiles (authenticated profiles) </p> </td> 
   <td colname="col2"> <p>The default time-to-live (TTL) interval for inactive CRM-level profiles (Customer IDs) is 24 months. However, you can use the Audience Manager UI to reduce or extend the TTL interval for inactive CRM-level profiles between one month and 5 years. You can accomplish this when creating or editing a Cross-Device data source.</p> <p>For more information, see Data Source Settings in  Create a Cross-Device Data Source .<a href="../features/profile-merge-rules/merge-rules-start.md#settings"></a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>Die Aufbewahrungsbedingungen für Mobilgeräte-IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) folgen der in den ersten beiden Zeilen beschriebenen Kadenz: Back-End-Server und Edge-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kundendaten-Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>Eine CDF-Datei enthält dieselben Daten, die ein <span class="keyword"> Audience Manager</span> -Ereignisaufruf (/event) an unsere Server sendet. Die Retentionszeit beträgt 8 Tage. Weitere Informationen zu CDF finden Sie in den häufig gestellten Fragen zu <a href="../features/cdf-files.md"> CDF Intro</a> und <a href="../faq/faq-cdf.md"> CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zuordnungen zwischen synchronisierten IDs </p> </td> 
   <td colname="col2"> <p>Die Lebensdauer der <a href="../features/administration/usage-limits.md#id-mapping-limits"> ID-Zuordnungen</a> zwischen Cookie-IDs von Audience Manager (Unique User IDs von<a href="../reference/ids-in-aam.md">Audience Manager oder AAM UUIDs</a>) und Cookie-IDs von Drittanbietern ist auf 120 Tage beschränkt. Die Lebensdauer der ID-Zuordnung wird jedes Mal zurückgesetzt, wenn das Audience Manager-Cookie im Audience Manager-Netzwerk angezeigt wird. Die letzte Synchronisierung der ID-Zuordnung bleibt während der gesamten Dauer der zugehörigen Unique User ID (AAM UUID)<a href="../reference/ids-in-aam.md">für </a>Audience Manager erhalten.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inbound-Daten </p> </td> 
   <td colname="col2"> <p>Dies sind eingehende Daten, die Sie per FTP an <span class="keyword"> Audience Manager</span> oder direkt an einen <span class="keyword"> Amazon S3</span> -Ordner senden. Siehe <a href="../faq/faq-inbound-data-ingestion.md"> Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgehende Daten </p> </td> 
   <td colname="col2"> <p>Dies sind die Stapeldaten, die <span class="keyword"> Audience Manager</span> an Aktivierungspartner von Drittanbietern sendet. Die Retentionszeit beträgt 8 Tage. Weitere Informationen zu ausgehenden Daten finden Sie unter <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Ausgehende Batch-Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datenaufbewahrung zur Eigenschaftsqualifikation {#trait-qual}

Die nachstehende Tabelle listet die Optionen zur Aufbewahrung von Eigenschaftsqualifikationen auf.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Eigenschaftsvorgang </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eine Eigenschaft löschen </p> </td> 
   <td colname="col2"> <p>Beim Löschen einer Eigenschaft werden die Daten zur Eigenschaftenqualifikation aus allen Benutzerprofilen entfernt, die sich in der Vergangenheit für die Eigenschaft qualifiziert hatten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zeichenbeschränkung erreicht </p> </td> 
   <td colname="col2"> <p>Für jedes Benutzerprofil gilt eine Beschränkung von 100.000 Eigenschaftsqualifikationen. Die Beschränkung gilt für authentifizierte Profile und Geräteprofile. Wenn ein Benutzerprofil diese Grenze erreicht, werden die ältesten Eigenschaftsqualifikationen auf der Basis des Erststarts gelöscht. </p> <p>Weitere Informationen finden Sie in unserem <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Qualifikationslimit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


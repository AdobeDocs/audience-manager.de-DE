---
description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-title: Häufig gestellte Fragen zum Datenschutz und zur Datenaufbewahrung
solution: Audience Manager
title: Häufig gestellte Fragen zum Datenschutz und zur Datenaufbewahrung
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.

<!-- faq_privacy.xml -->

## Datenschutz FAQ {#privacy-faq}

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
   <td colname="col2"> <p>120 Tage. </p> <p> Audience Manager löscht Benutzerdaten von unseren Back-End-Servern 120 Tage nach der letzten Anzeige eines Benutzers auf der Audience Manager-Plattform. Wenn <span class="keyword"> Audience Manager</span> die Benutzeraktivität innerhalb dieses 120-Tage-Zyklus aufzeichnet, behalten wir diese Daten weitere 120 Tage bei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-Server </p> </td> 
   <td colname="col2"> <p> 14 Tage. </p> <p>Audience Manager löscht Benutzerdaten von unseren Edge-Servern 14 Tage nach der letzten Anzeige eines Benutzers auf der Audience Manager-Plattform. Wenn <span class="keyword"> Audience Manager</span> die Benutzeraktivität innerhalb dieses 14-Tage-Zyklus aufzeichnet, behalten wir diese Daten weitere 14 Tage bei. Wenn der Benutzer nach dem 14-Tage-Zeitraum wieder aktiv wird, kommt es zu einer Verzögerung zwischen dieser ersten neuen Seitenansicht und dem Zeitpunkt, zu dem der Benutzer handlungsfähig wird. Nach mehr als 14 Tagen Inaktivität dauert es 6-18 Stunden, bis das gesamte Profil wieder in die Edge-Mitte gebracht wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rohprotokolle </p> </td> 
   <td colname="col2"> <p>180 Tage (nach 180 Tagen ohne Aktivität entfernt). </p> <p>Rohprotokolle sind Daten, die von einem Edge-Server über HTTP-Aufrufe oder von an <span class="keyword"> Audience Manager</span>gesendeten Dateien empfangen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzeigenserver-Protokolle </p> </td> 
   <td colname="col2"> <p><b>Berichterstellung</b> </p> <p>Protokolldateien werden bis zu 30 Tage für die Berichterstellung gespeichert. Wir bestehen nicht übereinstimmende Protokolle (d. h. Protokolle, für die keine ID-Synchronisierung zwischen der Anzeigen-Server-ID eines Besuchers und der <span class="keyword"> Audience Manager</span> -ID besteht) in unserem Backend-Speicher, und in <span class="keyword"> Amazon S3</span> gespeicherte übereinstimmende Protokolle werden bis zu 30 Tage lang aufbewahrt. </p> <p><b>Actionable Log Files</b> </p> <p>Sowohl übereinstimmende als auch nicht übereinstimmende Protokolle werden bis zu 30 Tage lang aufbewahrt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profile auf CRM-Ebene (authentifizierte Profile) </p> </td> 
   <td colname="col2"> <p>Das Standardintervall für die Time-to-live (TTL) für inaktive CRM-Profile (Kunden-IDs) beträgt 24 Monate. Sie können jedoch die Benutzeroberfläche von Audience Manager verwenden, um das TTL-Intervall für inaktive CRM-Profile zwischen einem Monat und fünf Jahren zu reduzieren oder zu verlängern. Dies ist beim Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle möglich.</p> <p>Weitere Informationen finden Sie unter Datenquelleneinstellungen in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Erstellen einer geräteübergreifenden Datenquelle </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgerät-IDs </p> </td> 
   <td colname="col2"> <p>Die Aufbewahrungsbedingungen für Mobilgeräte-IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) folgen der in den ersten beiden Zeilen beschriebenen Kadenz: Back-End-Server und Edge-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kundendaten-Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>Eine CDF-Datei enthält dieselben Daten, die ein <span class="keyword"> Audience Manager</span> -Ereignisaufruf (/event) an unsere Server sendet. Die Retentionszeit beträgt 8 Tage. Weitere Informationen zu CDF finden Sie in den häufig gestellten Fragen zu <a href="../features/cdf-files.md"> CDF Intro</a> und <a href="../faq/faq-cdf.md"> CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zuordnungen zwischen synchronisierten IDs </p> </td> 
   <td colname="col2"> <p>Zuordnungen zwischen synchronisierten IDs können während der gesamten Dauer der zugehörigen Unique User ID (AAM UUID)<a href="../reference/ids-in-aam.md">für </a> Audience Manager beibehalten werden. </p> </td> 
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


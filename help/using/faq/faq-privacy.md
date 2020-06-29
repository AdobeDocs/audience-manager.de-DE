---
description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-title: Häufig gestellte Fragen zum Datenschutz und zur Datenaufbewahrung
solution: Audience Manager
title: Häufig gestellte Fragen zum Datenschutz und zur Datenaufbewahrung
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 5%

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.

<!-- faq_privacy.xml -->

## Datenschutz FAQ {#privacy-faq}

>[!TIP]
>
>Weitere Informationen finden Sie im [Adobe Privacy Center](https://www.adobe.com/privacy.html) .

**Wie verwendet der Audience Manager Cookies und welche Cookies setzt er?**

See [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html).

**Können Audience Manager in der US-Zielgruppe auf EU-Immobilien zugreifen?**

Ja. Audience Manager arbeitet mit Kunden, die über internationale Immobilien und Lagerbestände verfügen. Die EU hat strenge Datenschutzvorschriften, aber Audience Manager hat Kunden, die Erstanbieter-Daten für das Targeting von Audiencen in Europa verwenden. Audience Manager können das Targeting auf EU-Audiencen unterstützen, aber es liegt in Ihrer Verantwortung, die lokalen Datenschutzbestimmungen einzuhalten.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Häufig gestellte Fragen zur Datenaufbewahrung {#data-retention-faq}

In der folgenden Tabelle werden die Speicherzeiten für verschiedene Datentypen und Datenspeicherung Liste.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datentyp, Quelle oder Datenspeicherung </th> 
   <th colname="col2" class="entry"> Datenaufbewahrungsdauer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Back-End-Server </p> </td> 
   <td colname="col2"> <p>120 Tage. </p> <p> Audience Manager löscht Benutzerdaten von unseren Back-End-Servern 120 Tage nach der letzten Anzeige eines Audience Managers. Wenn <span class="keyword"> Audience Manager</span> die Benutzerdaten innerhalb dieses 120-Tage-Zyklus aufzeichnet, behalten wir diese Daten weitere 120 Tage bei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-Server </p> </td> 
   <td colname="col2"> <p> 14 Tage. </p> <p>Audience Manager löscht Benutzerdaten von unseren Edge-Servern 14 Tage nach der letzten Anzeige eines Audience Managers. Wenn <span class="keyword"> Audience Manager</span> die Benutzerdaten innerhalb dieses 14-tägigen Zyklus aufzeichnet, behalten wir diese Daten weitere 14 Tage bei. Wenn der Benutzer nach Ablauf des Zeitraums von 14 Tagen wieder aktiv wird, kommt es zu einer Verzögerung zwischen der ersten Ansicht der neuen Seite und dem Zeitpunkt, zu dem der Benutzer handlungsfähig wird. Nach mehr als 14 Tagen Inaktivität dauert es 6-18 Stunden, bis das gesamte Profil wieder zum Edge Center zurückgebracht wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rohprotokolle </p> </td> 
   <td colname="col2"> <p>180 Tage (nach 180 Tagen ohne Aktivität entfernt). </p> <p>Rohprotokolle sind Daten, die von einem Edge-Server über HTTP-Aufrufe oder von an <span class="keyword"> Audience Manager</span>gesendeten nicht mitgelieferten Dateien empfangen werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzeigenserver-Protokolle </p> </td> 
   <td colname="col2"> <p><b>Berichterstellung</b> </p> <p>Protokolldateien werden bis zu 30 Berichte lang aufbewahrt. Wir bestehen nicht übereinstimmende Protokolle (d. h. Protokolle, für die keine ID-Synchronisierung zwischen der Anzeigen-Server-ID eines Besuchers und der <span class="keyword"> Audience Manager</span> -ID besteht) in unserer Backend-Datenspeicherung, und in <span class="keyword"> Amazon S3</span> gespeicherte übereinstimmende Protokolle werden bis zu 30 Tage lang aufbewahrt. </p> <p><b>Actionable Log Files</b> </p> <p>Sowohl übereinstimmende als auch nicht übereinstimmende Protokolle werden bis zu 30 Tage lang aufbewahrt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-Profil (authentifizierte Profil) </p> </td> 
   <td colname="col2"> <p>Das Standardintervall für die Live-Übertragung (TTL) von inaktiven CRM-Profilen (Kunden-IDs) beträgt 24 Monate. Sie können jedoch die Audience Manager-Benutzeroberfläche verwenden, um das TTL-Intervall für inaktive CRM-Profil zwischen einem Monat und fünf Jahren zu reduzieren oder zu verlängern. Dies ist beim Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle möglich.</p> <p>Weitere Informationen finden Sie unter Datenquelleneinstellungen in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Erstellen einer geräteübergreifenden Datenquelle </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgerät-IDs </p> </td> 
   <td colname="col2"> <p>Die Aufbewahrungsbedingungen für Mobilgeräte-IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) folgen der in den ersten beiden Zeilen beschriebenen Kadenz: Back-End-Server und Edge-Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kundendaten-Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>Eine CDF-Datei enthält dieselben Daten, die ein <span class="keyword"> Audience Manager</span> -Ereignis-Aufruf (/Ereignis) an unsere Server sendet. Die Retentionszeit beträgt 8 Tage. Weitere Informationen zu CDF finden Sie in den häufig gestellten Fragen zu <a href="../features/cdf-files.md"> CDF Intro</a> und <a href="../faq/faq-cdf.md"> CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zuordnungen zwischen synchronisierten IDs </p> </td> 
   <td colname="col2"> <p>Die Lebensdauer der <a href="../features/administration/usage-limits.md#id-mapping-limits"> ID-Zuordnungen</a> zwischen Audience Manager-Cookie-IDs (Unique User IDs des<a href="../reference/ids-in-aam.md">Audience Managers oder AAM UUIDs</a>) und Drittanbieter-Cookie-IDs ist auf 120 Tage beschränkt. Die Lebensdauer der ID-Zuordnung wird jedes Mal zurückgesetzt, wenn das Audience Manager-Cookie im Audience Manager-Netzwerk angezeigt wird. Die letzte Synchronisierung der ID-Zuordnung bleibt während der gesamten Dauer der zugehörigen Unique User ID des <a href="../reference/ids-in-aam.md">Audience Managers (AAM UUID)</a>erhalten.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inbound-Daten </p> </td> 
   <td colname="col2"> <p>Dies sind eingehende Daten, die Sie per FTP an <span class="keyword"> Audience Manager</span> oder direkt an einen <span class="keyword"> Amazon S3</span> -Ordner senden. Siehe <a href="../faq/faq-inbound-data-ingestion.md"> Häufig gestellte Fragen zur Ingestion von Inbound-Kundendaten</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgehende Daten </p> </td> 
   <td colname="col2"> <p>Dies sind die Stapeldaten, die <span class="keyword"> Audience Manager</span> an Aktivierungen von Drittanbietern sendet. Die Retentionszeit beträgt 8 Tage. Weitere Informationen zu ausgehenden Daten finden Sie unter <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Ausgehende Batch-Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datenaufbewahrung zur Eigenschaftsqualifikation {#trait-qual}

Die nachstehende Tabelle Liste die Optionen zur Aufbewahrung von Eigenschaftsqualifikationen.

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
   <td colname="col2"> <p>Beim Löschen einer Eigenschaft werden die Daten zur Eigenschaftenqualifikation aus allen Profilen entfernt, die sich in der Vergangenheit für die Eigenschaft qualifiziert hatten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zeichenbeschränkung erreicht </p> </td> 
   <td colname="col2"> <p>Für jedes Profil wird eine Grenze von 100.000 Eigenschaftsqualifikationen festgelegt. Die Beschränkung gilt für authentifizierte Profil und Profil. Wenn ein Profil diese Grenze erreicht, werden wir die ältesten Eigenschaftsqualifikationen auf der Basis des Erststarts löschen. </p> <p>Weitere Informationen finden Sie in unserem <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"> Qualifikationslimit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


---
description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-title: Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung
solution: Audience Manager
title: Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance & Privacy
exl-id: bccf49d7-1a3b-4286-86fb-59e472af4501
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 84%

---

# Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung {#privacy-and-data-retention-faq}

Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.

<!-- faq_privacy.xml -->

## Häufig gestellte Fragen zum Datenschutz {#privacy-faq}

>[!TIP]
>
>Weitere Informationen finden Sie im [Datenschutzzentrum von Adobe](https://www.adobe.com/de/privacy.html).

**Wie verwendet Audience Manager Cookies und welche Cookies werden gesetzt?**

Siehe [Audience Manager-Cookies](https://docs.adobe.com/content/help/de-DE/core-services/interface/ec-cookies/cookies-am.html).

**Können Audience Manager-Kunden in den USA Benutzer mit EU-Eigenschaften ansprechen?**

Ja. Audience Manager arbeitet mit Clients, die über internationale Eigenschaften und Inventar verfügen. In der EU gibt es strenge Datenschutzgesetze, aber Audience Manager hat Clients, die Erstanbieterdaten für die Zielgruppenansprache in Europa verwenden. Audience Manager kann die Zielgruppenansprache für EU-Zielgruppen unterstützen, aber es liegt in Ihrer Verantwortung, die örtlichen Datenschutzbestimmungen einzuhalten.

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
   <th colname="col2" class="entry"> Datenaufbewahrungsfrist </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Backend-Server </p> </td> 
   <td colname="col2"> <p>120 Tage </p> <p> Audience Manager löscht Benutzerdaten 120 Tage nach dem letzten Besuch eines Benutzers auf der Audience Manager-Plattform von unseren Backend-Servern. Wenn <span class="keyword"> Audience Manager</span> die Aktivität des Benutzers innerhalb dieses 120-Tage-Zyklus aufzeichnet, behalten wir diese Daten noch weitere 120 Tage bei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-Server </p> </td> 
   <td colname="col2"> <p> 14 Tage </p> <p>Audience Manager löscht Benutzerdaten 14 Tage nach dem letzten Besuch eines Benutzers auf der Audience Manager-Plattform von unseren Edge-Servern. Wenn <span class="keyword"> Audience Manager</span> die Aktivität des Benutzers innerhalb dieses 14-Tage-Zyklus erfasst, behalten wir diese Daten noch 14 Tage. Wenn der Benutzer nach dem 14-tägigen Zyklus erneut aktiv wird, kommt es zu einer Verzögerung zwischen der ersten neuen Seitenversion und dem Zeitpunkt, zu dem der Benutzer zu einer Ansicht kommt. Nach mehr als 14 Tagen Inaktivität dauert es 6-18 Stunden, bis das gesamte Profil wieder zum Edge Center zurückgebracht wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rohprotokolle </p> </td> 
   <td colname="col2"> <p>60 Tage (nach 60 Tagen ohne Aktivität entfernt) </p> <p>Rohprotokolle sind Daten, die von einem Edge-Server über HTTP-Aufrufe empfangen werden, oder integrierten Dateien, die an <span class="keyword"> Audience Manager</span> gesendet werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adserver-Protokolle </p> </td> 
   <td colname="col2"> <p><b>Berichterstellung</b> </p> <p>Protokolldateien werden zu Berichtszwecken bis zu 30 Tage lang aufbewahrt. Nicht übereinstimmende Protokolle (d. h. Protokolle, bei denen es keine ID-Synchronisierung zwischen der ID des Adservers eines Besuchers und der <span class="keyword">Audience Manager</span>-ID gibt) werden nicht in unserem Backend-Speicher aufbewahrt. Übereinstimmende Protokolle, die in <span class="keyword">Amazon S3</span> gespeichert sind, werden bis zu 30 Tage lang aufbewahrt. </p> <p><b>Ausführbare Protokolldateien</b> </p> <p>Sowohl übereinstimmende als auch nicht übereinstimmende Protokolle werden bis zu 30 Tage lang aufbewahrt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profile auf CRM-Ebene (authentifizierte Profil) </p> </td> 
   <td colname="col2"> <p>Das Standard-TTL-Intervall (Time-to-Live) für inaktive Profile auf CRM-Ebene (Kunden-IDs) beträgt 24 Monate. Sie können jedoch die Audience Manager-Benutzeroberfläche verwenden, um das TTL-Intervall für inaktive CRM-Profil zwischen einem Monat und fünf Jahren zu reduzieren oder zu verlängern. Dies ist beim Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle möglich.</p> <p>Weitere Informationen finden Sie unter „Datenquelleneinstellungen“ in <a href="../features/profile-merge-rules/merge-rules-start.md#settings">Erstellen einer geräteübergreifenden Datenquelle</a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte-IDs </p> </td> 
   <td colname="col2"> <p>Die Aufbewahrungsbedingungen für Mobilgeräte-IDs (<a href="../reference/ids-in-aam.md">IDFA, GAID</a>) stimmen mit den in den ersten beiden Zeilen (Backend-Server und Edge-Server) überein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kundendaten-Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>Eine CDF-Datei enthält dieselben Daten, die ein <span class="keyword">Audience Manager</span>-Ereignisaufruf (/event) an unsere Server sendet. Die Aufbewahrungsfrist beträgt 8 Tage. Weitere Informationen zu CDF finden Sie in unter <a href="../features/cdf-files.md">Einführung in Kundendaten-Feeds</a> und <a href="../faq/faq-cdf.md">Häufig gestellte Fragen zu Kundendaten-Feeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zuordnungen zwischen synchronisierten IDs </p> </td> 
   <td colname="col2"> <p>Die Lebensdauer der <a href="../features/administration/usage-limits.md#id-mapping-limits">ID-Zuordnungen</a> zwischen Audience Manager-Cookie-IDs (<a href="../reference/ids-in-aam.md">Audience Manager Unique User IDs oder AAM-UUIDs</a>) und Cookie-IDs von Drittanbietern ist auf 120 Tage begrenzt. Die Lebensdauer der ID-Zuordnung wird jedes Mal zurückgesetzt, wenn das Audience Manager-Cookie im Audience Manager-Netzwerk gesehen wird. Die letzte ID-Zuordnungssynchronisierung bleibt für die Lebensdauer der zugeordneten <a href="../reference/ids-in-aam.md">AAM-UUID (Audience Manager Unique User ID)</a> erhalten.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eingehende Daten </p> </td> 
   <td colname="col2"> <p>Dies sind eingehende Daten, die Sie per FTP an <span class="keyword">Audience Manager</span> oder direkt an ein <span class="keyword">Amazon S3</span>-Verzeichnis senden. Siehe <a href="../faq/faq-inbound-data-ingestion.md">Häufig gestellte Fragen zur Erfassung von eingehenden Kundendaten</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgehende Daten </p> </td> 
   <td colname="col2"> <p>Dies sind die Batch-Daten, die <span class="keyword">Audience Manager</span> an Drittaktivierungspartner sendet. Die Aufbewahrungsfrist beträgt 8 Tage. Weitere Informationen zu ausgehenden Daten finden Sie unter <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">Ausgehende Batch-Übertragungen</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Datenaufbewahrung zur Eigenschaftsqualifikation {#trait-qual}

In der folgenden Tabelle sind die Aufbewahrungsoptionen für Eigenschaftsqualifikationen aufgeführt.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Eigenschaftsvorgang </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eigenschaft löschen </p> </td> 
   <td colname="col2"> <p>Beim Löschen einer Eigenschaft werden die Daten zur Eigenschaftsqualifikation aus allen Profilen entfernt, die sich in der Vergangenheit für die Eigenschaft qualifiziert hatten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eigenschaftsgrenze erreicht </p> </td> 
   <td colname="col2"> <p>Für jedes Profil wird eine Grenze von 100.000 Eigenschaftsqualifikationen festgelegt. Die Grenze gilt für authentifizierte Profile und Geräteprofile. Wenn ein Benutzerprofil diese Grenze erreicht, werden die ältesten Eigenschaftsqualifikationen anhand des Fi-Fo-Prinzips auf der Basis des Erststarts gelöscht. </p> <p>Weitere Informationen finden Sie unter <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">Qualifikationslimit für Eigenschaften</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

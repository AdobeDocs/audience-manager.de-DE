---
description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-description: Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.
seo-title: Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung
solution: Audience Manager
title: Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung
uuid: ef 558 fca -35 ff -44 f 1-8527-f 8 bee 9 f 2 c 7 e 9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung{#privacy-and-data-retention-faq}

Antworten auf häufige Fragen oder Probleme zum Thema Datenschutz und Daten.

<!-- faq_privacy.xml -->

## Häufig gestellte Fragen zum Datenschutz {#privacy-faq}

>[!TIP]
>
>Weitere Informationen finden Sie im [Datenschutzcenter](https://www.adobe.com/privacy.html) von Adobe.

**Wie verwendet Audience Manager Cookies und welche Cookies werden gesetzt?**

Siehe [Audience Manager-Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**Können Audience Manager-Kunden in den USA Benutzer auf EU-Eigenschaften als Ziel auswählen?**

Ja. Audience Manager funktioniert mit Kunden, die über internationale Eigenschaften und Bestände verfügen. Die EU hat strenge Datenschutzgesetze, aber Audience Manager verfügt über Kunden, die Erstanbieterdaten für Zielgruppentargeting in Europa verwenden. Audience Manager kann Targeting auf EU-Zielgruppen unterstützen, es ist jedoch Ihre Verantwortung, die lokalen Datenschutzvorschriften einzuhalten.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Häufig gestellte Fragen zur Datenaufbewahrung {#data-retention-faq}

In der folgenden Tabelle sind die Verfolgungszeiten für verschiedene Datentypen und Speichersysteme aufgeführt.

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
   <td colname="col2"> <p>120 Tage. </p> <p> Audience Manager löscht Benutzerdaten von unseren Back-End-Servern 120 Tage nach dem letzten Anzeigen eines Benutzers auf der Audience Manager-Plattform. Wenn <span class="keyword"> Audience Manager</span> die Benutzeraktivität innerhalb dieses 120-Tage-Zyklus aufzeichnet, werden diese Daten für weitere 120 Tage aufbewahrt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-Server </p> </td> 
   <td colname="col2"> <p> 14 Tage. </p> <p>Audience Manager löscht Benutzerdaten von unseren Edge-Servern 14 Tage nach der letzten Anzeige eines Benutzers auf der Audience Manager-Plattform. Wenn <span class="keyword"> Audience Manager</span> die Benutzeraktivität innerhalb dieses 14-Tage-Zyklus aufzeichnet, werden diese Daten für weitere 14 Tage beibehalten. Wenn der Benutzer nach dem 14-Tage-Zeitraum erneut aktiv wird, gibt es eine Verzögerung zwischen dieser ersten neuen Seitenansicht und dem Zeitpunkt, zu dem der Benutzer nachvollziehbar wird. Es dauert 6 bis 18 Stunden, bis das vollständige Profil nach mehr als 14 Tagen Inaktivität wieder zur Edge-Mitte zurückkehrt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rohprotokolle </p> </td> 
   <td colname="col2"> <p>180 Tage (nach 180 Tagen ohne Aktivität entfernt). </p> <p>Rohprotokolle sind Daten, die von einem Edge-Server über HTTP-Aufrufe empfangen werden oder aus Onboarved-Dateien, die an <span class="keyword"> Audience Manager gesendet</span>wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anzeigen-Server-Protokolle </p> </td> 
   <td colname="col2"> <p><b>Berichterstellung</b> </p> <p>Protokolldateien werden für Berichterstellungszwecke bis zu 30 Tage beibehalten. Wir bleiben nicht übereinstimmende Protokolle (d. h. Protokolle, für die keine ID-Synchronisierung zwischen der Werbeserver-ID des Besuchers und <span class="keyword"> Audience Manager</span> -ID) in unserem Backend-Speicher <span class="keyword"> vorhanden ist,</span> werden in unserem Backend-Speicher gespeichert, und übereinstimmende Protokolle werden bis zu 30 Tage aufbewahrt. </p> <p><b>Actionable Log Files</b> </p> <p>Übereinstimmende und nicht übereinstimmende Protokolle werden bis zu 30 Tage aufbewahrt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-Ebenenprofile (authentifizierte Profile) </p> </td> 
   <td colname="col2"> <p>Das Standardmäßige Zeitintervall (TTL) für inaktive CRM-Ebenenprofile (Kunden-IDs) beträgt 24 Monate. Sie können die Benutzeroberfläche von Audience Manager jedoch verwenden, um das TTL-Intervall für inaktive CRM-Ebenenprofile zwischen einem Monat und 5 Jahren zu reduzieren oder zu erweitern. Dies können Sie beim Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle erreichen.</p> <p>Weitere Informationen finden Sie unter Datenquelleneinstellungen unter <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Erstellen einer geräteübergreifenden Datenquelle </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobilgeräte-IDs </p> </td> 
   <td colname="col2"> <p>Die Aufbewahrungsbedingungen für Mobilgeräte-IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) folgen dem in den ersten beiden Zeilen, Backend-Servern und Edge-Servern beschriebenen Cache. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kundendatenfeeds (CDF) </p> </td> 
   <td colname="col2"> <p>Eine CDF-Datei enthält dieselben Daten, die ein <span class="keyword"> Audience Manager</span> -Ereignisaufruf (/-ereignis) an unsere Server sendet. Der Aufbewahrungszeitraum beträgt 8 Tage. Weitere Informationen zu CDF finden Sie unter <a href="../features/cdf-files.md"> CDF-Einführung und</a> <a href="../faq/faq-cdf.md"> CDF-häufig gestellte Fragen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Zuordnungen zwischen synchronisierten IDs </p> </td> 
   <td colname="col2"> <p>Zuordnungen zwischen synchronisierten IDs können für die gesamte Benutzer-ID <a href="../reference/ids-in-aam.md"> des Audience Manager-ID (AAM UUID) beibehalten</a>werden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eingehende Daten </p> </td> 
   <td colname="col2"> <p>Dies sind eingehende Daten, die <span class="keyword"> Sie</span> per FTP oder direkt in einen <span class="keyword"> Amazon S 3</span> -Ordner an Audience Manager senden. Siehe Häufig gestellte Fragen zu <a href="../faq/faq-inbound-data-ingestion.md"> Inbound Customer Data Capture</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ausgehende Daten </p> </td> 
   <td colname="col2"> <p>Dies sind die Batch-Daten, die <span class="keyword"> Audience Manager</span> an Drittanbieter-Aktivierungspartner sendet. Der Aufbewahrungszeitraum beträgt 8 Tage. Weitere Informationen zu ausgehenden Daten finden Sie unter <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Ausgehende Batch-Übertragungen</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-Qualifizierungsdatenspeicherung {#trait-qual}

In der folgenden Tabelle sind die Treueoptionen für Trait-Qualifikationen aufgeführt.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Trait-Vorgang </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Löschen von Eigenschaften </p> </td> 
   <td colname="col2"> <p>Wenn Sie eine Eigenschaft löschen, werden die Eigenschaftsqualifizierungsdaten aus allen Benutzerprofilen entfernt, die für die Eigenschaft in der Vergangenheit qualifiziert waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trait-Limit erreicht </p> </td> 
   <td colname="col2"> <p>Wir setzen ein Limit von 100.000 Eigenschaften für jedes Benutzerprofil ein. Die Beschränkung gilt für authentifizierte Profile und Geräteprofile. Wenn ein Benutzerprofil diese Grenze erreicht, löschen wir die ältesten Eigenschaften von Eigenschaften zunächst auf erster Ebene. </p> <p>Weitere Informationen finden Sie in unserem <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Trait-Qualifikationsgrenzwert</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


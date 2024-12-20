---
description: Häufige Fragen und Probleme im Zusammenhang mit dem Reporting.
seo-description: Common reporting-related questions and issues.
seo-title: Reporting FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zum Reporting
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting Reference
exl-id: 1e6531b2-bb39-4056-9d5e-164f50955f99
source-git-commit: 3bddd51582f3f8c46908dba5c5ac1938cb480013
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 95%

---

# Häufig gestellte Fragen zum Reporting{#reporting-faq}

Häufige Fragen und Probleme im Zusammenhang mit dem Reporting.

<br>

<!-- 

faq_reports.xml

 -->

**Warum zeigt das [!UICONTROL Trait Graph] bei neuen integrierten Eigenschaften manchmal niedrigere als die erwarteten Zahlen oder 0 an?**

Manchmal zeigt das [!UICONTROL Trait Graph] nach dem Hochladen von Eigenschaften keine Ergebnisse oder niedrigere als die erwarteten Zahlen an. Dies passiert, wenn das Datenvolumen, das wir erhalten, so groß ist, dass der eingehende Verarbeitungsvorgang die Aufnahme dieser Informationen erst nach Ablauf der Berichtsfrist für diesen Tag abschließen kann. 

Infolgedessen werden diese Daten zu spät an das Berichtssystem gesendet und nicht in dem eintägigen Berichtsintervall angezeigt, das zum Zeichnen des [!UICONTROL Trait Graph] verwendet wird. Sie können diese Daten jedoch am darauffolgenden Tag im 7-, 14-, 30- und 60-tägigen Berichtintervall in einem [Trendbericht](../reporting/trend-reports.md#trend-report-overview) oder einem [allgemeinen Bericht](../reporting/general-reports.md#general-reports-overview) anzeigen.

<br>

**Einige Segmente fehlen in einem [!UICONTROL Overlap]-Bericht. Wo sind sie?**

Um den Rechenaufwand zu verringern, werden in diesen Berichten statistisch nicht signifikante Daten aus den Ergebnissen weggelassen. Ihre Segmente fehlen nicht, sie werden nur ausgelassen, weil sie weder aussagekräftige Ergebnisse noch nützliche Benutzerpools liefern, die Sie gezielt ansprechen können. Siehe auch:

* [Berichte und Methoden des Daten-Sampling](../reporting/report-sampling.md)
* [Zählen von Unique Users in Überlagerungen und allgemeinen Berichten](../reporting/unique-user-counts.md).

<br>

**Ich führe eine E-Mail-Marketing-Kampagne durch. Wie kann ich feststellen, ob umgeleitete Benutzer von dieser Kampagne oder aus anderen Quellen auf meine Website kommen?**

Hängen Sie eine kampagnenspezifische Abfragezeichenfolge an die URL des Website-Bereichs an, den Sie überwachen möchten. Richten Sie anschließend eine Eigenschaftsregel ein, um diese Variable zu erfassen. Wenn Ihre URL beispielsweise in einer Kampagnen-ID wie dieser `www.test123.com/electronics?campaign=123` übergeben wird, erstellen Sie eine Trait-Regel , um diese Daten aus der `h_referer`-Variablen mit einer Trait-Regel zu erfassen, die nach einer Kopfzeile wie `h_referer = 'campaign=123'` sucht.

<br>

**Was ist der Unterschied zwischen der Echtzeit- und der Gesamtanzahl der Segmentpopulationen?**

* **Echtzeit:** Die Anzahl der Unique Users, die Teil des Segments sind und während eines festgelegten Zeitraums in Ihren Eigenschaften aktiv sind (d. h. [!DNL Audience Manager] muss die Aktivität für diesen Benutzer für den bestimmten Zeitraum aufgezeichnet haben).

* **Segmentpopulation insgesamt:** Eine Aggregation aller Benutzer, die derzeit in diesem Segment klassifiziert sind.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br>

**Ich habe ein Segment, das aus nur einer Eigenschaft besteht. Wenn ich mir die Berichtsmetriken ansehe, stimmen ihre Zahlen nicht überein. Woran liegt das?**

Siehe [Eigenschafts- und Segmentpopulationsdaten in Segment Builder](../features/segments/segment-builder-data.md).

<br>

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Ich integriere eine Datei und mein Eingangsbeleg zeigt eine hohe Anzahl erfolgreich bearbeiteter Datensätze. Die Berichte zeigen aber deutlich niedrigere Zahlen an. Warum?**

Im Backend werden integrierte Daten nur an Benutzer angehängt, die noch in AAM aktiv sind (Benutzer müssen in den letzten 120 Tagen die [!DNL DCS]-Aktivitäten ausgeführt haben). Wenn Sie Daten für Benutzer einbinden, die in [!DNL Audience Manager] bereits abgelaufen sind, teilt Ihnen [!UICONTROL Inbound] möglicherweise mit, dass eine bestimmte Anzahl von Benutzerdatensätzen eingebunden wurde. Wenn diese Benutzer jedoch keine aktuellen Aktivitäten ausgeführt haben, werden diese Daten gelöscht, wenn sie [!UICONTROL User Profile Store] erreichen, und die Berichterstattung wird dies aufzeigen.

<br>

**Warum sind die eindeutigen Eigenschaften meiner geräteübergreifend integrieren Eigenschaften viel höher als die Gesamtzahl der integrierten Datensätze?**

Wenn Sie eine Datei für einen geräteübergreifenden Datenanbieter integrieren, für den die Kunden-ID eingegeben wurde, führt Audience Manager eine Suche durch, um alle Geräte-IDs abzurufen, die jeder der integrierten Kunden-IDs zugeordnet sind. Audience Manager weist dann die integrierten Eigenschaften der Geräte-ID zu, die der Kunden-ID zugeordnet ist.

Angenommen, Sie haben 100 Datensätze integriert. Für jede dieser Kunden-IDs hat AAM im Durchschnitt drei Geräte-IDs zugeordnet. Daher wird die integrierte Eigenschaft 300 Geräte-IDs zugewiesen.

Es gibt zwei Gründe, warum eine einzelne geräteübergreifende Kunden-ID mit mehreren Geräte-IDs verknüpft werden kann:

* Benutzer melden sich von mehreren Computern/Browsern bei demselben geräteübergreifenden Konto an.
* Benutzer löschen ihre Cookies. Hinweis: „Aufgegebene“ Cookies werden nach 120 Tagen der Inaktivität des Benutzers gelöscht.

<br>

**Warum sind die [!UICONTROL Total Trait Realizations] für meine integrierten Eigenschaften immer 0?**

[!UICONTROL Total Trait Realizations] entsprechen den Seitenladevorgängen. [!UICONTROL Total Trait Realizations] geben an, wie oft bestimmte Eigenschaften in Echtzeit ausgelöst wurden. Diese Zahl wird nur für regelbasierte Eigenschaften berechnet. Integrierte Eigenschaften zeigen [!UICONTROL Total Trait Realizations] immer als 0.

<br>

**Ich habe eine Eigenschaft erstellt und das [!UICONTROL Trait Graph] zeigt eine größere Anzahl von [!UICONTROL Unique Trait Realizations] als die [!UICONTROL Total Trait Population]. Ist das normal?**

Sie sehen dies, weil es sich bei den [!UICONTROL Unique Trait Realizations] um Echtzeit-Metriken handelt. Die Berichtsvorgänge, die wir zur Berechnung von [!UICONTROL Total Trait Population] ausführen, laufen hingegen nicht in Echtzeit. Die [!UICONTROL Total Trait Population] sollte innerhalb weniger Tage größer als die [!UICONTROL Unique Trait Realizations] sein.

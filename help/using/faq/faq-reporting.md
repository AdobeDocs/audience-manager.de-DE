---
description: Häufige Fragen und Probleme im Zusammenhang mit Berichten.
seo-description: Häufige Fragen und Probleme im Zusammenhang mit Berichten.
seo-title: Häufig gestellte Fragen zum Reporting
solution: Audience Manager
title: Häufig gestellte Fragen zum Reporting
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---


# Häufig gestellte Fragen zum Reporting{#reporting-faq}

Häufige Fragen und Probleme im Zusammenhang mit Berichten.

<br> 

<!-- 

faq_reports.xml

 -->

**Warum werden bei neuen Onboarded-Eigenschaften[!UICONTROL Trait Graph]manchmal weniger als erwartet Zahlen oder 0 angezeigt?**

Manchmal werden nach dem Hochladen von Eigenschaften keine Ergebnisse angezeigt oder es werden weniger als erwartet [!UICONTROL Trait Graph] angezeigt. Dies geschieht, wenn das Datenvolumen, das wir erhalten, so groß ist, dass der eingehende Verarbeitungsauftrag diese Informationen erst nach Ablauf der Frist für diesen Berichte abrufen kann.

Daher werden diese Daten verspätet an das Berichte-System gesendet und nicht im 1-Tage-Berichte-Intervall angezeigt, das für die Darstellung der Daten verwendet wird [!UICONTROL Trait Graph]. Sie können diese Daten jedoch am darauffolgenden Tag im 7-, 14-, 30- und 60-tägigen Berichtintervall in einem [Trend](../reporting/trend-reports.md#trend-report-overview) - oder [Gesamtbericht](../reporting/general-reports.md#general-reports-overview) Ansicht werden.

<br> 

**Einige Segmente fehlen in einem[!UICONTROL Overlap]Bericht. Wo sind sie?**

Um die Rechenleistung zu reduzieren, lassen diese Berichte statistisch unbedeutende Daten aus den Ergebnissen aus. Ihre Segmente fehlen nicht, sie werden einfach gelöscht, weil sie keine aussagekräftigen Ergebnisse oder nützlichen Benutzerpools liefern, die Sie zur Zielgruppe nutzen können. Siehe auch:

* [Methoden für Berichte und Datenbearbeitung](../reporting/report-sampling.md)
* [Zählung individueller Benutzer in Überschneidungen und allgemeinen Berichten](../reporting/unique-user-counts.md).

<br> 

**Wenn ich eine E-Mail-Marketing-Kampagne verwende, wie kann ich feststellen, ob umgeleitete Benutzer von dieser Kampagne oder aus anderen Quellen zu meiner Site gelangen?**

Hängen Sie eine Kampagne-spezifische Abfrage-Zeichenfolge an die URL des Sitebereichs an, den Sie überwachen möchten. Richten Sie anschließend eine Eigenschaftsregel ein, um diese Variable zu erfassen. Wenn Ihre URL beispielsweise eine Kampagnen-ID wie die folgende übergibt, `www.test123.com/electronics?campaign=123`erstellen Sie eine Eigenschaftsregel, um die Daten aus der `h_referer` Variablen mit einer Eigenschaftsregel zu erfassen, die nach einer Überschrift wie `h_referer = 'campaign=123'`).

<br> 

**Was ist der Unterschied zwischen der Echtzeit- und der Gesamtanzahl der Segmentpopulationen?**

* **Echtzeit:** Die Anzahl der Unique Users, die innerhalb eines bestimmten Zeitraums Teil des Segments sind und in Ihren Eigenschaften aktiv sind (d. h., sie [!DNL Audience Manager] müssen die Aktivität für den betreffenden Zeitraum aufgezeichnet haben).

* **Segmentpopulation insgesamt:** Eine Aggregation aller Benutzer, die derzeit in diesem Segment klassifiziert sind.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Ich habe ein Segment, das aus nur einer Eigenschaft besteht. Wenn ich mir die Metriken der Berichte ansehe, stimmen ihre Zahlen nicht überein. Woran liegt das?**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Ich eingehende eine Datei und meine Eingangsbestätigung zeigt eine hohe Anzahl erfolgreich verarbeiteter Datensätze, aber Berichte zeigt deutlich niedrigere Zahlen an. Warum?**

Im Backend werden Daten, die nicht an Bord sind, nur an Benutzer angehängt, die weiterhin in AAM aktiv sind (Benutzer müssen in den letzten 120 Tagen eine aktuelle [!DNL DCS] Aktivität erhalten haben). Wenn Sie also Daten zu Benutzern eintragen, die bereits abgelaufen sind, [!DNL Audience Manager]können Sie [!UICONTROL Inbound] mitteilen, dass eine bestimmte Anzahl von Benutzerdatensätzen an Bord war. Wenn diese Benutzer jedoch keine Aktivität hatten, werden diese Daten bei Erreichen unseres Benutzerprofils gelöscht, [!UICONTROL User Profile Store] und der Berichte wird diese Daten aufdecken.

<br> 

**Warum sind die individuellen Merkmale meiner geräteübergreifenden Onboarded-Eigenschaften viel höher als die Gesamtzahl der Onboarded-Datensätze?**

Wenn Sie eine Datei für einen geräteübergreifenden Datenanbieter mit der Kunden-ID eintragen, führt Audience Manager eine Suche durch, um alle Geräte-IDs abzurufen, die mit jeder integrierten Kunden-IDs verknüpft sind. Audience Manager weist dann die integrierten Eigenschaften der Geräte-ID zu, die der Kunden-ID zugeordnet ist.

Angenommen, Sie haben 100 Datensätze an Bord. Für jede dieser Kunden-IDs hat AAM im Durchschnitt drei Geräte-IDs zugeordnet. Daher wird die Eigenschaft, die an Bord war, 300 Geräte-IDs zugewiesen.

Es gibt zwei Gründe, warum eine einzelne geräteübergreifende Kunden-ID mit mehreren Geräte-IDs verknüpft werden kann:

* Benutzer melden sich von mehreren Computern/Browsern an demselben geräteübergreifenden Konto an.
* Benutzer löschen ihre Cookies. Hinweis: &quot;Abgebrochene&quot;Cookies werden nach 120 Tagen der Inaktivität des Benutzers gelöscht.

<br> 

**Warum sind[!UICONTROL Total Trait Realizations]meine Onboared Eigenschaften immer 0?**

[!UICONTROL Total Trait Realizations] entsprechen den Seitenladevorgängen. [!UICONTROL Total Trait Realizations] Geben Sie an, wie oft bestimmte Eigenschaften in Echtzeit ausgelöst wurden. Diese Zahl wird nur für regelbasierte Eigenschaften berechnet. Die integrierten Eigenschaften werden immer [!UICONTROL Total Trait Realizations] als 0 angezeigt.

<br> 

**Ich habe eine Eigenschaft erstellt und die[!UICONTROL Trait Graph]zeigt eine größere Anzahl von[!UICONTROL Unique Trait Realizations]als die[!UICONTROL Total Trait Population]. Ist das normal?**

Sie sehen dies, weil es sich bei den [!UICONTROL Unique Trait Realizations] Metriken um Echtzeit-Metriken handelt, aber die Berichte-Aufträge, die wir zur Berechnung des Werts ausführen, [!UICONTROL Total Trait Population] sind nicht in Echtzeit. Die [!UICONTROL Total Trait Population] sollte innerhalb weniger Tage größer als die [!UICONTROL Unique Trait Realizations] sein.

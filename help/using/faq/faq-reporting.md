---
description: Allgemeine berichterstellungsbezogene Fragen und Probleme.
seo-description: Allgemeine berichterstellungsbezogene Fragen und Probleme.
seo-title: Häufig gestellte Fragen zum Reporting
solution: Audience Manager
title: Häufig gestellte Fragen zum Reporting
uuid: 78 cd 6 c 66-8 a 4 a -4748-ab 71-b 6 e 8 d 6078 c 94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Häufig gestellte Fragen zum Reporting{#reporting-faq}

Allgemeine berichterstellungsbezogene Fragen und Probleme.

<br> 

<!-- 

faq_reports.xml

 -->

**Warum werden bei neuen Aufgerufenen Eigenschaften[!UICONTROL Trait Graph]manchmal weniger als erwartet oder 0 angezeigt?**

Sometimes, after you upload traits, the [!UICONTROL Trait Graph] doesn't show any results or shows lower than expected numbers. Dies geschieht, wenn das Datenvolumen, das wir erhalten, so großartig ist, dass der eingehende Verarbeitungsauftrag diese Informationen erst nach dem Termin der Berichterstellung für diesen Tag abschließen kann.

As a result, this data is sent to the reporting system late and won't show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. However, you can view this data in the 7, 14, 30, and 60-day report intervals in a [Trend](../reporting/trend-reports.md#trend-report-overview) or [General Report](../reporting/general-reports.md#general-reports-overview) on the following day.

<br> 

**Einige Segmente fehlen in einem[!UICONTROL Overlap]Bericht. Where are they?**

Um die rechnerspezifische Nachfrage zu reduzieren, lassen diese Berichte statistisch unbedeutende Daten aus den Ergebnissen weg. Ihre Segmente fehlen nicht. Sie werden einfach abgelegt, da sie keine aussagekräftigen oder nützlichen Benutzerpools erbringen, die Sie als Ziel auswählen können. Siehe auch:

* [Berichte zu Berichten und Datenstichproben](../reporting/report-sampling.md)
* [Zählung individueller Benutzer in Überlappung und allgemeine Berichte](../reporting/unique-user-counts.md).

<br> 

**Wie kann ich feststellen, ob weitergeleitete Benutzer von dieser Kampagne oder aus anderen Quellen zu meiner Site gelangen, wenn ich eine E-Email-Marketingkampagne ausführe?**

Hängen Sie eine kampagnenspezifische Abfragezeichenfolge an die URL des Sitebereichs an, den Sie überwachen möchten. Richten Sie dann eine Eigenschaftsregel ein, um diese Variable zu erfassen. For example, if your URL passes in a campaign ID like this, `www.test123.com/electronics?campaign=123`, then create a trait rule to capture that data from the `h_referer` variable with a trait rule that looks for a header like `h_referer = 'campaign=123'`).

<br> 

**Was ist der Unterschied zwischen der Echtzeit- und der Gesamtanzahl der Segmente?**

* **Echtzeit:** Die Anzahl Unique Users, die Teil des Segments sind und während eines festgelegten Zeitraums aktiv für Ihre Eigenschaften sind (d. [!DNL Audience Manager] h. für den betreffenden Zeitraum aufgezeichnet worden sein).

* **Gesamtbesucherpopulation:** Eine Aggregation aller Benutzer, die aktuell in dieses Segment klassifiziert sind.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Ich habe ein Segment, das aus nur einer Eigenschaft besteht. Wenn ich die Berichterstellungsmetriken betrachte, stimmen ihre Zähler nicht überein. Woran liegt das?**

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

**Ich Inbound A File and my Inbound Receipt zeigt eine hohe Anzahl erfolgreich verarbeiteter Datensätze, aber die Berichterstellung zeigt viel niedrigere Zahlen an. Warum?**

In the backend, onboarded data gets attached only to users that are still active in AAM (user must have had recent [!UICONTROL DCS] activity in the past 120 days). Therefore, if you onboard data for users that have already expired in [!DNL Audience Manager], [!UICONTROL Inbound] might tell you that a certain number of user records were onboarded, but if these users have not had any recent activity, this data is dropped when it reaches our [!UICONTROL User Profile Store] and reporting will surface that.

<br> 

**Warum sind die Eigenschaftsangaben für mein geräteübergreifendes Merkmal wesentlich höher als die Gesamtanzahl der aufgenommenen Datensätze?**

Wenn Sie eine Datei für einen geräteübergreifenden Datenanbieter aufrufen, der die Kunden-ID abschließt, führt Audience Manager eine Suche durch, um alle Geräte-IDs abzurufen, die mit den einzelnen Kunden-IDs verknüpft sind. Audience Manager weist dann die onboarded-Eigenschaften der Geräte-ID zu, die mit der Kunden-ID verknüpft ist.

Angenommen, Sie haben 100 Einträge aufgezeichnet. Für jede dieser Kunden-IDs hat AAM im Durchschnitt drei Geräte-IDs zugeordnet. Daher wird die aufgenommene Eigenschaft 300 Geräte-IDs zugewiesen.

Es gibt zwei Gründe, warum eine einzelne geräteübergreifende Kunden-ID mit mehreren Geräte-IDs verknüpft werden kann:

* Benutzer melden sich bei demselben geräteübergreifenden Konto von mehreren Computern/Browsern an.
* Benutzer löschen ihre Cookies. Hinweis: " Abgebrochen" -Cookies werden nach 120 Tagen der Benutzerinaktivität gelöscht.

<br> 

**Warum sind[!UICONTROL Total Trait Realizations]meine vordefinierten Eigenschaften immer 0?**

[!UICONTROL Total Trait Realizations] auf Seite laden. [!UICONTROL Total Trait Realizations] geben an, wie oft bestimmte Eigenschaften in Echtzeit ausgelöst wurden. Diese Zahl wird nur für regelbasierte Eigenschaften berechnet. Onboarded traits always show [!UICONTROL Total Trait Realizations] as 0.

<br> 

**Ich habe eine Eigenschaft erstellt und die[!UICONTROL Trait Graph]Ansicht eine größere Zahl[!UICONTROL Unique Trait Realizations]als die[!UICONTROL Total Trait Population]. Is this normal?**

You are seeing this because the [!UICONTROL Unique Trait Realizations] are real-time metrics, but the reporting jobs we do to calculate the [!UICONTROL Total Trait Population] are not real-time. The [!UICONTROL Total Trait Population] should be larger than the [!UICONTROL Unique Trait Realizations] within a couple of days.

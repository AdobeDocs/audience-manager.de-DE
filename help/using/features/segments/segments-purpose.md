---
description: Beschreibt Segmente, deren Bestandteile und die Regelerstellung mit dem Segmentaufbau.
seo-description: Beschreibt Segmente, deren Bestandteile und die Regelerstellung mit dem Segmentaufbau.
seo-title: Segmente, Zusammensetzung und Regeln
solution: Audience Manager
title: Segmente, Zusammensetzung und Regeln
uuid: 886 d 4 abe-b 1 b 6-4983-b 4 fb-b 552 d 54 d 51 ba
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Segments: Purpose, Composition, and Rules {#segments-purpose-composition-and-rules}

Describes segments, their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## Zweck von Segmenten

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. In Audience Manager erstellen Sie Segmente mit serverseitigen Regeln. Mit diesen Regeln können Sie Zielgruppen anhand der Attribute der Site-Besucher erstellen, z. B.:

* Verhalten;
* Demografie (Alter, Geschlecht, Einkommen usw.);
* Andere Eigenschaften, die Sie in der Benutzeroberfläche definieren können.

## Segmentzusammensetzung

Ein Audience Manager-Segment ist eine serverseitige Regel, die aus einzelnen Eigenschaften oder Gruppen von Eigenschaften besteht. Eigenschaften bestehen aus Datenelementen mit Schlüssel-Wert-Paaren. Zusammen mit Regeln, die Sie auf Segmentebene festlegen, enthalten diese Schlüssel/Wert-Paare die Kriterien, die Besucher für Eigenschaften und Segmentmitgliedschaft qualifizieren.

## Überlegungen zur Adobe Analytics-Segmentzuordnung

Wenn Sie Adobe Analytics-Segmente oder Report Suites Ihrer Experience Cloud-Organisation zuordnen, erstellt Audience Manager automatisch neue, entsprechende, schreibgeschützte Segmente und Eigenschaften. Sie können den Speicherort dieser Segmente nicht über Audience Manager bearbeiten oder ändern. Alle Änderungen, die Sie an Ihren zugeordneten Adobe Analytics-Segmenten oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen.

>[!TIP]
>
>Audience Manager segments are different from [!DNL Adobe Analytics] segments. Read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.

## Regelbasierte Segmente mit Segmentaufbau erstellen

Im Gegensatz zu herkömmlichen Pixeln, die als Reaktion auf einfache Ja/keine Bedingungen ausgelöst werden, können Sie mit Segmentaufbau komplexe Segmentanforderungen erstellen. Like traits, segments evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. Diese Funktionen helfen Ihnen, fokussierte Zielgruppensegmente zu erstellen, die für Ihre geschäftlichen Anforderungen relevant sind.

## Vorteile

Segmente verbessern die standardmäßigen Pixelbasierten Zielgruppenerstellung/Segmentierungsprozesse, da sie:

* Erstellen Sie relevante, nützliche Segmente mit Eigenschaften von First und Drittanbietern.
* Erstellen Sie komplexe und komplexe Segmentierungsregeln mit booleschen Operatoren, Vergleichsausdrücken und Neuigkeits-/Häufigkeitskriterien.
* Senden Sie Segmentdaten an einen Zielpartner.
* Überwachen Sie die Leistung mit Audience Manager-Berichten.

>[!MORE_ LIKE_ THIS]
>
>* [Signale, Eigenschaften und Segmente](../../reference/signal-trait-segment.md)


---
description: Beschreibt Segmente, ihre Komponenten und die Regelerstellung mit dem Segmentaufbau.
seo-description: Beschreibt Segmente, ihre Komponenten und die Regelerstellung mit dem Segmentaufbau.
seo-title: Zweck, Zusammensetzung und Regeln von Segmenten
solution: Audience Manager
title: Zweck, Zusammensetzung und Regeln von Segmenten
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Segmente: Zweck, Zusammensetzung und Regeln {#segments-purpose-composition-and-rules}

Beschreibt Segmente, ihre Bestandteile und die Regelerstellung mit [!UICONTROL Segment Builder].

## Zweck der Segmente

Eine *`segment`* (oder eine *`audience`*) Gruppe von Benutzern, die gemeinsame Attribute haben. In Audience Manager erstellen Sie Segmente mit serverseitigen Regeln. Mit diesen Regeln können Sie Zielgruppengruppen basierend auf Site-Besucherattributen erstellen, z. B.:

* Verhalten;
* Demografie (Alter, Geschlecht, Einkommen usw.);
* Andere Eigenschaften, die Sie in der Benutzeroberfläche definieren können.

## Segmentzusammensetzung

Ein Audience Manager-Segment ist eine serverseitige Regel, die aus einzelnen oder Gruppen von Eigenschaften besteht. Eigenschaften bestehen aus Datenelementen, die Schlüssel-Wert-Paare genannt werden. Neben den Regeln, die Sie auf Segmentebene festlegen, enthalten diese Schlüssel-Wert-Paare die Kriterien, die Besucher für die Mitgliedschaft in Eigenschaften und Segmenten qualifizieren.

## Überlegungen zur Segmentzuordnung von Adobe Analytics

Beim Zuordnen von Adobe Analytics-Segmenten oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, entsprechende, schreibgeschützte Segmente und Eigenschaften. Sie können den Speicherort dieser Segmente nicht in Audience Manager bearbeiten oder ändern. Änderungen, die Sie an Ihren zugeordneten Adobe Analytics-Segmenten oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen.

>[!TIP]
>
>Audience Manager-Segmente unterscheiden sich von [!DNL Adobe Analytics] Segmenten. Eine ausführliche Beschreibung der Unterschiede finden Sie unter Segmente [in Analytics und Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) .

## Regelbasierte Segmente mit Segmentaufbau erstellen

Im Gegensatz zu herkömmlichen Pixeln, die aufgrund einfacher Ja/Nein-Bedingungen ausgelöst werden, können Sie mit dem Segmentaufbau komplexe Segmentanforderungen erstellen. Wie Eigenschaften bewerten Segmente Daten anhand von [!DNL Boolean] Ausdrücken ([!DNL AND], [!DNL OR], [!DNL NOT]), Vergleichsoperatoren (größer als, kleiner als, gleich usw.) und Neuigkeits-/Häufigkeitskriterien. Diese Funktionen unterstützen Sie bei der Erstellung zielgerichteter Zielgruppensegmente, die für Ihre geschäftlichen Anforderungen relevant sind.

## Vorteile

Segmente verbessern sich bei standardmäßigen pixelbasierten Zielgruppenerstellungs-/Segmentierungsprozessen, da sie Ihnen Folgendes ermöglichen:

* Erstellen Sie relevante, nützliche Segmente mit Eigenschaften von Erstanbietern und Drittanbietern.
* Erstellen Sie ausgefeilte und komplexe Segmentierungsregeln mit booleschen Operatoren, Vergleichsausdrücken und Neuigkeits-/Häufigkeitskriterien.
* Senden von Segmentdaten an einen Zielpartner
* Überwachen der Leistung mit Audience Manager-Berichten.

>[!MORELIKETHIS]
>
>* [Signale, Eigenschaften und Segmente](../../reference/signal-trait-segment.md)


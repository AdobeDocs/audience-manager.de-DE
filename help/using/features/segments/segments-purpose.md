---
description: Beschreibt Segmente, ihre Komponenten und die Regelerstellung mit dem Segmentaufbau.
seo-description: Beschreibt Segmente, ihre Komponenten und die Regelerstellung mit dem Segmentaufbau.
seo-title: Zweck, Zusammensetzung und Regeln von Segmenten
solution: Audience Manager
title: Zweck, Zusammensetzung und Regeln von Segmenten
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# Segmente: Zweck, Zusammensetzung und Regeln {#segments-purpose-composition-and-rules}

Beschreibt [!UICONTROL segments]die zugehörigen Komponenten und die Regelerstellung mit [!UICONTROL Segment Builder].

## Zweck [!UICONTROL Segments]

Ein *`segment`* (oder ein *`audience`*) ist eine Gruppe von Benutzern, die gemeinsame Attribute haben. In Audience Manager erstellen Sie [!UICONTROL segments] mit serverseitigen Regeln. Mit diesen Regeln können Sie Audiencen basierend auf Site-Besucher-Attributen erstellen, z. B.:

* Verhalten;
* Demografie (Alter, Geschlecht, Einkommen usw.);
* Andere Eigenschaften, die Sie in der Benutzeroberfläche definieren können.

## [!UICONTROL Segment] Zusammensetzung

Ein Audience Manager [!UICONTROL segment] ist eine serverseitige Regel, die aus einzelnen oder Gruppen von Eigenschaften besteht. Eigenschaften bestehen aus Datenelementen, die Schlüssel-Wert-Paare genannt werden. Neben den auf [!UICONTROL segment] Ebene festgelegten Regeln enthalten diese Schlüssel/Wert-Paare die Kriterien, die Besucher für Eigenschaften und [!UICONTROL segment] Mitgliedschaften qualifizieren.

## Überlegungen zur [!UICONTROL Adobe Analytics][!UICONTROL Segment] Zuordnung

Beim Zuordnen von Adobe Analytics [!UICONTROL segments] oder Report Suites zu Ihrem Experience Cloud erstellt Audience Manager automatisch neue, zugehörige, schreibgeschützte [!UICONTROL segments] und Eigenschaften. Sie können den Speicherort dieser Datenspeicherung nicht in Audience Manager [!UICONTROL segments] bearbeiten oder ändern. Änderungen, die Sie an Ihrem zugeordneten Adobe Analytics [!UICONTROL segments] oder Ihren Report Suites vornehmen, werden jedoch in Audience Manager übernommen.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] unterscheidet sich von [!DNL Adobe Analytics] [!UICONTROL segments]. Lesen Sie die [Informationen zu Segmenten in Analytics und Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) , um die Unterschiede ausführlich zu beschreiben.

## Regelbasiert erstellen [!UICONTROL Segments] mit [!UICONTROL Segment Builder]

Im Gegensatz zu herkömmlichen Pixeln, die aufgrund einfacher Ja/Nein-Bedingungen ausgelöst werden, [!UICONTROL Segment Builder] können Sie komplexe [!UICONTROL segment] Anforderungen erstellen. Sie können z. [!UICONTROL traits]B. Daten anhand von [!UICONTROL segments] Ausdrücken ( [!DNL Boolean] ,[!DNL AND], [!DNL OR]), Vergleichsoperatoren (größer als, kleiner als, gleich usw.) und Neuigkeits-/Häufigkeitskriterien [!DNL NOT]auswerten. Diese Funktionen unterstützen Sie bei der Erstellung gezielter Audiencen, die für Ihre geschäftlichen Anforderungen [!UICONTROL segments] relevant sind.

## Vorteile

[!UICONTROL Segments] verbessern Sie die standardmäßigen pixelbasierten Audiencen-/Segmentierungsprozesse, da Sie damit Folgendes tun können:

* Erstellen Sie relevante, nützliche Eigenschaften [!UICONTROL segments] mit Eigenschaften von Erstanbietern und Drittanbietern.
* Erstellen Sie ausgefeilte und komplexe Segmentierungsregeln mit booleschen Operatoren, Vergleichswerten und Neuigkeits-/Häufigkeitskriterien.
* Senden Sie [!UICONTROL segment] Daten an einen Zielpartner.
* Überwachen Sie die Leistung mit Audience Manager-Berichten.

>[!MORELIKETHIS]
>
>* [Signale, Eigenschaften und Segmente](../../reference/signal-trait-segment.md)


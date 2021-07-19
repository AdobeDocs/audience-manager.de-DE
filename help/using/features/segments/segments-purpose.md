---
description: Beschreibt Segmente, die zugehörigen Teile und die Regelerstellung mit Segment Builder.
seo-description: Beschreibt Segmente, die zugehörigen Teile und die Regelerstellung mit Segment Builder.
seo-title: Zweck, Zusammensetzung und Regeln von Segmenten
solution: Audience Manager
title: Zweck, Zusammensetzung und Regeln von Segmenten
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 'Segmente '
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 6%

---

# Segmente: Zweck, Zusammensetzung und Regeln {#segments-purpose-composition-and-rules}

Beschreibt [!UICONTROL segments], die zugehörigen Teile und die Regelerstellung mit [!UICONTROL Segment Builder].

## Zweck von [!UICONTROL Segments]

Ein *`segment`* (oder ein *`audience`*) ist eine Gruppe von Benutzern, die gemeinsame Attribute haben. In Audience Manager erstellen Sie [!UICONTROL segments] mit serverseitigen Regeln. Mit diesen Regeln können Sie Zielgruppen basierend auf Site-Besucherattributen erstellen, z. B.:

* Verhalten;
* Demografie (Alter, Geschlecht, Einkommen usw.);
* Andere Eigenschaften, die Sie in der Benutzeroberfläche definieren können.

## [!UICONTROL Segment] Komposition

Ein Audience Manager [!UICONTROL segment] ist eine serverseitige Regel, die aus einzelnen Eigenschaften oder Eigenschaftengruppen besteht. Eigenschaften bestehen aus Datenelementen, die als Schlüssel-Wert-Paare bezeichnet werden. Zusammen mit den Regeln, die Sie auf der [!UICONTROL segment]-Ebene festlegen, enthalten diese Schlüssel-Wert-Paare die Kriterien, die Besucher für Eigenschaften und die [!UICONTROL segment]-Mitgliedschaft qualifizieren.

## Überlegungen zur [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Zuordnung

Beim Zuordnen von Adobe Analytics [!UICONTROL segments] oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, übereinstimmende, schreibgeschützte [!UICONTROL segments] und Eigenschaften. Sie können den Speicherort dieser [!UICONTROL segments] nicht über Audience Manager bearbeiten oder ändern. Änderungen, die Sie an Ihren zugeordneten Adobe Analytics [!UICONTROL segments] oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] unterscheidet sich von [!DNL Adobe Analytics] [!UICONTROL segments]. Eine ausführliche Beschreibung der Unterschiede finden Sie unter [Grundlegendes zu Segmenten in Analytics und Audience Manager](https://docs.adobe.com/content/help/de-DE/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) .

## Erstellen regelbasierter [!UICONTROL Segments] mit [!UICONTROL Segment Builder]

Im Gegensatz zu herkömmlichen Pixeln, die als Reaktion auf einfache Ja/Nein-Bedingungen ausgelöst werden, können Sie mit [!UICONTROL Segment Builder] komplexe [!UICONTROL segment]-Anforderungen erstellen. Wie [!UICONTROL traits] werten [!UICONTROL segments] Daten mithilfe von [!DNL Boolean] Ausdrücken ([!DNL AND], [!DNL OR], [!DNL NOT]), Vergleichsoperatoren (größer als, kleiner als, gleich usw.) und Neuigkeits-/Häufigkeitskriterien aus. Diese Funktionen helfen bei der Erstellung einer fokussierten Zielgruppe [!UICONTROL segments], die für Ihre geschäftlichen Anforderungen relevant ist.

## Vorteile

[!UICONTROL Segments] die standardmäßigen pixelbasierten Zielgruppenerstellungs-/Segmentierungsprozesse verbessern, da sie Ihnen Folgendes ermöglichen:

* Erstellen Sie relevante, nützliche [!UICONTROL segments] mit Erstanbieter- und Drittanbieter-Eigenschaften.
* Erstellen Sie komplexe und komplexe Segmentierungsregeln mit booleschen Operatoren, Vergleichsausdrücken sowie Neuigkeits-/Häufigkeitskriterien.
* Senden Sie [!UICONTROL segment] -Daten an einen Zielpartner.
* Überwachen der Leistung mit Audience Manager-Berichten.

>[!MORELIKETHIS]
>
>* [Signale, Eigenschaften und Segmente](../../reference/signal-trait-segment.md)


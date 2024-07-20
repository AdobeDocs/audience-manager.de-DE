---
description: Beschreibt Segmente, die zugehörigen Teile und die Regelerstellung mit Segment Builder.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Zweck, Zusammensetzung und Regeln von Segmenten
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Segmente: Zweck, Zusammensetzung und Regeln {#segments-purpose-composition-and-rules}

Beschreibt [!UICONTROL segments], die zugehörigen Teile und die Regelerstellung mit [!UICONTROL Segment Builder].

## Zweck von [!UICONTROL Segments]

Ein *`segment`* (oder ein *`audience`*) ist ein Satz von Benutzern, die gemeinsame Attribute aufweisen. In Audience Manager erstellen Sie [!UICONTROL segments] mit serverseitigen Regeln. Mit diesen Regeln können Sie Zielgruppen basierend auf Site-Besucherattributen erstellen, z. B.:

* Verhalten;
* Demografie (Alter, Geschlecht, Einkommen usw.);
* Andere Eigenschaften, die Sie in der Benutzeroberfläche definieren können.

## [!UICONTROL Segment] Komposition

Ein Audience Manager [!UICONTROL segment] ist eine serverseitige Regel, die aus einzelnen Eigenschaften oder Eigenschaftengruppen besteht. Eigenschaften bestehen aus Datenelementen, die als Schlüssel-Wert-Paare bezeichnet werden. Zusammen mit Regeln, die Sie auf [!UICONTROL segment]-Ebene festlegen, enthalten diese Schlüssel-Wert-Paare die Kriterien, die Besucher für Eigenschaften- und [!UICONTROL segment]-Mitgliedschaft qualifizieren.

## Überlegungen zur [!UICONTROL Adobe Analytics] [!UICONTROL Segment]-Zuordnung

Beim Zuordnen von Adobe Analytics [!UICONTROL segments] oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, übereinstimmende schreibgeschützte Eigenschaften [!UICONTROL segments] und . Sie können den Speicherort dieser [!UICONTROL segments] nicht im Audience Manager bearbeiten oder ändern. Änderungen, die Sie an Ihrer zugeordneten Adobe Analytics [!UICONTROL segments] oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] unterscheidet sich von [!DNL Adobe Analytics] [!UICONTROL segments]. Eine ausführliche Beschreibung der Unterschiede finden Sie unter [Grundlegendes zu Segmenten in Analytics und Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) .

## Erstellen regelbasierter [!UICONTROL Segments] mit [!UICONTROL Segment Builder]

Im Gegensatz zu herkömmlichen Pixeln, die als Reaktion auf einfache Ja-/Nein-Bedingungen ausgelöst werden, können Sie mit [!UICONTROL Segment Builder] komplexe [!UICONTROL segment] Anforderungen erstellen. Wie [!UICONTROL traits] werten [!UICONTROL segments] Daten anhand von [!DNL Boolean] Ausdrücken ([!DNL AND], [!DNL OR], [!DNL NOT]), Vergleichsoperatoren (größer als, kleiner als, gleich usw.) und Neuigkeits-/Frequenzkriterien aus. Diese Funktionen helfen bei der Erstellung einer fokussierten Zielgruppe [!UICONTROL segments], die für Ihre geschäftlichen Anforderungen relevant ist.

## Vorteile

[!UICONTROL Segments] verbessert die standardmäßigen pixelbasierten Zielgruppenerstellungs-/Segmentierungsprozesse, da sie Ihnen Folgendes ermöglichen:

* Erstellen Sie relevante, nützliche [!UICONTROL segments] mit Erstanbieter- und Drittanbieter-Eigenschaften.
* Erstellen Sie komplexe und komplexe Segmentierungsregeln mit booleschen Operatoren, Vergleichsausdrücken sowie Neuigkeits-/Häufigkeitskriterien.
* Senden von [!UICONTROL segment] -Daten an einen Zielpartner.
* Überwachen der Leistung mit Audience Manager-Berichten.

>[!MORELIKETHIS]
>
>* [Signale, Eigenschaften und Segmente](../../reference/signal-trait-segment.md)

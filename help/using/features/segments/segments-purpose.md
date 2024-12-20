---
description: Beschreibt Segmente, ihre Bestandteile und die Regelerstellung mit Segment Builder.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Zweck, Komposition und Regeln der Segmente
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Segmente: Zweck, Komposition und Regeln {#segments-purpose-composition-and-rules}

Beschreibt [!UICONTROL segments], ihre Bestandteile und die Regelerstellung mit [!UICONTROL Segment Builder].

## Zweck der [!UICONTROL Segments]

Ein *`segment`* (oder ein *`audience`*) ist eine Gruppe von Benutzern, die gemeinsame Attribute aufweisen. Im Audience Manager erstellen Sie [!UICONTROL segments] mit serverseitigen Regeln. Mit diesen Regeln können Sie Zielgruppen erstellen, die auf Site-Besucherattributen basieren, z. B.:

* Verhalten;
* Demografie (Alter, Geschlecht, Einkommen usw.);
* Andere Merkmale, die Sie in der Benutzeroberfläche definieren können.

## [!UICONTROL Segment]

Eine Audience Manager-[!UICONTROL segment] ist eine Server-seitige Regel, die aus einzelnen Eigenschaften oder aus Gruppen von Eigenschaften besteht. Eigenschaften bestehen aus Datenelementen, die als Schlüssel-Wert-Paare bezeichnet werden. Diese Schlüssel-Wert-Paare enthalten neben den Regeln, die Sie auf [!UICONTROL segment] festlegen, die Kriterien, die Besucher für die Mitgliedschaft in einer Eigenschaft oder einem [!UICONTROL segment] qualifizieren.

## Überlegungen zur [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Beim Zuordnen von Adobe Analytics [!UICONTROL segments] oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, entsprechende schreibgeschützte [!UICONTROL segments] und Eigenschaften. Der Speicherort dieser [!UICONTROL segments] kann nicht vom Audience Manager aus bearbeitet oder geändert werden. Jede Änderung, die Sie an Ihren zugeordneten Adobe Analytics-[!UICONTROL segments] oder Report Suites vornehmen, spiegelt sich jedoch im Audience Manager wider.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] unterscheiden sich von [!DNL Adobe Analytics] [!UICONTROL segments]. Audience Manager Unter [Grundlagen zu Segmenten in Analytics und ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)&quot; finden Sie eine ausführliche Beschreibung der Unterschiede.

## Erstellen von regelbasierten [!UICONTROL Segments] mit [!UICONTROL Segment Builder]

Im Gegensatz zu herkömmlichen Pixeln, die bei einfachen Ja-/Nein-Bedingungen ausgelöst werden, ermöglicht [!UICONTROL Segment Builder] das Erstellen komplexer [!UICONTROL segment]. Wie [!UICONTROL traits] werten [!UICONTROL segments] Daten mithilfe von [!DNL Boolean]-Ausdrücken ([!DNL AND], [!DNL OR], [!DNL NOT]), Vergleichsoperatoren (größer als, kleiner als, gleich usw.) und Kriterien für Neuigkeit/Häufigkeit aus. Mit diesen Funktionen können Sie zielgerichtete [!UICONTROL segments] erstellen, die auf Ihre Geschäftsanforderungen zugeschnitten sind.

## Vorteile

[!UICONTROL Segments] verbessern die standardmäßigen pixelbasierten Zielgruppenerstellungs-/Segmentierungsprozesse, da sie Ihnen Folgendes ermöglichen:

* Erstellen Sie relevante, nützliche [!UICONTROL segments] mit First- und Third-Party-Eigenschaften.
* Erstellen Sie anspruchsvolle und komplexe Segmentierungsregeln mit booleschen Operatoren, Vergleichsausdrücken und Kriterien für Neuigkeit/Häufigkeit.
* Senden [!UICONTROL segment] Daten an einen Zielpartner.
* Überwachen der Leistung mit Audience Manager-Berichten.

>[!MORELIKETHIS]
>
>* [Signale, Eigenschaften und Segmente](../../reference/signal-trait-segment.md)

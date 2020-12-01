---
description: Beschreibt Segmente, ihre Komponenten und die Regelerstellung mit dem Segmentaufbau.
seo-description: Beschreibt Segmente, ihre Komponenten und die Regelerstellung mit dem Segmentaufbau.
seo-title: Zweck, Zusammensetzung und Regeln von Segmenten
solution: Audience Manager
title: Zweck, Zusammensetzung und Regeln von Segmenten
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# Segmente: Zweck, Zusammensetzung und Regeln {#segments-purpose-composition-and-rules}

Beschreibt [!UICONTROL segments], die zugehörigen Komponenten und die Regelerstellung mit [!UICONTROL Segment Builder].

## Zweck von [!UICONTROL Segments]

Ein *`segment`* (oder ein *`audience`*) ist eine Gruppe von Benutzern, die gemeinsame Attribute verwenden. In Audience Manager erstellen Sie [!UICONTROL segments] mit serverseitigen Regeln. Mit diesen Regeln können Sie Audiencen basierend auf Site-Besucher-Attributen erstellen, z. B.:

* Verhalten;
* Demografie (Alter, Geschlecht, Einkommen usw.);
* Andere Eigenschaften, die Sie in der Benutzeroberfläche definieren können.

## [!UICONTROL Segment] Zusammensetzung

Ein Audience Manager [!UICONTROL segment] ist eine serverseitige Regel, die aus einzelnen oder Gruppen von Eigenschaften besteht. Eigenschaften bestehen aus Datenelementen, die Schlüssel-Wert-Paare genannt werden. Neben den Regeln, die Sie auf der Ebene [!UICONTROL segment] festlegen, enthalten diese Schlüssel-Wert-Paare die Kriterien, die Besucher für Eigenschaften und [!UICONTROL segment]-Mitgliedschaft qualifizieren.

## Überlegungen zur [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Zuordnung

Beim Zuordnen von Adobe Analytics [!UICONTROL segments] oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, zugehörige schreibgeschützte [!UICONTROL segments]- und -Eigenschaften. Sie können den Speicherort der Datenspeicherung dieser [!UICONTROL segments] nicht von Audience Manager aus bearbeiten oder ändern. Änderungen, die Sie an Ihren zugeordneten Adobe Analytics [!UICONTROL segments]- oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] unterscheiden sich von [!DNL Adobe Analytics] [!UICONTROL segments]. Eine ausführliche Beschreibung der Unterschiede finden Sie unter [Die Segmente in Analytics und Audience Manager](https://docs.adobe.com/content/help/de-DE/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Regelbasierte [!UICONTROL Segments] mit [!UICONTROL Segment Builder] erstellen

Im Gegensatz zu herkömmlichen Pixeln, die aufgrund einfacher Ja/Nein-Bedingungen ausgelöst werden, können Sie mit [!UICONTROL Segment Builder] komplexe [!UICONTROL segment]-Anforderungen erstellen. Wie [!UICONTROL traits] können Sie [!UICONTROL segments] Daten mit [!DNL Boolean]-Ausdrücken ([!DNL AND], [!DNL OR], [!DNL NOT]), Vergleichsoperatoren (größer als, kleiner als, gleich usw.) und Neuigkeits-/Häufigkeitskriterien auswerten. Diese Funktionen unterstützen Sie bei der Erstellung einer fokussierten Audience [!UICONTROL segments], die für Ihre geschäftlichen Anforderungen relevant ist.

## Vorteile

[!UICONTROL Segments] verbessern Sie die standardmäßigen pixelbasierten Audiencen-/Segmentierungsprozesse, da Sie damit Folgendes tun können:

* Erstellen Sie relevante, nützliche [!UICONTROL segments] mit Eigenschaften von Erstanbietern und Drittanbietern.
* Erstellen Sie ausgefeilte und komplexe Segmentierungsregeln mit booleschen Operatoren, Vergleichswerten und Neuigkeits-/Häufigkeitskriterien.
* Senden Sie [!UICONTROL segment]-Daten an einen Zielpartner.
* Überwachen Sie die Leistung mit Audience Manager-Berichten.

>[!MORELIKETHIS]
>
>* [Signale, Eigenschaften und Segmente](../../reference/signal-trait-segment.md)


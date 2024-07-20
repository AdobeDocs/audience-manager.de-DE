---
description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Verwenden Sie die sofortige geräteübergreifende Unterdrückungsfunktion, um Ihren Benutzern geräteübergreifend ein konsistentes Erlebnis bereitzustellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Sofortige geräteübergreifende Unterdrückung
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 6%

---

# Sofortige geräteübergreifende Unterdrückung {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] ist die Möglichkeit, Benutzer auf mehreren Geräten zu unterdrücken, die mit ihnen verbunden sind, wenn ein bestimmtes Erlebnis auf einem dieser Geräte auftritt. Verwenden Sie die [!UICONTROL Instant Cross-Device Suppression] -Funktion, um Ihren Benutzern geräteübergreifend ein konsistentes Erlebnis bereitzustellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.

## Überblick {#overview}

[!UICONTROL Instant Cross-Device Suppression] bietet zwei wichtige Anwendungsfälle: verbesserte Benutzerfreundlichkeit und Medieneffizienz.

* **Verbessertes Benutzererlebnis**: Für Benutzer, die bereits Ihr Produkt oder Ihren Dienst erworben haben, werden nicht die gleichen kreativen Inhalte angezeigt wie vor dem Kauf. Stattdessen können Sie Upsell- oder Querverweise für Produkte oder Services anzeigen, von denen Sie wissen, dass sie nicht gekauft wurden.
* **Medieneffizienz**: Optimieren Sie Ihre Kampagnenausgaben, indem Sie eine globale Frequenzbegrenzung für alle [!DNL DSP]s anwenden. Die Frequenzlimitierung kann in Echtzeit für mehrere Geräte eines Benutzers aktiviert werden.

Die technischen Details der Aufhebung der Segmentierung in Echtzeit werden in [Regeln zur Profilzusammenführung und Prozesses zur Aufhebung der Gerätesegmentierung](merge-rule-unsegment.md) ausführlich beschrieben. Lesen Sie für die praktische Umsetzung der oben beschriebenen Anwendungsfälle weiter.

## Keine Zielgruppe nach Konvertierung {#do-not-target-once}

Vergewissern Sie sich, dass Ihre Benutzer, die bereits konvertiert haben (ein Produkt gekauft, ein Abonnement erworben haben usw.) wird nicht die gleiche Nachricht wie vor der Konvertierung angezeigt. Sie können dies wie folgt mit der [!UICONTROL AND NOT] -Logik abrufen.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die Logik [!UICONTROL AND NOT] , wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Konversionsereignis zu definieren, damit das Aufheben der Segmentierung in Echtzeit ausgelöst wird. Erfahren Sie mehr darüber, wie Sie [regelbasierte Eigenschaften erstellen](../traits/create-onboarded-rule-based-traits.md).
2. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Erfahren Sie mehr über das Hinzufügen von Segmenten zu [Server-zu-Server-Zielen](../destinations/add-edit-segments.md).

Ihre Besucher qualifizieren sich für das Segment, solange sie nicht konvertiert wurden. Sobald sie sich für die Konversionseigenschaft qualifizieren, folgen sie nicht mehr der Segmentregel und werden sofort aus dem Segment entfernt.

![](assets/and_not_use_case.png)

## Keine Zielgruppe nach x Impressionen {#do-not-target-after-x}

Sie können sicherstellen, dass Ihre Benutzer nicht mit demselben kreativen Inhalt überschwemmt werden, indem Sie Neuigkeits- und Häufigkeitskontrollen festlegen. Erstellen Sie in diesem Szenario ein Segment mit zwei Eigenschaften, wie in den folgenden Schritten beschrieben.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die Logik [!UICONTROL AND] , wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Impressionsereignis zu definieren, damit das Aufheben der Segmentierung in Echtzeit ausgelöst wird. Erfahren Sie mehr darüber, wie Sie [regelbasierte Eigenschaften erstellen](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Sie können [!UICONTROL Actionable Log Files] oder [!UICONTROL Pixel Calls] verwenden, um Eigenschaften basierend auf Benutzerimpressionen zu erstellen. Weitere Informationen zu [ausführbaren Protokolldateien](../../integration/media-data-integration/actionable-log-files.md) und [Pixelaufrufen](../../integration/media-data-integration/impression-data-pixels.md).
2. Anwenden von Frequenzsteuerelementen auf die zweite Eigenschaft. Bei Bedarf können Sie auch Neuigkeitskontrollen hinzufügen. Erfahren Sie mehr über [das Anwenden von Neuigkeits- und Frequenzsteuerelementen](../segments/recency-and-frequency.md).
3. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Erfahren Sie mehr über das Hinzufügen von Segmenten zu [Server-zu-Server-Zielen](../destinations/add-edit-segments.md).

In diesem Szenario werden Ihre Benutzer, sobald sie mehr als drei Impressionen gesammelt haben, aus diesem Segment entfernt und sehen diesen bestimmten Kreativelement nicht mehr.

![](assets/impressions_use_case.png)

## Wichtige Aspekte - Verarbeitung {#processing-notes}

Beachten Sie die folgenden Aspekte im Zusammenhang mit der Verarbeitung:

* Damit die Funktion zur Aufhebung der Segmentierung in Echtzeit funktioniert, müssen Sie die gewünschten Segmente den Echtzeit-Server-zu-Server-Zielen zuordnen.
* Für Geräte, die über ein [Gerätediagramm](profile-link-use-case.md#recommendations) mit einem Gerät verbunden sind, wird eine Beschränkung von vier Geräten für die Auswertung und Aufhebung der Segmentierung erzwungen. Diese Einschränkung wird unter [Gerätediagrammoptionen und Gerätesegmentierung](merge-rule-unsegment.md#device-graph-options-unsegmentation) beschrieben. &#x200B;
* Der Befehl zum Aufheben der Segmentierung wird in eine Batch-Datei aufgenommen, die alle 24 Stunden an Ziele gesendet wird. Dies gilt für mehrere Geräte, die über das Gerätediagramm verbunden sind.
* Das Gerät muss in Echtzeit (auf dem [Edge](../../reference/system-components/components-edge.md)) angezeigt werden, um die Segmentbewertung in Echtzeit zu veranlassen. Bei Eigenschaften mit dem Wert &quot;[!UICONTROL time-to-live (TTL)]&quot;, wenn die Eigenschaft &quot;[!DNL TTL]&quot; erfüllt ist, wird die Segmentierung des Geräts über die Batch-Datei automatisch innerhalb von 24 Stunden aufgehoben. &#x200B; Erfahren Sie mehr darüber, wie Sie [ein Ablaufintervall für eine Eigenschaft festlegen](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Wenn Sie die [!UICONTROL DCS API] verwenden, um regelbasierte Eigenschaften in Echtzeit zu integrieren, können Sie die Aufhebung der Segmentierung mit der Verwendung der [!UICONTROL AND NOT] -Logik Trigger haben. Weitere Informationen zum Senden von Daten an die DCS-API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) finden Sie &#x200B;[

## Wichtige Aspekte - Zeit {#timing-notes}

Beachten Sie die folgenden Aspekte im Zusammenhang mit dem Timing:

* Ein Segment wird auf dem [Edge](../../reference/system-components/components-edge.md) für den gleichen Zeitraum gespeichert wie ein Geräteprofil auf dem [!UICONTROL Edge], d. h. 14 Tage seit der letzten Echtzeit-Interaktion. Weitere Informationen zur Datenaufbewahrung finden Sie in unseren [FAQ zur Datenaufbewahrung](../../faq/faq-privacy.md#data-retention-faq).
* Es dauert etwa 24 Stunden, bis sich der Vorgang zum Aufheben der Segmentierung über [!DNL DCS] -Regionen erstreckt. Mehr über unsere [!DNL DCS] Regionen [hier](../../reference/system-components/components-data-collection.md) und [hier](../../api/dcs-intro/dcs-api-reference/dcs-regions.md) erfahren.

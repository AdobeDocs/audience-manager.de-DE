---
description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-title: Sofortige geräteübergreifende Unterdrückung
title: Sofortige geräteübergreifende Unterdrückung
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# Sofortige geräteübergreifende Unterdrückung {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] ist die Möglichkeit, Benutzer über mehrere Geräte hinweg zu unterdrücken, wenn ein bestimmtes Erlebnis auf einem dieser Geräte auftritt. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.

## Überblick {#overview}

[!UICONTROL Instant Cross-Device Suppression] liefert zwei Schlüsselfälle: verbesserte Benutzererfahrung und Medieneffizienz.

* **Ein verbessertes Benutzererlebnis**: Benutzer, die bereits Ihre Produkte oder Dienstleistungen gekauft haben, sehen nicht dieselben kreativen Elemente wie vor dem Kauf. Stattdessen könnten Sie Upsell- oder Querverkaufsmeldungen für Produkte oder Services anzeigen, die sie nicht gekauft haben.
* **Medieneffizienz**: Optimieren Sie Ihre Kampagnenausgaben, indem Sie für alle [!DNL DSP]s eine globale Frequenzausrichtung anwenden. Die Häufigkeit der Interaktion kann in Echtzeit für mehrere Geräte festgelegt werden, die zu einem Benutzer gehören.

Technische Details zur Echtzeitaufhebung der Segmentierung sind in der Länge unter ["Profilzusammenführung - Regeln und Geräteun-Segmentierungsprozesse](../../features/profile-merge-rules/merge-rule-unsegment.md)«beschrieben. Lesen Sie die Informationen zur praktischen Implementierung der oben beschriebenen Anwendungsfälle.

## Kein Targeting nach Konvertierung {#do-not-target-once}

Stellen Sie sicher, dass Ihre Benutzer bereits konversion (ein Produkt erworben, ein Abonnement erworben usw.) nicht dieselbe Messaging wie vor der Konvertierung. Sie können dies wie folgt mithilfe der [!UICONTROL AND NOT] Logik abrufen.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND NOT] Logik, wie im Bild unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Konversionsereignis für das unsegment zu definieren, das in Echtzeit ausgelöst werden soll. Erfahren Sie mehr darüber, wie regelbasierte Eigenschaften [erstellt](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)werden.
1. Ordnen Sie das Segment einer beliebigen Anzahl von Real-Time Server-to-Server-Zielen zu. Erfahren Sie, wie Sie Segmente zu [Server-zu-Server-Zielen hinzufügen](../../features/destinations/add-edit-segments.md).

Ihre Besucher qualifizieren sich für das Segment, solange sie nicht konvertiert wurden. Sobald sie sich für die Konversionseigenschaft qualifizieren, werden sie nicht mehr der Segmentregel entsprechen und werden sofort aus dem Segment entfernt.

![](assets/and_not_use_case.png)

## Nicht nach X Impressionen suchen {#do-not-target-after-x}

Sie können Ihre Benutzer nicht mit dem gleichen Kreativen überschwemmen, indem Sie Neuigkeit- und Häufigkeitssteuerelemente festlegen. Erstellen Sie in diesem Szenario ein Segment mit zwei Eigenschaften, wie in den unten stehenden Schritten beschrieben.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND] Logik, wie im Bild unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Impressionsereignis für das unsegment zu definieren, das in Echtzeit ausgelöst werden soll. Erfahren Sie mehr darüber, wie regelbasierte Eigenschaften [erstellt](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)werden.
   >[!NOTE]
   >
   >Sie können [!UICONTROL Actionable Log Files] Eigenschaften [!UICONTROL Pixel Calls] basierend auf Benutzerimpressionen verwenden oder erstellen. Weitere Informationen zu [ausführbaren Protokolldateien](../../integration/media-data-integration/actionable-log-files.md) und [Pixel-Aufrufen](../../integration/media-data-integration/impression-data-pixels.md).
1. Wenden Sie Steuerelemente für die Frequenz auf die zweite Eigenschaft an. Sie können auch Neuigkeit-Steuerelemente hinzufügen. Erfahren Sie mehr über [die Anwendung von Neuigkeit- und Frequenzsteuerelementen](../../features/segments/recency-and-frequency.md).
1. Ordnen Sie das Segment einer beliebigen Anzahl von Real-Time Server-to-Server-Zielen zu. Erfahren Sie, wie Sie Segmente zu [Server-zu-Server-Zielen hinzufügen](../../features/destinations/add-edit-segments.md).

In diesem Szenario werden die Benutzer, sobald sie mehr als drei Impressionen gesammelt haben, aus diesem Segment entfernt und dieses spezifische kreative Element wird nicht mehr angezeigt.

![](assets/impressions_use_case.png)

## Wichtige Aspekte - Verarbeitung - Verarbeitung {#processing-notes}

Beachten Sie folgende Aspekte im Zusammenhang mit der Verarbeitung:

* Damit die Echtzeit-Segmentfunktion funktioniert, müssen Sie die gewünschten Segmente realisierungsserver-zu-Server-Zielen zuordnen.
* Für Geräte, die mit einem Gerät mit [einem Gerätediagramm](../../features/profile-merge-rules/profile-link-use-case.md#recommendations)verbunden sind, erzwingen wir eine Beschränkung von vier Geräten bezüglich der Auswertung und der Aufhebung der Segmentierung. Diese Einschränkung wird unter [Gerätediagrammoptionen und Geräteaufhebung](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation)beschrieben.
* Der Befehl "Unsegmente" wird in einer Stapelverarbeitungsdatei, die alle 24 Stunden an die Ziele gesendet wird, für mehrere Geräte verwendet, die durch das Gerätediagramm verbunden sind.
* Das Gerät muss in Echtzeit (auf der [Edge](../../reference/system-components/components-edge.md)) angezeigt werden, um die Segmentauswertung anzufordern. Bei Eigenschaften mit [!UICONTROL time-to-live (TTL)] einem Wert wird das Gerät nicht automatisch segmentiert, solange eine Eigenschaft [!DNL TTL]*erfüllt* ist, bis das Gerät in Echtzeit weiter angezeigt wird. Erfahren Sie mehr darüber, wie [Sie ein Eigenschaftsablaufintervall festlegen](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Wenn Sie die [!UICONTROL DCS API] auf Bord regelbasierten Eigenschaften in Echtzeit verwenden, können Sie das Unsegment mit der [!UICONTROL AND NOT] Logik auslösen. Erfahren Sie mehr über [das Senden von Daten an die DCS-API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Wichtige Aspekte - Zeit - Zeit {#timing-notes}

Beachten Sie folgende Aspekte im Zusammenhang mit dem Timing:

* Ein Segment wird für denselben Zeitraum auf [der Edge](../../reference/system-components/components-edge.md) gespeichert, da ein Geräteprofil auf dem Tag [!UICONTROL Edge](14 Tage seit der letzten Echtzeitinteraktion) gespeichert ist. Lesen Sie mehr zur Datenaufbewahrung in unseren häufig gestellten Fragen zur [Datenaufbewahrung](../../faq/faq-privacy.md#data-retention-faq).
* Es dauert ca. 24 Stunden, bis der Segmentvorgang über [!UICONTROL DCS] mehrere Regionen verteilt wird. Erfahren Sie mehr über unsere [!UICONTROL DCS] Regionen [hier](../../reference/system-components/components-data-collection.md) und [](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)hier.
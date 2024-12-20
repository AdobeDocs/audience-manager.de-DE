---
description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Verwenden Sie die Funktion „Sofortige geräteübergreifende Unterdrückung“, um Ihren Benutzern ein konsistentes Erlebnis auf allen Geräten zu bieten. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
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

[!UICONTROL Instant Cross-Device Suppression] ist die Möglichkeit, Benutzer auf mehreren Geräten, die mit ihnen verbunden sind, zu unterdrücken, wenn ein bestimmtes Erlebnis auf einem dieser Geräte auftritt. Verwenden Sie die [!UICONTROL Instant Cross-Device Suppression]-Funktion, um Ihren Benutzern ein konsistentes Erlebnis über Geräte hinweg zu bieten. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.

## Überblick {#overview}

[!UICONTROL Instant Cross-Device Suppression] bietet zwei wichtige Anwendungsfälle: Verbessertes Benutzererlebnis und Medieneffizienz.

* **Ein verbessertes Benutzererlebnis**: Benutzer, die bereits Ihr Produkt oder Ihre Dienstleistung gekauft haben, sehen nicht mehr dieselben Kreativen wie vor dem Kauf. Stattdessen können Sie Upsell- oder Crossselling-Nachrichten für Produkte oder Services anzeigen, von denen Sie wissen, dass sie nicht gekauft haben.
* **Medieneffizienz**: Optimieren Sie Ihre Kampagnenausgaben, indem Sie eine globale Häufigkeitsbegrenzung auf alle [!DNL DSP] anwenden. Die Frequenzlimitierung kann für mehrere Geräte eines Benutzers in Echtzeit aktiviert werden.

Die technischen Details der Echtzeit-Nicht-Segmentierung werden in „Profilzusammenführungsregeln und Prozesse zur Aufhebung der [&quot; ](merge-rule-unsegment.md). Lesen Sie weiter, um die oben beschriebenen Anwendungsfälle praktisch umzusetzen.

## Nach der Konvertierung nicht als Ziel auswählen {#do-not-target-once}

Vergewissern Sie sich, dass Ihren Benutzern, die bereits eine Konversion durchgeführt haben (ein Produkt gekauft, ein Abonnement erworben haben usw.), nicht dieselbe Nachricht angezeigt wird wie vor der Konversion. Sie können dies mit der [!UICONTROL AND NOT] Logik wie folgt abrufen.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND NOT] Logik, wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Konversionsereignis zu definieren, damit die Aufhebung des Segments in Echtzeit ausgelöst wird. Erfahren Sie mehr über [Erstellen regelbasierter Eigenschaften](../traits/create-onboarded-rule-based-traits.md).
2. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Erfahren Sie mehr über das Hinzufügen von Segmenten zu [Server-zu-Server-Zielen](../destinations/add-edit-segments.md).

Ihre Besucher sind für das Segment qualifiziert, solange sie nicht konvertiert sind. Sobald sie sich für das Konversionsmerkmal qualifizieren, hören sie auf, die Segmentregel zu befolgen, und werden sofort aus dem Segment entfernt.

![](assets/and_not_use_case.png)

## Nach x Impressionen nicht als Ziel auswählen {#do-not-target-after-x}

Sie können sicherstellen, dass Sie Ihre Benutzer nicht mit denselben kreativen Inhalten überschwemmen, indem Sie die Steuerung der Neuigkeit und Häufigkeit festlegen. Erstellen Sie in diesem Szenario ein Segment mit zwei Eigenschaften, wie in den folgenden Schritten beschrieben.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND] Logik, wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Impression-Ereignis für das Unsegment zu definieren, das in Echtzeit ausgelöst werden soll. Erfahren Sie mehr über [Erstellen regelbasierter Eigenschaften](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Sie können [!UICONTROL Actionable Log Files] oder [!UICONTROL Pixel Calls] verwenden, um Eigenschaften basierend auf Benutzerimpressionen zu erstellen. Lesen Sie mehr über [Verwertbare Protokolldateien](../../integration/media-data-integration/actionable-log-files.md) und [Pixel-Aufrufe](../../integration/media-data-integration/impression-data-pixels.md).
2. Wenden Sie Häufigkeitssteuerungen auf die zweite Eigenschaft an. Wenn Sie möchten, können Sie auch Neuigkeitskontrollen hinzufügen. Lesen Sie mehr über [Anwenden von Neuigkeits- und Häufigkeitskontrollen](../segments/recency-and-frequency.md).
3. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Erfahren Sie mehr über das Hinzufügen von Segmenten zu [Server-zu-Server-Zielen](../destinations/add-edit-segments.md).

In diesem Szenario werden Ihre Benutzer, sobald sie mehr als drei Impressions gesammelt haben, aus diesem Segment entfernt und sehen diese bestimmte Kreativität nicht mehr.

![](assets/impressions_use_case.png)

## Wichtige Aspekte - Verarbeitung {#processing-notes}

Beachten Sie diese Aspekte in Bezug auf die Verarbeitung:

* Damit die Funktion zum Aufheben von Segmenten in Echtzeit funktioniert, müssen Sie die gewünschten Segmente Echtzeit-Server-zu-Server-Zielen zuordnen.
* Für Geräte, die über ein [Gerätediagramm](profile-link-use-case.md#recommendations) mit einem Gerät verbunden sind, erzwingen wir eine Beschränkung von vier Geräten in Bezug auf die Bewertung und Nicht-Segmentierung. Diese Einschränkung wird unter [Optionen für Gerätediagramme und ](merge-rule-unsegment.md#device-graph-options-unsegmentation)&quot; beschrieben&#x200B;
* Der Befehl zum Aufheben der Segmentierung wird in einer Batch-Datei enthalten sein, die für mehrere über das Gerätediagramm verbundene Geräte alle 24 Stunden an Ziele gesendet wird.
* Das Gerät muss in Echtzeit (auf der [Edge) angezeigt werden](../../reference/system-components/components-edge.md) um eine Segmentauswertung in Echtzeit zu veranlassen. Bei Eigenschaften, die eine [!UICONTROL time-to-live (TTL)] haben, wenn die [!DNL TTL] erfüllt ist, wird die Segmentierung des Geräts innerhalb von 24 Stunden über die Batch-Datei automatisch aufgehoben..&#x200B; Erfahren Sie mehr über das [Festlegen eines Ablaufintervalls für Eigenschaften](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Wenn Sie die [!UICONTROL DCS API] verwenden, um regelbasierte Eigenschaften in Echtzeit zu integrieren, können Sie die Aufhebung der Segmentierung mithilfe der [!UICONTROL AND NOT] Logik als Trigger verwenden. Weitere Informationen über [Senden von Daten an die DCS-API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Wichtige Aspekte zu beachten - Timing {#timing-notes}

Beachten Sie diese Aspekte im Zusammenhang mit dem Timing:

* Ein Segment wird in der [Edge](../../reference/system-components/components-edge.md) für denselben Zeitraum gespeichert, in dem ein Geräteprofil in der [!UICONTROL Edge] gespeichert wird, d. h. 14 Tage seit der letzten Echtzeit-Interaktion. Weitere Informationen zur Datenspeicherung finden Sie in unserer [Häufig gestellte Fragen zur Datenspeicherung](../../faq/faq-privacy.md#data-retention-faq).
* Es dauert etwa 24 Stunden, bis sich der Vorgang zum Aufheben der Segmentierung über [!DNL DCS] Regionen ausbreitet. Lesen Sie mehr über unsere [!DNL DCS] Regionen [hier](../../reference/system-components/components-data-collection.md) und [hier](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

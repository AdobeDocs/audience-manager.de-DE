---
description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-title: Sofortige geräteübergreifende Unterdrückung
title: Sofortige geräteübergreifende Unterdrückung
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Sofortige geräteübergreifende Unterdrückung {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] ist die Möglichkeit, Benutzer über mehrere Geräte hinweg zu unterdrücken, wenn ein bestimmtes Erlebnis auf einem dieser Geräte auftritt. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.

## Überblick {#overview}

[!UICONTROL Instant Cross-Device Suppression] liefert zwei Schlüsselfälle: verbesserte Benutzererfahrung und Medieneffizienz.

* **Ein verbessertes Benutzererlebnis**: Benutzer, die bereits Ihre Produkte oder Dienstleistungen gekauft haben, sehen nicht dieselben kreativen Elemente wie vor dem Kauf. Stattdessen könnten Sie Upsell- oder Querverkaufsmeldungen für Produkte oder Services anzeigen, die sie nicht gekauft haben.
* **Medieneffizienz**: Optimieren Sie Ihre Kampagnenausgaben, indem Sie für alle [!DNL DSP]s eine globale Frequenzausrichtung anwenden. Die Häufigkeit der Interaktion kann in Echtzeit für mehrere Geräte festgelegt werden, die zu einem Benutzer gehören.

The technical details of the real-time unsegmentation are described in length in [Profile Merge Rules and Device Un-Segmentation Processes](../../features/profile-merge-rules/merge-rule-unsegment.md). Lesen Sie die Informationen zur praktischen Implementierung der oben beschriebenen Anwendungsfälle.

## Do Not Target Once Converted {#do-not-target-once}

Stellen Sie sicher, dass Ihre Benutzer bereits konversion (ein Produkt erworben, ein Abonnement erworben usw.) nicht dieselbe Messaging wie vor der Konvertierung. You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Konversionsereignis für das unsegment zu definieren, das in Echtzeit ausgelöst werden soll. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. Ordnen Sie das Segment einer beliebigen Anzahl von Real-Time Server-to-Server-Zielen zu. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

Ihre Besucher qualifizieren sich für das Segment, solange sie nicht konvertiert wurden. Sobald sie sich für die Konversionseigenschaft qualifizieren, werden sie nicht mehr der Segmentregel entsprechen und werden sofort aus dem Segment entfernt.

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

Sie können Ihre Benutzer nicht mit dem gleichen Kreativen überschwemmen, indem Sie Neuigkeit- und Häufigkeitssteuerelemente festlegen. Erstellen Sie in diesem Szenario ein Segment mit zwei Eigenschaften, wie in den unten stehenden Schritten beschrieben.

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Impressionsereignis für das unsegment zu definieren, das in Echtzeit ausgelöst werden soll. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. Read more about [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) and [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
1. Wenden Sie Steuerelemente für die Frequenz auf die zweite Eigenschaft an. Sie können auch Neuigkeit-Steuerelemente hinzufügen. Read more about [how to apply recency and frequency controls](../../features/segments/recency-and-frequency.md).
1. Ordnen Sie das Segment einer beliebigen Anzahl von Real-Time Server-to-Server-Zielen zu. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

In diesem Szenario werden die Benutzer, sobald sie mehr als drei Impressionen gesammelt haben, aus diesem Segment entfernt und dieses spezifische kreative Element wird nicht mehr angezeigt.

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

Beachten Sie folgende Aspekte im Zusammenhang mit der Verarbeitung:

* Damit die Echtzeit-Segmentfunktion funktioniert, müssen Sie die gewünschten Segmente realisierungsserver-zu-Server-Zielen zuordnen.
* For devices connected to a device by a [device graph](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), we enforce a four-device limit regarding evaluation and unsegmentation. This limitation is described in [Device Graph Options and Device Unsegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).&#x200B;
* Der Befehl "Unsegmente" wird in einer Stapelverarbeitungsdatei, die alle 24 Stunden an die Ziele gesendet wird, für mehrere Geräte verwendet, die durch das Gerätediagramm verbunden sind.
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md)) to prompt segment evaluation. For traits that have a [!UICONTROL time-to-live (TTL)] value, even if a trait [!DNL TTL] is met, the device will *not* automatically be unsegmented until the device is next seen in real-time.&#x200B; Read more about how to [Set a Trait Expiration Interval](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Important Aspects to Note - Timing {#timing-notes}

Beachten Sie folgende Aspekte im Zusammenhang mit dem Timing:

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!UICONTROL DCS] regions. Read more about our [!UICONTROL DCS] regions [here](../../reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
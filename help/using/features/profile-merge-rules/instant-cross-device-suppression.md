---
description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-title: Sofortige geräteübergreifende Unterdrückung
title: Sofortige geräteübergreifende Unterdrückung
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Sofortige geräteübergreifende Unterdrückung {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] ist die Möglichkeit, Benutzer auf mehreren Geräten zu unterdrücken, die mit ihnen verbunden sind, wenn auf einem dieser Geräte ein bestimmtes Erlebnis auftritt. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.

## Überblick {#overview}

[!UICONTROL Instant Cross-Device Suppression] liefert zwei wichtige Anwendungsfälle: verbesserte Benutzerfreundlichkeit und Medieneffizienz.

* **Verbesserte Benutzerfreundlichkeit**: Benutzer, die Ihr Produkt oder Ihren Dienst bereits erworben haben, sehen nicht dieselben kreativen Elemente wie vor dem Kauf. Stattdessen können Sie Upsell- oder Querverkaufsmeldungen für Produkte oder Dienste anzeigen, von denen Sie wissen, dass sie nicht gekauft wurden.
* **Medieneffizienz**: Optimieren Sie Ihre Kampagnenausgaben, indem Sie eine globale Häufigkeitsgrenze für alle [!DNL DSP]s anwenden. Die Frequenzgrenze kann in Echtzeit für mehrere Geräte eines Benutzers festgelegt werden.

Die technischen Details der Echtzeit-Segmentierung werden in den [Profilzusammenführungsregeln und den Geräten-Aufhebung-Segmentierungsprozessen](merge-rule-unsegment.md)ausführlich beschrieben. Lesen Sie weiter für die praktische Umsetzung der oben beschriebenen Anwendungsfälle.

## Nach Konvertierung kein Targeting vornehmen {#do-not-target-once}

Vergewissern Sie sich, dass Ihre Benutzer, die bereits konvertiert haben (ein Produkt gekauft, ein Abonnement erworben usw.) wird nicht die gleiche Meldung angezeigt wie vor der Konvertierung. Sie können dies mithilfe der [!UICONTROL AND NOT] folgenden Logik abrufen.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND NOT] Logik, wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Konversionsereignis zu definieren, damit das Segment in Echtzeit ausgelöst wird. Erfahren Sie mehr darüber, wie Sie regelbasierte Eigenschaften [erstellen](../traits/create-onboarded-rule-based-traits.md).
2. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Lesen Sie mehr darüber, wie Sie [Server-zu-Server-Zielen](../destinations/add-edit-segments.md)Segmente hinzufügen.

Ihre Besucher qualifizieren sich für das Segment, solange sie nicht konvertiert wurden. Sobald sie sich für die Konversionseigenschaft qualifizieren, folgen sie nicht mehr der Segmentregel und werden sofort aus dem Segment entfernt.

![](assets/and_not_use_case.png)

## Kein Targeting nach x Impressionen {#do-not-target-after-x}

Sie können sicherstellen, dass Ihre Benutzer nicht mit demselben kreativen Element überschwemmt werden, indem Sie die Neuigkeits- und Häufigkeitseinstellungen festlegen. Erstellen Sie in diesem Szenario ein Segment mit zwei Eigenschaften, wie in den folgenden Schritten beschrieben.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND] Logik, wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Impressionsereignis zu definieren, damit das Segment in Echtzeit ausgelöst wird. Erfahren Sie mehr darüber, wie Sie regelbasierte Eigenschaften [erstellen](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Sie können Eigenschaften verwenden [!UICONTROL Actionable Log Files] oder [!UICONTROL Pixel Calls] erstellen, die auf Benutzerimpressionen basieren. Lesen Sie mehr über [Akzeptable Protokolldateien](../../integration/media-data-integration/actionable-log-files.md) und [Pixelaufrufe](../../integration/media-data-integration/impression-data-pixels.md).
2. Wenden Sie Frequenzsteuerungen auf die zweite Eigenschaft an. Auf Wunsch können Sie auch Neuigkeitssteuerelemente hinzufügen. Erfahren Sie mehr darüber, [wie Sie Neuigkeits- und Häufigkeitskontrollen](../segments/recency-and-frequency.md)anwenden.
3. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Lesen Sie mehr darüber, wie Sie [Server-zu-Server-Zielen](../destinations/add-edit-segments.md)Segmente hinzufügen.

In diesem Szenario werden Ihre Benutzer, sobald sie mehr als drei Impressionen gesammelt haben, aus diesem Segment entfernt und sehen diese bestimmten kreativen Elemente nicht mehr.

![](assets/impressions_use_case.png)

## Wichtige Aspekte - Verarbeitung {#processing-notes}

Beachten Sie die folgenden Aspekte im Zusammenhang mit der Verarbeitung:

* Damit die Echtzeit-Funktion zum Entfernen von Segmenten funktioniert, müssen Sie die gewünschten Segmente den Echtzeit-Server-zu-Server-Zielen zuordnen.
* Bei Geräten, die mit einem [Gerätediagramm](profile-link-use-case.md#recommendations)an ein Gerät angeschlossen sind, wird eine Beschränkung für die Auswertung und Aufhebung der Segmentierung auf vier Geräte angewendet. Diese Einschränkung wird unter [Gerätediagrammoptionen und Gerätesegmentierung](merge-rule-unsegment.md#device-graph-options-unsegmentation)beschrieben. &#x200B;
* Der Befehl "Nicht segmentieren"wird bei mehreren Geräten, die über das Gerätediagramm angeschlossen sind, in eine Batch-Datei aufgenommen, die alle 24 Stunden an Ziele gesendet wird.
* Das Gerät muss in Echtzeit (an der [Edge](../../reference/system-components/components-edge.md) ) angezeigt werden, um eine Segmentbewertung in Echtzeit zu veranlassen. Bei Eigenschaften, die eine Eigenschaft aufweisen, [!UICONTROL time-to-live (TTL)] wenn die Eigenschaft erfüllt [!DNL TTL] wird, wird das Gerät automatisch innerhalb von 24 Stunden über die Stapelverarbeitungsdatei aufgehoben. &#x200B; Lesen Sie mehr darüber, wie Sie ein Ablaufintervall für Eigenschaften [festlegen](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Wenn Sie die regelbasierten Eigenschaften [!UICONTROL DCS API] zu integrierten Regeln in Echtzeit verwenden, können Sie das Segmentaufheben mithilfe der [!UICONTROL AND NOT] Logik auslösen. Mehr über das [Senden von Daten an die DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Wichtige Aspekte - Zeit {#timing-notes}

Berücksichtigen Sie die folgenden Aspekte im Zusammenhang mit dem Zeitplan:

* Ein Segment wird für denselben Zeitraum auf der [Edge](../../reference/system-components/components-edge.md) gespeichert, wie ein Geräteprofil auf der gespeichert wird, d. h. 14 Tage seit der letzten Interaktion in Echtzeit [!UICONTROL Edge]. Lesen Sie mehr über die Datenspeicherung in unserer FAQ zur [Datenaufbewahrung](../../faq/faq-privacy.md#data-retention-faq).
* Es dauert etwa 24 Stunden, bis der Vorgang zum Entfernen von Segmenten über [!UICONTROL DCS] Regionen hinweg übertragen wird. Mehr über unsere [!UICONTROL DCS] Regionen [hier](../..//reference/system-components/components-data-collection.md) und [hier](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

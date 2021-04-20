---
description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-title: Sofortige geräteübergreifende Unterdrückung
title: Sofortige geräteübergreifende Unterdrückung
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# Sofortige geräteübergreifende Unterdrückung {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] ist die Möglichkeit, Benutzer auf mehreren Geräten, die mit ihnen verbunden sind, zu unterdrücken, wenn auf einem dieser Geräte ein bestimmtes Erlebnis auftritt. Verwenden Sie die Funktion [!UICONTROL Instant Cross-Device Suppression], um Ihren Benutzern eine konsistente Darstellung auf allen Geräten zu bieten. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.

## Überblick {#overview}

[!UICONTROL Instant Cross-Device Suppression] liefert zwei wichtige Anwendungsfälle: verbesserte Benutzerfreundlichkeit und Medieneffizienz.

* **Verbesserte Benutzerfreundlichkeit**: Benutzer, die Ihr Produkt oder Ihren Dienst bereits erworben haben, sehen nicht dieselben kreativen Elemente wie vor dem Kauf. Stattdessen können Sie Upsell- oder Querverkaufsmeldungen für Produkte oder Dienste anzeigen, von denen Sie wissen, dass sie nicht gekauft wurden.
* **Medieneffizienz**: Optimieren Sie Ihre Ausgaben für Kampagnen, indem Sie eine globale Frequenzgrenze für alle  [!DNL DSP]s anwenden. Die Frequenzgrenze kann in Echtzeit für mehrere Geräte eines Benutzers festgelegt werden.

Die technischen Details der Echtzeit-Segmentierung werden in der Länge unter [Profil Merge Rules and Device Un-Segmentation Processes](merge-rule-unsegment.md) beschrieben. Lesen Sie weiter für die praktische Umsetzung der oben beschriebenen Anwendungsfälle.

## Keine Zielgruppe nach Konvertierung von {#do-not-target-once}

Vergewissern Sie sich, dass Ihre Benutzer, die bereits konvertiert haben (ein Produkt gekauft, ein Abonnement gekauft usw.) wird nicht die gleiche Meldung angezeigt wie vor der Konvertierung. Sie können dies mithilfe der [!UICONTROL AND NOT]-Logik wie folgt abrufen.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND NOT]-Logik, wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Konversions-Ereignis zu definieren, damit das Segment in Echtzeit ausgelöst wird. Erfahren Sie mehr darüber, wie [regelbasierte Eigenschaften erstellen](../traits/create-onboarded-rule-based-traits.md).
2. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Lesen Sie mehr darüber, wie Sie [Server-zu-Server-Zielen](../destinations/add-edit-segments.md) Segmente hinzufügen.

Ihre Besucher qualifizieren sich für das Segment, solange sie nicht konvertiert wurden. Sobald sie sich für die Konversionseigenschaft qualifizieren, folgen sie nicht mehr der Segmentregel und werden sofort aus dem Segment entfernt.

![](assets/and_not_use_case.png)

## Keine Zielgruppe nach x Impressionen {#do-not-target-after-x}

Sie können sicherstellen, dass Ihre Benutzer nicht mit demselben kreativen Element überschwemmt werden, indem Sie die Neuigkeits- und Häufigkeitseinstellungen festlegen. Erstellen Sie in diesem Szenario ein Segment mit zwei Eigenschaften, wie in den folgenden Schritten beschrieben.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND]-Logik, wie in der Abbildung unten dargestellt. Sie müssen ein regelbasiertes Merkmal verwenden, um das Impressionssegment zu definieren, das in Echtzeit ausgelöst werden soll. Erfahren Sie mehr darüber, wie [regelbasierte Eigenschaften erstellen](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Sie können [!UICONTROL Actionable Log Files] oder [!UICONTROL Pixel Calls] verwenden, um Eigenschaften zu erstellen, die auf Benutzerimpressionen basieren. Lesen Sie mehr über [Verfolgbare Protokolldateien](../../integration/media-data-integration/actionable-log-files.md) und [Pixelaufrufe](../../integration/media-data-integration/impression-data-pixels.md).
2. Wenden Sie Frequenzsteuerungen auf die zweite Eigenschaft an. Auf Wunsch können Sie auch Neuigkeitssteuerelemente hinzufügen. Lesen Sie mehr über [Anwenden von Neuigkeits- und Frequenzsteuerelementen](../segments/recency-and-frequency.md).
3. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Lesen Sie mehr darüber, wie Sie [Server-zu-Server-Zielen](../destinations/add-edit-segments.md) Segmente hinzufügen.

In diesem Szenario werden Ihre Benutzer, sobald sie mehr als drei Impressionen gesammelt haben, aus diesem Segment entfernt und sehen diese bestimmten kreativen Elemente nicht mehr.

![](assets/impressions_use_case.png)

## Wichtige Aspekte zu beachten - Verarbeitung von {#processing-notes}

Beachten Sie die folgenden Aspekte im Zusammenhang mit der Verarbeitung:

* Damit die Echtzeit-Funktion zum Entfernen von Segmenten funktioniert, müssen Sie die gewünschten Segmente den Echtzeit-Server-zu-Server-Zielen zuordnen.
* Bei Geräten, die mit einem [Gerätediagramm](profile-link-use-case.md#recommendations) an ein Gerät angeschlossen sind, wird eine Beschränkung für die Auswertung und Aufhebung der Segmentierung auf vier Geräte angewendet. Diese Einschränkung wird unter [Gerätediagrammoptionen und Gerätesegmentierung](merge-rule-unsegment.md#device-graph-options-unsegmentation) beschrieben. &#x200B;
* Der Befehl &quot;Nicht segmentieren&quot;wird bei mehreren Geräten, die über das Gerätediagramm angeschlossen sind, in eine Batch-Datei aufgenommen, die alle 24 Stunden an Ziele gesendet wird.
* Das Gerät muss in Echtzeit gesehen werden (auf dem [Edge](../../reference/system-components/components-edge.md), um eine Segmentbewertung in Echtzeit anzufordern. Bei Eigenschaften, die eine [!UICONTROL time-to-live (TTL)] aufweisen, wenn die Eigenschaft [!DNL TTL] erfüllt ist, wird das Gerät automatisch innerhalb von 24 Stunden über die Stapeldatei aufgehoben. &#x200B; Erfahren Sie mehr darüber, wie Sie ein Ablaufintervall für Eigenschaften [festlegen können.](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
* Wenn Sie [!UICONTROL DCS API] in Echtzeit zu integrierten regelbasierten Eigenschaften verwenden, können Sie das Segment mit der [!UICONTROL AND NOT]-Logik Trigger haben. Lesen Sie mehr über das Senden von Daten an die DCS-API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;[

## Wichtige Aspekte zu beachten - Zeit {#timing-notes}

Berücksichtigen Sie die folgenden Aspekte im Zusammenhang mit dem Zeitplan:

* Ein Segment wird auf dem [Edge](../../reference/system-components/components-edge.md) für denselben Zeitraum wie ein Profil auf dem [!UICONTROL Edge] gespeichert, d. h. 14 Tage seit der letzten Interaktion in Echtzeit. Lesen Sie mehr über die Datenspeicherung in unserer [FAQ zur Datenaufbewahrung](../../faq/faq-privacy.md#data-retention-faq).
* Es dauert etwa 24 Stunden, bis der Vorgang zum Entfernen von Segmenten über [!DNL DCS]-Regionen verteilt wird. Lesen Sie mehr über unsere [!DNL DCS] Regionen [hier](../..//reference/system-components/components-data-collection.md) und [hier](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

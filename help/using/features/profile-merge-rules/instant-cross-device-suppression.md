---
description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-description: Die sofortige geräteübergreifende Unterdrückung ermöglicht das Unterdrücken von Benutzern auf mehreren Geräten, mit denen sie verbunden sind, sobald ein bestimmtes Erlebnis auf einem dieser Geräte eintritt. Mithilfe der sofortigen geräteübergreifenden Unterdrückung können Sie für Ihre Benutzer geräteübergreifend ein konsistentes Erlebnis bereitstellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.
seo-title: Sofortige geräteübergreifende Unterdrückung
title: Sofortige geräteübergreifende Unterdrückung
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profilzusammenführung
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# Sofortige geräteübergreifende Unterdrückung {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] ist die Möglichkeit, Benutzer auf mehreren Geräten zu unterdrücken, die mit ihnen verbunden sind, wenn ein bestimmtes Erlebnis auf einem dieser Geräte auftritt. Verwenden Sie die [!UICONTROL Instant Cross-Device Suppression]-Funktion, um Ihren Benutzern geräteübergreifend ein konsistentes Erlebnis bereitzustellen. Dieses Erlebnis wird durch die Echtzeitfunktionen zum Aufheben der Segmentierung von Audience Manager ermöglicht.

## Überblick {#overview}

[!UICONTROL Instant Cross-Device Suppression] stellt zwei wichtige Anwendungsfälle bereit: verbesserte Benutzerfreundlichkeit und Medieneffizienz.

* **Verbessertes Benutzererlebnis**: Benutzer, die bereits Ihr Produkt oder Ihren Dienst gekauft haben, sehen nicht die gleichen kreativen Inhalte wie vor dem Kauf. Stattdessen können Sie Upsell- oder Querverweise für Produkte oder Services anzeigen, von denen Sie wissen, dass sie nicht gekauft wurden.
* **Medieneffizienz**: Optimieren Sie Ihre Kampagnenausgaben, indem Sie eine globale Frequenzbegrenzung für alle  [!DNL DSP]s anwenden. Die Frequenzlimitierung kann in Echtzeit für mehrere Geräte eines Benutzers aktiviert werden.

Die technischen Details der Aufhebung der Segmentierung in Echtzeit werden in [Regeln zur Profilzusammenführung und Prozesse zur Aufhebung der Gerätesegmentierung](merge-rule-unsegment.md) ausführlich beschrieben. Lesen Sie für die praktische Umsetzung der oben beschriebenen Anwendungsfälle weiter.

## Keine Zielgruppe nach Konvertierung von {#do-not-target-once}

Vergewissern Sie sich, dass Ihre Benutzer, die bereits konvertiert haben (ein Produkt gekauft, ein Abonnement erworben haben usw.) wird nicht die gleiche Nachricht wie vor der Konvertierung angezeigt. Sie können dies mit der [!UICONTROL AND NOT] -Logik wie folgt abrufen.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND NOT]-Logik, wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Konversionsereignis zu definieren, damit das Aufheben der Segmentierung in Echtzeit ausgelöst wird. Erfahren Sie mehr darüber, wie Sie [regelbasierte Eigenschaften erstellen](../traits/create-onboarded-rule-based-traits.md).
2. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Erfahren Sie mehr darüber, wie Sie Segmente zu [Server-zu-Server-Zielen](../destinations/add-edit-segments.md) hinzufügen.

Ihre Besucher qualifizieren sich für das Segment, solange sie nicht konvertiert wurden. Sobald sie sich für die Konversionseigenschaft qualifizieren, folgen sie nicht mehr der Segmentregel und werden sofort aus dem Segment entfernt.

![](assets/and_not_use_case.png)

## Keine Zielgruppenbestimmung nach x Impressionen {#do-not-target-after-x}

Sie können sicherstellen, dass Ihre Benutzer nicht mit demselben kreativen Inhalt überschwemmt werden, indem Sie Neuigkeits- und Häufigkeitskontrollen festlegen. Erstellen Sie in diesem Szenario ein Segment mit zwei Eigenschaften, wie in den folgenden Schritten beschrieben.

1. Erstellen Sie ein Segment mit zwei Eigenschaften und verwenden Sie die [!UICONTROL AND]-Logik, wie in der Abbildung unten dargestellt. Sie müssen eine regelbasierte Eigenschaft verwenden, um das Impressionsereignis zu definieren, damit das Aufheben der Segmentierung in Echtzeit ausgelöst wird. Erfahren Sie mehr darüber, wie Sie [regelbasierte Eigenschaften erstellen](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Sie können [!UICONTROL Actionable Log Files] oder [!UICONTROL Pixel Calls] verwenden, um Eigenschaften basierend auf Benutzerimpressionen zu erstellen. Weitere Informationen zu [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) und [Pixelaufrufe](../../integration/media-data-integration/impression-data-pixels.md).
2. Anwenden von Frequenzsteuerelementen auf die zweite Eigenschaft. Bei Bedarf können Sie auch Neuigkeitskontrollen hinzufügen. Lesen Sie mehr über [Anwenden von Neuigkeits- und Frequenzsteuerelementen](../segments/recency-and-frequency.md).
3. Ordnen Sie das Segment einer beliebigen Anzahl von Echtzeit-Server-zu-Server-Zielen zu. Erfahren Sie mehr darüber, wie Sie Segmente zu [Server-zu-Server-Zielen](../destinations/add-edit-segments.md) hinzufügen.

In diesem Szenario werden Ihre Benutzer, sobald sie mehr als drei Impressionen gesammelt haben, aus diesem Segment entfernt und sehen diesen bestimmten Kreativelement nicht mehr.

![](assets/impressions_use_case.png)

## Wichtige Aspekte zu beachten - Verarbeitung {#processing-notes}

Beachten Sie folgende Aspekte im Zusammenhang mit der Verarbeitung:

* Damit die Funktion zur Aufhebung der Segmentierung in Echtzeit funktioniert, müssen Sie die gewünschten Segmente den Echtzeit-Server-zu-Server-Zielen zuordnen.
* Für Geräte, die über ein [Gerätediagramm](profile-link-use-case.md#recommendations) mit einem Gerät verbunden sind, wird eine Beschränkung von vier Geräten für die Auswertung und Aufhebung der Segmentierung erzwungen. Diese Einschränkung wird unter [Gerätediagrammoptionen und Gerätesegmentierung](merge-rule-unsegment.md#device-graph-options-unsegmentation) beschrieben. &#x200B;
* Der Befehl zum Aufheben der Segmentierung wird in eine Batch-Datei aufgenommen, die alle 24 Stunden an Ziele gesendet wird. Dies gilt für mehrere Geräte, die über das Gerätediagramm verbunden sind.
* Das Gerät muss in Echtzeit (auf dem [Edge](../../reference/system-components/components-edge.md) angezeigt werden, um die Segmentbewertung in Echtzeit zu veranlassen. Bei Eigenschaften mit [!UICONTROL time-to-live (TTL)], wenn die Eigenschaft [!DNL TTL] erfüllt ist, wird die Segmentierung des Geräts über die Batch-Datei automatisch innerhalb von 24 Stunden aufgehoben. &#x200B; Erfahren Sie mehr darüber, wie Sie [ein Ablaufintervall für Eigenschaften festlegen](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Wenn Sie [!UICONTROL DCS API] verwenden, um regelbasierte Eigenschaften in Echtzeit zu integrieren, können Sie die Aufhebung der Segmentierung mit der Verwendung der [!UICONTROL AND NOT]-Logik Trigger haben. Lesen Sie mehr über [Senden von Daten an die DCS-API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Wichtige Aspekte zu beachten - Zeit {#timing-notes}

Beachten Sie die folgenden Aspekte im Zusammenhang mit dem Timing:

* Ein Segment wird im [Edge](../../reference/system-components/components-edge.md) für denselben Zeitraum gespeichert, in dem ein Geräteprofil auf dem [!UICONTROL Edge] gespeichert ist, d. h. 14 Tage seit der letzten Echtzeit-Interaktion. Weitere Informationen zur Datenaufbewahrung finden Sie in den [FAQ zur Datenaufbewahrung](../../faq/faq-privacy.md#data-retention-faq).
* Es dauert etwa 24 Stunden, bis sich der Vorgang zum Aufheben der Segmentierung über [!DNL DCS] -Regionen erstreckt. Mehr über unsere [!DNL DCS] Regionen [hier](../../reference/system-components/components-data-collection.md) und [hier](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

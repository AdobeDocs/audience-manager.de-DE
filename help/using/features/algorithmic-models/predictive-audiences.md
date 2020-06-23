---
description: Predictive Audiencen helfen Ihnen, unbekannte Audiencen mithilfe der Datenwissenschaft in Echtzeit in verschiedene Personengruppen zu klassifizieren.
seo-description: Predictive Audiencen helfen Ihnen, unbekannte Audiencen mithilfe der Datenwissenschaft in Echtzeit in verschiedene Personengruppen zu klassifizieren.
seo-title: Übersicht über Audiencen
solution: Audience Manager
title: Audience Manager Predictive Audiencen
translation-type: tm+mt
source-git-commit: f52321f3621d9eb6b9c5b643a3516f39f35466c2
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 0%

---


# [!UICONTROL Predictive Audiences] Übersicht {#predictive-audiences}

[!UICONTROL Predictive Audiences] hilft Ihnen, eine unbekannte Audience in Echtzeit mithilfe fortschrittlicher Datenwissenstechniken in verschiedene Personen zu klassifizieren.

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

In einem Marketingkontext ist eine Audience ein Segment, das von Besuchern, Benutzern oder potenziellen Käufern definiert wird, die eine bestimmte Reihe von Eigenschaften gemeinsam haben, wie demografische Merkmale, Browsing-Gewohnheiten, Shopping-Geschichte usw.

[!UICONTROL Predictive Audiences] Modelle gehen noch einen Schritt weiter, indem Sie die maschinellen Lernfähigkeiten von Audience Manager nutzen, um unbekannte Audiencen in verschiedene Personen zu klassifizieren. Audience Manager hilft Ihnen dabei, die Tendenz Ihrer unbekannten Erstanbieter-Audience für eine Reihe bekannter Erstanbieter-Audiencen zu berechnen.

Wenn Sie ein [!UICONTROL Predictive Audiences] Modell erstellen, wählen Sie zunächst die Grundeigenschaften oder Segmente aus, nach denen die Audience Ihrer Zielgruppe klassifiziert werden soll. Diese Eigenschaften oder Segmente definieren Ihre Personas.

Während der Bewertungsphase erstellt das Modell ein neues [!UICONTROL Predictive Audiences] Segment für jede Eigenschaft oder jedes Segment, die bzw. das Sie als Basiswert definiert haben. Wenn Audience Manager das nächste Mal einen Besucher aus Ihrer Zielgruppe-Audience sehen, der nicht für eine Persona klassifiziert ist (die für keine Ihrer Grundeigenschaften oder Segmente qualifiziert war), bestimmt das [!UICONTROL Predictive Audiences] Modell, zu welchen der Vorhersagesegmente der Besucher gehören soll, und fügt den Besucher zu diesem Segment hinzu.

Sie können die vom Modell erstellten prädiktiven Segmente auf der [!UICONTROL Segments] Seite identifizieren. Jedes [!UICONTROL Predictive Audiences] Modell hat einen eigenen Ordner unter dem [!UICONTROL Predictive Audiences] Ordner, und Sie können die Segmente jedes Modells sehen, indem Sie auf den Modellordner klicken.

![prognotive-Audiencen-segmente](assets/predictive-audiences-segments.png)

## Nutzungsszenarios {#use-cases}

Damit Sie besser verstehen können, wie und wann Sie diese Funktion verwenden können, [!UICONTROL Predictive Audiences]gibt es einige Anwendungsfälle, die Audience Manager mithilfe dieser Funktion lösen können.

### Verwendungsfall Nr. 1

Als Vermarkter in einer E-Commerce-Firma möchte ich alle meine Web- und mobilen Besucher in verschiedene Kategorien zur Affinität von Marken klassifizieren, damit ich ihre Benutzererfahrung personalisieren kann.

### Verwendungsfall Nr. 2

Als Marketingexperte in einer Media-Firma möchte ich meine nicht authentifizierten Web- und mobilen Besucher nach Lieblingsgenres klassifizieren, damit ich ihnen personalisierte Inhalte über alle Kanal hinweg vorschlagen kann.

### Verwendungsfall 3

Als Anbieter für eine Airline-Firma möchte ich sicherstellen, dass ich meine Audience aufgrund ihres Interesses an Reisezielen klassifiziere, damit ich sie in Echtzeit und innerhalb eines kurzen Retargeting-Fensters bewerben kann.

### Verwendungsfall Nr. 4

Als Anbieter möchte ich meine Erstanbieter-Audience in Echtzeit klassifizieren, damit ich schnell auf Trendnachrichten reagieren kann.

### Verwendungsfall Nr. 5

Als Marketingspezialist möchte ich vorhersagen, in welcher Customer Journey die Besucher meiner Website sich befinden, wie z.B. Entdeckung, Interaktion, Kauf oder Bindung, damit ich sie entsprechend Zielgruppe haben kann.

### Verwendungsfall Nr. 6

Als Medien-Firma möchte ich meine Audience kategorisieren, damit ich meine Werbeflächen zu Premium-Preisen verkaufen kann, während ich meinen Besucher relevante Anzeigen anbieten kann.

## Funktionsweise von [!UICONTROL Predictive Audiences] Modellen {#how-predictive-audiences-models-work}

Wenn Sie ein [!UICONTROL Predictive Audiences] Modell erstellen, gehen Sie drei Schritte durch:

1. Zuerst wählen Sie mindestens zwei Eigenschaften oder zwei Segmente aus, die Ihre Person definieren.
1. Wählen Sie dann eine Eigenschaft oder ein Segment aus, das bzw. das die Audience der Zielgruppe definiert, die Sie klassifizieren möchten.
1. Schließlich wählen Sie einen Namen für das Modell und eine Datenquelle aus, in der die prädiktiven Segmente gespeichert werden.

### Auswahlkriterien für Personas {#selection-personas}

Sie können beliebige Eigenschaften oder Segmente Ihrer Erstanbieter auswählen, um Ihre Personas zu definieren. Für optimale Ergebnisse finden Sie jedoch eine Reihe empfohlener Best Practices:

* Wählen Sie Ihre persönlichen Eigenschaften oder Segmente aus, damit jede Person mindestens hundert [Geräte-IDs](../../reference/ids-in-aam.md)hat.
* Wenn Ihre Eigenschaften auf [geräteübergreifenden IDs](../../reference/ids-in-aam.md)basieren, können Sie sie in Segmente mit [Profil Merge Rules](../profile-merge-rules/merge-rules-overview.md) einschließen, die [Geräte-IDs](../../reference/ids-in-aam.md)verwenden, z. B. [!UICONTROL Device Graph]. Dadurch wird sichergestellt, dass genügend [Geräte-IDs](../../reference/ids-in-aam.md) vorhanden sind, von denen der Algorithmus lernen kann.
* Es wird empfohlen, Eigenschaften oder einfache Segmente für Ihre Personen auszuwählen, die aus 1 bis 3 Eigenschaften bestehen.
* Wählen Sie Grundlinieneigenschaften oder Segmente mit minimaler Überschneidung.
* Achten Sie darauf, dass Sie granulare Eigenschaften in allen digitalen Eigenschaften erfassen.

### Auswahlkriterien für die Audience des Targets {#selection-audience}

Ähnlich wie bei der Personenauswahl sollten Sie Ihre Eigenschaft oder Ihr Segment auswählen, das Ihre Zielgruppe so definiert, dass es Echtzeit-Benutzer mit komplexen Eigenschaften zur Klassifizierung in die richtige Persona hat.

### [!UICONTROL Predictive Audiences] Modellschulungsphase {#model-training}

Bevor der Algorithmus Ihre Erstanbieter-Audience in die richtige Person klassifizieren kann, muss er sich auf Ihre Daten stützen.

Für jede von Ihnen definierte Person analysiert der Algorithmus die jeweilige Audience und bewertet jede beliebige Echtzeit- und/oder Onboard-Eigenschaften-Aktivität für seine Benutzer in den letzten 30 Tagen.
Dieser Schritt findet einmal alle 24 Stunden statt, um Änderungen in Ihrer Erstanbieter-Audience zu berücksichtigen.

### [!UICONTROL Predictive Audiences] Modellklassifizierungsphase {#model-classification}

Wenn ein Besucher, der zur Audience der Zielgruppe gehört, in Echtzeit angezeigt wird, bewertet das Modell, ob der Besucher zu den definierten Personas gehört. Für jeden Besucher, der keiner der Personen angehört, weist das Modell einen persönlichen Qualifikationswert zu.

Bei der Auswertung von Erstanbieter-Audiencen und der Zuweisung von Ergebnissen verwendet das Modell die in Ihrem Konto **[!UICONTROL Profile Merge Rule]** definierte Standardeinstellung. Schließlich wird der Besucher in die Persona eingeteilt, für die er den höchsten Wert erhielt.

![prognotive-Audiencen-graph](assets/predictive-audiences-graph.png)

## Überlegungen und Einschränkungen {#considerations}

>[!IMPORTANT]
> Lesen Sie diesen Abschnitt sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

Berücksichtigen Sie beim Konfigurieren Ihrer [!UICONTROL Predictive Audiences] Modelle die folgenden Überlegungen und Einschränkungen:

* Sie können bis zu 10 [!UICONTROL Predictive Audiences] Modelle erstellen.
* Für jedes Modell können Sie bis zu 50 Basiseigenschaften/Segmente auswählen.
* Zweiter- und Drittanbieterdaten werden derzeit nicht in unterstützt [!UICONTROL Predictive Audiences].
* Die Audience wird nur für Erstanbieter-Audiencen in Echtzeit klassifiziert. Die Klassifizierung der integrierten Erstanbieter-Audiencen wird in zukünftigen Aktualisierungen möglicherweise unterstützt.
   >[!IMPORTANT]
   > Zurzeit wird der Wert [!UICONTROL Total Segment Population] Ihrer prädiktiven Segmente als 0 angezeigt und [Batch-Ausgehende Datenübertragungen](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) werden nicht unterstützt [!UICONTROL Predictive Audiences]. Dieses Verhalten wird sich in einem zukünftigen Update ändern.
* [!UICONTROL Predictive Audiences] führt eine Audience-Classification anhand Ihrer Erstanbieter-Eigenschaften aus allen Erstanbieter-Datenquellen durch.
* Die Segmentbewertung [!UICONTROL Predictive Audiences] verwendet den Standard, den Sie in Ihrem Konto definiert **[!UICONTROL Profile Merge Rule]** haben. Weitere Informationen finden Sie [!UICONTROL Profile Merge Rules] in der [Dokumentation](../profile-merge-rules/merge-rules-overview.md).
* Einige Eigenschaften und Segmente werden nicht als Basis- oder Zielgruppe-Audiencen unterstützt. [!UICONTROL Predictive Audiences] die Modelle können nicht gespeichert werden, wenn eine der folgenden Audiencen als Basislinien oder Zielgruppe ausgewählt wird:
   * Prognostische Eigenschaften und Segmente, die mit Prognoseeigenschaften erstellt wurden;
   * [Adobe Experience Platformen](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) oder Segmente;
   * Algorithmische Eigenschaften;
   * Eigenschaften von Zweitanbietern und Drittanbietern.

## [!UICONTROL Data Export Controls] {#dec}

Prognostische Segmente, die von [!UICONTROL Predictive Audiences] Modellen erstellt wurden, erben die [Datenexportsteuerelemente](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) aus den folgenden Erstanbieter-Datenquellen:

1. Die Erstanbieter-Datenquelle, die Sie beim Erstellen des Modells auswählen.
1. Die Erstanbieter-Datenquellen Ihrer Zielgruppe-Audience. Die Datenexportsteuerelemente der Eigenschaften oder Segmente, aus denen die Audience Ihrer Zielgruppe besteht.

Die neu erstellten Prognosemerkmale und -segmente unterliegen denselben Datenschutzeinschränkungen wie die oben beschriebene Vereinigung der Erstanbieter-Datenquellen.

Eigenschaften mit zusätzlichen Einschränkungen, die nicht Teil der [!UICONTROL Predictive Audiences] Segmentdatenschutzbeschränkungen sind, werden aus der Schulungsphase ausgeschlossen und werden für das Modell nicht relevant.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Die Eigenschaften und Segmente, die Sie für die Klassifizierung &quot;Personas&quot;und &quot;Audience&quot;auswählen, unterliegen den Audience Manager- [Rollenbasierten Zugriffskontrollen](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager können nur Eigenschaften oder Segmente für Personas- und Zielgruppen-Audiencen auswählen, die [zur Ansicht](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)berechtigt sind.

---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Vorhersagekräftige Zielgruppen für Audience Manager
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1470'
ht-degree: 3%

---

# [!UICONTROL Predictive Audiences] Überblick {#predictive-audiences}

[!UICONTROL Predictive Audiences] hilft Ihnen, eine unbekannte Zielgruppe in Echtzeit mithilfe fortschrittlicher Datenwissenschaftstechniken in eindeutige Personas zu klassifizieren.

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

In einem Marketingkontext ist eine Persona ein Zielgruppensegment, das von Besuchern, Benutzern oder potenziellen Käufern definiert wird, die bestimmte Eigenschaften wie demografische Daten, Surfgewohnheiten, Einkaufsverlauf usw. gemeinsam haben.

[!UICONTROL Predictive Audiences]-Modelle gehen noch einen Schritt weiter und ermöglichen es Ihnen, mithilfe der maschinellen Lernfunktionen von Audience Manager unbekannte Zielgruppen in eindeutige Personas zu klassifizieren. Audience Manager hilft Ihnen dabei, die Neigung Ihrer unbekannten Erstanbieterzielgruppe für eine Reihe bekannter Erstanbieterzielgruppen zu berechnen.

Beim Erstellen eines [!UICONTROL Predictive Audiences] -Modells besteht der erste Schritt darin, die Grundlinieneigenschaften oder Segmente auszuwählen, nach denen Ihre Zielgruppe klassifiziert werden soll. Diese Eigenschaften oder Segmente definieren Ihre Rollen.

Während der Auswertungsphase erstellt das Modell ein neues [!UICONTROL Predictive Audiences] -Segment für jede Eigenschaft oder jedes Segment, die bzw. das Sie als Grundlinie definiert haben. Wenn der Audience Manager das nächste Mal einen Besucher aus Ihrer Zielgruppe sieht, der nicht für eine Persona klassifiziert ist (die sich nicht für eine Ihrer Grundlinieneigenschaften oder -segmente qualifiziert hat), bestimmt das Modell [!UICONTROL Predictive Audiences], zu welchem der Vorhersagesegmente der Besucher gehören soll, und fügt den Besucher zu diesem Segment hinzu.

Sie können die vom Modell erstellten prädiktiven Segmente auf der Seite [!UICONTROL Segments] identifizieren. Jedes Modell [!UICONTROL Predictive Audiences] verfügt über einen eigenen Ordner unter dem Ordner [!UICONTROL Predictive Audiences] und Sie können die Segmente der einzelnen Modelle durch Klicken auf den Modellordner sehen.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Nutzungsszenarios {#use-cases}

Um Ihnen zu helfen, besser zu verstehen, wie und wann Sie [!UICONTROL Predictive Audiences] verwenden können, finden Sie hier einige Anwendungsfälle, die Audience Manager mit dieser Funktion lösen können.

### Nutzungsszenario 1

Als Marketer in einem E-Commerce-Unternehmen möchte ich alle meine Web- und mobilen Besucher in verschiedene Kategorien von Markenaffinitäten klassifizieren, damit ich ihr Benutzererlebnis personalisieren kann.

### Nutzungsszenario 2

Als Marketer in einem Medienunternehmen möchte ich meine nicht authentifizierten Web- und Mobilbesucher nach Lieblingsgenres klassifizieren, damit ich ihnen personalisierte Inhalte über alle Kanäle hinweg vorschlagen kann.

### Anwendungsfall 3

Als Advertiser einer Fluggesellschaft möchte ich sicherstellen, dass ich meine Zielgruppe anhand ihres Interesses an Reisezielen klassifiziere, damit ich ihnen in Echtzeit und innerhalb eines kurzen Retargeting-Fensters Werbung machen kann.

### Anwendungsfall 4

Als Advertiser möchte ich meine Erstanbieter-Zielgruppe in Echtzeit klassifizieren, damit ich schnell auf Trendnachrichten reagieren kann.

### Anwendungsfall 5

Als Marketer möchte ich vorhersagen, in welcher Journey-Phase sich meine Website-Besucher befinden, z. B. Entdeckung, Interaktion, Kauf oder Bindung, damit ich sie entsprechend ansprechen kann.

### Anwendungsfall 6

Als Medienunternehmen möchte ich meine Zielgruppe kategorisieren, damit ich meine Werbefläche zu einem Premium-Preis verkaufen und gleichzeitig meinen Besuchern relevante Anzeigen anbieten kann.

## Funktionsweise von [!UICONTROL Predictive Audiences]-Modellen {#how-predictive-audiences-models-work}

Wenn Sie ein [!UICONTROL Predictive Audiences] -Modell erstellen, gehen Sie durch drei Schritte:

1. Zunächst wählen Sie mindestens zwei Eigenschaften oder zwei Segmente aus, die Ihre Personas definieren.
1. Wählen Sie dann eine Eigenschaft oder ein Segment aus, das bzw. das die Zielgruppe definiert, die Sie klassifizieren möchten.
1. Schließlich wählen Sie einen Namen für das Modell, eine Datenquelle, in der die prädiktiven Segmente gespeichert werden, und einen [!UICONTROL Profile Merge Rule] für das Modell.

### Auswahlkriterien für Personas {#selection-personas}

Sie können beliebige Erstanbietereigenschaften oder -segmente auswählen, um Ihre Personas zu definieren. Für optimale Ergebnisse finden Sie jedoch eine Reihe empfohlener Best Practices:

* Wählen Sie Ihre persönlichen Eigenschaften oder Segmente aus, sodass jede Persona mindestens hundert [Geräte-IDs](../../reference/ids-in-aam.md) aufweist.
* Wenn Ihre Eigenschaften auf [geräteübergreifenden IDs](../../reference/ids-in-aam.md) basieren, können Sie sie in Segmente mit [Regeln zur Profilzusammenführung](../profile-merge-rules/merge-rules-overview.md) aufnehmen, die [Geräte-IDs](../../reference/ids-in-aam.md) verwenden, z. B. [!UICONTROL Device Graph]. Dadurch wird sichergestellt, dass genügend [Geräte-IDs](../../reference/ids-in-aam.md) vorhanden sind, aus denen der Algorithmus lernen kann.
* Es wird empfohlen, Eigenschaften oder einfache Segmente für Ihre Personas auszuwählen, die aus 1 bis 3 Eigenschaften bestehen.
* Wählen Sie Grundlinieneigenschaften oder Segmente mit minimaler Überschneidung aus.
* Stellen Sie sicher, dass Sie granulare Eigenschaften in allen Ihren digitalen Eigenschaften erfassen.

### Auswahlkriterien für Target-Zielgruppe {#selection-audience}

Wählen Sie je nach Anwendungsfall eine Zielgruppe ([!UICONTROL trait] oder [!UICONTROL segment]) mit einer signifikanten Echtzeit- und/oder Gesamtpopulation aus, unabhängig davon, ob Sie Benutzer in Echtzeit, im Batch-Modus oder beidem klassifizieren möchten. Ähnlich wie bei der Personenauswahl wird empfohlen, dass Ihre Zielgruppe [!UICONTROL trait] oder [!UICONTROL segment] Benutzer mit Rich-Profilen (Rich-Sets von [!UICONTROL traits]) aufweist.

Analysieren Sie bei der Auswahl der Zielgruppe Ihren Anwendungsfall und entscheiden Sie, welche IDs klassifiziert werden sollen: [!UICONTROL device IDs] oder [!UICONTROL cross-device IDs]. Mit dem [!UICONTROL Profile Merge Rule] , den Sie beim Erstellen des Modells auswählen, werden die Daten definiert, die verwendet werden, um jeden Benutzer in das Prädiktiv [!UICONTROL segments] zu platzieren.

Als Best Practice empfehlen wir, einen [!UICONTROL Profile Merge Rule] auszuwählen, der dieselbe Konfiguration wie Ihre Zielgruppe [!UICONTROL Profile Merge Rule] aufweist oder den Profiltyp (Geräteprofil oder authentifiziertes Profil) Ihrer Zielgruppe enthält.

### [!UICONTROL Predictive Audiences] Modellschulungsphase {#model-training}

Bevor der Algorithmus Ihre Erstanbieter-Audience in die richtigen Personas klassifizieren kann, muss er sich selbst auf Ihre Daten trainieren.

Für jede von Ihnen definierte Persona analysiert der Algorithmus die jeweilige Zielgruppe und wertet die Echtzeit- und/oder integrierten Eigenschaftsaktivitäten für die Benutzer in den letzten 30 Tagen aus.
Dieser Schritt erfolgt einmal alle 24 Stunden, um Änderungen in Ihrer Erstanbieter-Zielgruppe zu berücksichtigen.

### [!UICONTROL Predictive Audiences] Modellklassifizierungsphase {#model-classification}

Bei der Echtzeit- und Batch-Zielgruppen-Classification prüft das Modell zunächst, ob ein Benutzer zur Zielgruppe gehört. Wenn sich der Benutzer für die Zielgruppe qualifiziert und keiner der Personas angehört, weist das Modell ihm eine Qualifizierungsbewertung für die Persona zu.

Beim Auswerten von Erstanbieterzielgruppen und Zuweisen von Werten verwendet das Modell die in Ihrem Konto definierte Standardeinstellung **[!UICONTROL Profile Merge Rule]**. Schließlich wird der Besucher in die Persona klassifiziert, für die er den höchsten Wert erhielt.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Überlegungen und Einschränkungen {#considerations}

>[!IMPORTANT]
> Lesen Sie diesen Abschnitt sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

Beachten Sie beim Konfigurieren Ihrer [!UICONTROL Predictive Audiences] -Modelle die folgenden Überlegungen und Einschränkungen:

* Sie können bis zu 10 [!UICONTROL Predictive Audiences] Modelle erstellen.
* Für jedes Modell können Sie bis zu 50 Basiseigenschaften/Segmente auswählen.
* Zweit- und Drittanbieterdaten werden derzeit in [!UICONTROL Predictive Audiences] nicht unterstützt.
* [!UICONTROL Predictive Audiences] führt eine Zielgruppen-Classification anhand Ihrer Erstanbieter-Eigenschaften aus allen Erstanbieter-Datenquellen durch.
* Die Segmentauswertung für [!UICONTROL Predictive Audiences] verwendet die **[!UICONTROL Profile Merge Rule]**, die Sie bei der Modellerstellung auswählen. Weitere Informationen zu [!UICONTROL Profile Merge Rules] finden Sie in der entsprechenden [Dokumentation](../profile-merge-rules/merge-rules-overview.md).
* Einige Eigenschaften und Segmente werden nicht als Grundlinien- oder Zielgruppen unterstützt. [!UICONTROL Predictive Audiences] -Modelle können nicht gespeichert werden, wenn eine der folgenden Optionen als Grundlinien- oder Zielgruppen ausgewählt wird:
   * Prädiktive Eigenschaften und Segmente, die mit prädiktiven Eigenschaften erstellt wurden;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) -Eigenschaften oder -Segmente;
   * Algorithmische Eigenschaften;
   * Eigenschaften von Zweit- und Drittanbietern.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] kann nicht in [!UICONTROL Audience Lab] verwendet werden.

## [!UICONTROL Data Export Controls] {#dec}

Von [!UICONTROL Predictive Audiences] -Modellen erstellte prädiktive Segmente übernehmen die [Datenexportkontrollen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) aus den folgenden Erstanbieter-Datenquellen:

1. Die Erstanbieter-Datenquelle, die Sie beim Erstellen des Modells auswählen.
1. Die Erstanbieter-Datenquellen Ihrer Zielgruppe. Insbesondere die Datenexportkontrollen der [!UICONTROL traits] oder [!UICONTROL segments], aus denen Ihre Zielgruppe besteht.
1. Die [Datenexportkontrollen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) der [!UICONTROL Profile Merge Rule], die Sie für das Modell ausgewählt haben.

Das neu erstellte Prädiktiv [!UICONTROL traits] und [!UICONTROL segments] weist dieselben Datenschutzbeschränkungen auf wie die Vereinigung der zuvor beschriebenen Erstanbieter-Datenquellen.

Eigenschaften mit zusätzlichen Einschränkungen, die nicht Teil der Datenschutzbeschränkungen für [!UICONTROL Predictive Audiences] -Segmente sind, werden aus der Schulungsphase ausgeschlossen und werden nicht für das Modell relevant.

## [!UICONTROL Profile Merge Rules] {#pmr}

Allen prädiktiven Segmenten wird der [!UICONTROL Profile Merge Rule] zugewiesen, den Sie beim Erstellen des Modells ausgewählt haben. Der von Ihnen ausgewählte [!UICONTROL Profile Merge Rule] ist aus den folgenden Gründen wichtig:

* Sie definiert, welche Geräte und/oder authentifizierten Profile bei der Analyse des einflussreichen [!UICONTROL traits] durch das Modell berücksichtigt werden sollen, wenn ein Benutzer in eine Vorhersage [!UICONTROL segment] klassifiziert wird.
* Sie legt fest, welche [!UICONTROL trait]-Typen (Geräteebene oder geräteübergreifend) während des Trainings-Schritts des Modells verwendet und als einflussreiche [!UICONTROL traits] angezeigt werden sollen. Prädiktiv [!UICONTROL segments] sind Untergruppen Ihrer Zielgruppe.
   * Wenn es sich bei der Zielgruppe um ein Segment handelt, empfehlen wir, für das Modell denselben [!UICONTROL Profile Merge Rule] wie für das Modell zu wählen, das Ihrer Zielgruppe zugewiesen ist, oder einen [!UICONTROL Profile Merge Rule] , der den Profiltyp Ihrer Zielgruppe enthält.
   * Wenn es sich bei der Zielgruppe um [!UICONTROL trait] handelt, empfehlen wir, eine [!UICONTROL Profile Merge Rule] auszuwählen, die auf denselben Datentyp wie die Zielgruppeneigenschaft zugreifen kann (entweder Geräteprofildaten oder geräteübergreifende Profildaten).
* [!UICONTROL Profile Merge Rules] Die Verwendung der Optionen [!UICONTROL Current Authenticated Profiles] und [!UICONTROL No Device Profile] wird nur für die Echtzeit-Zielgruppen-Classification unterstützt. Weitere Informationen finden Sie unter [Optionen für Profilzusammenführungsregeln definiert](../profile-merge-rules/merge-rule-definitions.md).

Wenn Sie einen [!UICONTROL Profile Merge Rule] auswählen, der sowohl Gerätedaten als auch geräteübergreifende Daten verwendet, wird die Anzahl von [!UICONTROL traits] maximiert, die für die Modellschulung und Benutzerklassifizierung in die Vorhersagefunktion [!UICONTROL segments] verwendet werden könnte.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Die Eigenschaften und Segmente, die Sie für Personas und Zielgruppen-Classifications auswählen, unterliegen dem Audience Manager [Rollenbasierte Zugriffskontrollen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager können nur Eigenschaften oder Segmente für Personas und Zielgruppen auswählen, wenn sie über [Berechtigung zum Anzeigen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions) verfügen.

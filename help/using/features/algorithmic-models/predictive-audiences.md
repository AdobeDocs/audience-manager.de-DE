---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-title: Vorhersagekräftige Zielgruppen – Überblick
solution: Audience Manager
title: Vorhersagekräftige Zielgruppen für Audience Manager
feature: Algorithmische Modelle
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] Überblick {#predictive-audiences}

[!UICONTROL Predictive Audiences] hilft Ihnen, eine unbekannte Zielgruppe in Echtzeit mithilfe fortschrittlicher datenwissenschaftlicher Techniken in eindeutige Personas zu klassifizieren.

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

In einem Marketing-Kontext ist eine Persona ein Zielgruppensegment, das durch Besucher, Benutzer oder potenzielle Käufer definiert wird, die bestimmte Eigenschaften wie demografische Daten, Surfgewohnheiten, Einkaufsverlauf usw. gemeinsam haben.

[!UICONTROL Predictive Audiences]-Modelle gehen noch einen Schritt weiter und ermöglichen es Ihnen, mithilfe der maschinellen Lernfunktionen von Audience Manager unbekannte Zielgruppen in eindeutige Personas zu klassifizieren. Mit Audience Manager können Sie dies erreichen, indem Sie die Neigung Ihrer unbekannten Erstanbieterzielgruppe für eine Reihe bekannter Erstanbieterzielgruppen berechnen.

Wenn Sie ein [!UICONTROL Predictive Audiences]-Modell erstellen, wählen Sie zunächst die Grundlinieneigenschaften oder Segmente aus, nach denen Ihre Zielgruppe klassifiziert werden soll. Diese Eigenschaften oder Segmente definieren Ihre Rollen.

Während der Auswertungsphase erstellt das Modell ein neues [!UICONTROL Predictive Audiences]-Segment für jede Eigenschaft oder jedes Segment, die bzw. das Sie als Grundlinie definiert haben. Wenn der Audience Manager das nächste Mal einen Besucher aus Ihrer Zielgruppe sieht, der nicht für eine Persona klassifiziert ist (die sich nicht für eine Ihrer Grundlinieneigenschaften oder -segmente qualifiziert hat), bestimmt das [!UICONTROL Predictive Audiences]-Modell, zu welchem der Vorhersagesegmente der Besucher gehören soll, und fügt den Besucher diesem Segment hinzu.

Sie können die vom Modell erstellten prädiktiven Segmente auf der Seite [!UICONTROL Segments] identifizieren. Jedes [!UICONTROL Predictive Audiences]-Modell hat einen eigenen Ordner unter dem Ordner [!UICONTROL Predictive Audiences] und Sie können die Segmente der einzelnen Modelle durch Klicken auf den Modellordner anzeigen.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Nutzungsszenarios {#use-cases}

Um Ihnen zu helfen, besser zu verstehen, wie und wann Sie [!UICONTROL Predictive Audiences] verwenden können, finden Sie hier einige Anwendungsfälle, die Audience Manager mit dieser Funktion lösen können.

### Anwendungsfall 1

Als Marketer in einem E-Commerce-Unternehmen möchte ich alle meine Web- und mobilen Besucher in verschiedene Kategorien von Markenaffinitäten klassifizieren, damit ich ihr Benutzererlebnis personalisieren kann.

### Anwendungsfall 2

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

Wenn Sie ein [!UICONTROL Predictive Audiences]-Modell erstellen, gehen Sie durch drei Schritte:

1. Zunächst wählen Sie mindestens zwei Eigenschaften oder zwei Segmente aus, die Ihre Personas definieren.
1. Wählen Sie dann eine Eigenschaft oder ein Segment aus, das bzw. das die Zielgruppe definiert, die Sie klassifizieren möchten.
1. Schließlich wählen Sie einen Namen für das Modell, eine Datenquelle, die die Vorhersagesegmente speichert, und einen [!UICONTROL Profile Merge Rule] für das Modell.

### Auswahlkriterien für Personas {#selection-personas}

Sie können beliebige Erstanbietereigenschaften oder -segmente auswählen, um Ihre Rollen zu definieren. Für optimale Ergebnisse finden Sie jedoch eine Reihe empfohlener Best Practices:

* Wählen Sie Ihre persönlichen Eigenschaften oder Segmente aus, sodass jede Persona mindestens hundert [Geräte-IDs](../../reference/ids-in-aam.md) aufweist.
* Wenn Ihre Eigenschaften auf [geräteübergreifenden IDs](../../reference/ids-in-aam.md) basieren, können Sie sie in Segmente mit [Profilzusammenführungsregeln](../profile-merge-rules/merge-rules-overview.md) einschließen, die [Geräte-IDs](../../reference/ids-in-aam.md) verwenden, z. B. [!UICONTROL Device Graph]. Dadurch wird sichergestellt, dass genügend [Geräte-IDs](../../reference/ids-in-aam.md) vorhanden sind, aus denen der Algorithmus lernen kann.
* Es wird empfohlen, Eigenschaften oder einfache Segmente für Ihre Personas auszuwählen, die aus 1 bis 3 Eigenschaften bestehen.
* Wählen Sie Grundlinieneigenschaften oder Segmente mit minimaler Überschneidung aus.
* Stellen Sie sicher, dass Sie granulare Eigenschaften in allen Ihren digitalen Eigenschaften erfassen.

### Auswahlkriterien für Zielgruppen {#selection-audience}

Wählen Sie je nach Anwendungsfall eine Zielgruppe ([!UICONTROL trait] oder [!UICONTROL segment]) mit einer signifikanten Echtzeit- und/oder Gesamtpopulation aus, unabhängig davon, ob Sie Benutzer in Echtzeit, im Batch-Modus oder beidem klassifizieren möchten. Ähnlich wie bei der Personenauswahl empfehlen wir, dass Ihre Zielgruppe [!UICONTROL trait] oder [!UICONTROL segment] Benutzer mit Rich-Profilen (umfangreiche Sets von [!UICONTROL traits]) aufweist.

Analysieren Sie bei der Auswahl der Zielgruppe Ihren Anwendungsfall und entscheiden Sie, welche IDs klassifiziert werden sollen: [!UICONTROL device IDs] oder [!UICONTROL cross-device IDs]. Das [!UICONTROL Profile Merge Rule], das Sie beim Erstellen des Modells auswählen, definiert die Daten, die verwendet werden, um jeden Benutzer in das Prädiktiv [!UICONTROL segments] zu platzieren.

Als Best Practice wird empfohlen, ein [!UICONTROL Profile Merge Rule] auszuwählen, das dieselbe Konfiguration wie Ihre Zielgruppe [!UICONTROL Profile Merge Rule] aufweist oder den Profiltyp (Geräteprofil oder authentifiziertes Profil) Ihrer Zielgruppe enthält.

### [!UICONTROL Predictive Audiences] Modellschulung  {#model-training}

Bevor der Algorithmus Ihre Erstanbieter-Audience in die richtigen Personas klassifizieren kann, muss er sich selbst auf Ihre Daten trainieren.

Für jede von Ihnen definierte Persona analysiert der Algorithmus die jeweilige Zielgruppe und wertet die Echtzeit- und/oder integrierten Eigenschaftsaktivitäten für die Benutzer in den letzten 30 Tagen aus.
Dieser Schritt erfolgt einmal alle 24 Stunden, um Änderungen in Ihrer Erstanbieter-Zielgruppe zu berücksichtigen.

### [!UICONTROL Predictive Audiences] Modellklassifizierungsphase  {#model-classification}

Bei der Echtzeit- und Batch-Zielgruppen-Classification prüft das Modell zunächst, ob ein Benutzer zur Zielgruppe gehört. Wenn sich der Benutzer für die Zielgruppe qualifiziert und keiner der Personas angehört, weist das Modell ihm eine Qualifizierungsbewertung für die Persona zu.

Beim Auswerten von Erstanbieterzielgruppen und Zuweisen von Werten verwendet das Modell die in Ihrem Konto definierte Standardeinstellung **[!UICONTROL Profile Merge Rule]**. Schließlich wird der Besucher in die Persona klassifiziert, für die er den höchsten Punktstand erzielt hat.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Überlegungen und Einschränkungen {#considerations}

>[!IMPORTANT]
> Lesen Sie diesen Abschnitt sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

Beachten Sie beim Konfigurieren Ihrer [!UICONTROL Predictive Audiences]-Modelle die folgenden Überlegungen und Einschränkungen:

* Sie können bis zu 10 [!UICONTROL Predictive Audiences]-Modelle erstellen.
* Für jedes Modell können Sie bis zu 50 Basiseigenschaften/Segmente auswählen.
* Zweit- und Drittanbieterdaten werden derzeit in [!UICONTROL Predictive Audiences] nicht unterstützt.
* [!UICONTROL Predictive Audiences] führt eine Zielgruppen-Classification anhand Ihrer Erstanbieter-Eigenschaften aus allen Erstanbieter-Datenquellen durch.
* Die Segmentbewertung für [!UICONTROL Predictive Audiences] verwendet die **[!UICONTROL Profile Merge Rule]**, die Sie bei der Modellerstellung auswählen. Weitere Informationen zu [!UICONTROL Profile Merge Rules] finden Sie in der dedizierten [Dokumentation](../profile-merge-rules/merge-rules-overview.md).
* Einige Eigenschaften und Segmente werden nicht als Grundlinien- oder Zielgruppen unterstützt. [!UICONTROL Predictive Audiences] -Modelle können nicht gespeichert werden, wenn Sie eine der folgenden Optionen als Grundlinien- oder Zielgruppen auswählen:
   * Prädiktive Eigenschaften und Segmente, die mit prädiktiven Eigenschaften erstellt wurden;
   * [Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Platform-Eigenschaften oder -Segmente;
   * Algorithmische Eigenschaften;
   * Eigenschaften von Zweit- und Drittanbietern.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] kann nicht in verwendet werden  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Von [!UICONTROL Predictive Audiences]-Modellen erstellte prädiktive Segmente übernehmen die [Datenexportkontrollen](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) aus den folgenden Erstanbieter-Datenquellen:

1. Die Erstanbieter-Datenquelle, die Sie beim Erstellen des Modells auswählen.
1. Die Erstanbieter-Datenquellen Ihrer Zielgruppe. Insbesondere die Datenexportkontrollen der [!UICONTROL traits] oder [!UICONTROL segments], aus denen Ihre Zielgruppe besteht.
1. Die [Datenexportkontrollen](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) der [!UICONTROL Profile Merge Rule], die Sie für das Modell ausgewählt haben.

Die neu erstellten Prognosen [!UICONTROL traits] und [!UICONTROL segments] weisen dieselben Datenschutzbeschränkungen auf wie die Vereinigung der oben beschriebenen Erstanbieter-Datenquellen.

Eigenschaften mit zusätzlichen Einschränkungen, die nicht Teil der [!UICONTROL Predictive Audiences]-Segmentdatenschutzbeschränkungen sind, werden aus der Schulungsphase ausgeschlossen und werden nicht für das Modell relevant.

## [!UICONTROL Profile Merge Rules] {#pmr}

Allen prädiktiven Segmenten wird die [!UICONTROL Profile Merge Rule] zugewiesen, die Sie beim Erstellen des Modells ausgewählt haben. Der von Ihnen ausgewählte [!UICONTROL Profile Merge Rule] ist aus folgenden Gründen wichtig:

* Sie definiert, welche Geräte und/oder authentifizierten Profile bei der Analyse des einflussreichen [!UICONTROL traits] durch das Modell berücksichtigt werden sollen, zum Zeitpunkt der Klassifizierung eines Benutzers in ein Prädiktiv [!UICONTROL segment].
* Sie legt fest, welche [!UICONTROL trait]-Typen (Geräteebene oder geräteübergreifend) während des Trainings-Schritts des Modells verwendet und als einflussreiche [!UICONTROL traits] angezeigt werden sollen. Prädiktive [!UICONTROL segments] sind Untergruppen Ihrer Zielgruppe.
   * Wenn es sich bei der Zielgruppe um ein Segment handelt, empfehlen wir, für das Modell dasselbe [!UICONTROL Profile Merge Rule] wie für das Ihrer Zielgruppe zugewiesene Modell oder ein [!UICONTROL Profile Merge Rule] auszuwählen, das den Profiltyp Ihrer Zielgruppe enthält.
   * Wenn es sich bei der Zielgruppe um eine [!UICONTROL trait] handelt, empfehlen wir, ein [!UICONTROL Profile Merge Rule] auszuwählen, das auf denselben Datentyp wie die Zielgruppeneigenschaft zugreifen kann (entweder Geräteprofildaten oder geräteübergreifende Profildaten).
* [!UICONTROL Profile Merge Rules] Die Verwendung der  [!UICONTROL Current Authenticated Profiles] Optionen und  [!UICONTROL No Device Profile] wird nur für die Echtzeit-Zielgruppen-Classification unterstützt. Weitere Informationen finden Sie unter [Optionen für Profilzusammenführungsregeln definiert](../profile-merge-rules/merge-rule-definitions.md).

Wenn Sie ein [!UICONTROL Profile Merge Rule] auswählen, das sowohl Gerätedaten als auch geräteübergreifende Daten verwendet, wird die Anzahl der [!UICONTROL traits] maximiert, die für die Modellschulung und Benutzerklassifizierung in das Prädiktiv [!UICONTROL segments] verwendet werden können.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Die Eigenschaften und Segmente, die Sie für Personas und Zielgruppen-Classifications auswählen, unterliegen dem Audience Manager [Rollenbasierte Zugriffskontrollen](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager können nur Eigenschaften oder Segmente für Personas und Zielgruppen auswählen, wenn sie über [Berechtigung zum Anzeigen](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions) verfügen.

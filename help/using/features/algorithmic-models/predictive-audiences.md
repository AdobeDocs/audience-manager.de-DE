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

# [!UICONTROL Predictive Audiences] {#predictive-audiences}

[!UICONTROL Predictive Audiences] können Sie mithilfe fortschrittlicher Datenwissenschafts-Techniken eine unbekannte Zielgruppe in Echtzeit in verschiedene Personas klassifizieren.

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Verwendung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um Rechtsberatung zu erhalten.

In einem Marketing-Kontext ist eine Rolle ein Zielgruppensegment, das von Besuchern, Benutzern oder potenziellen Käufern definiert wird, die bestimmte Eigenschaften wie Demografie, Browser-Gewohnheiten, Einkaufsverlauf usw. gemeinsam haben.

[!UICONTROL Predictive Audiences]-Modelle gehen noch einen Schritt weiter und ermöglichen es Ihnen, mithilfe der maschinellen Lernfunktionen von Audience Manager unbekannte Zielgruppen in eindeutige Personas zu klassifizieren. Audience Manager hilft Ihnen dabei, die Neigung Ihrer unbekannten Erstanbieter-Zielgruppe für eine Reihe bekannter Erstanbieter-Zielgruppen zu berechnen.

Wenn Sie ein [!UICONTROL Predictive Audiences] erstellen, besteht der erste Schritt darin, die grundlegenden Eigenschaften oder Segmente auszuwählen, nach denen Ihre Zielgruppe klassifiziert werden soll. Diese Eigenschaften oder Segmente definieren Ihre Personas.

Während der Auswertungsphase erstellt das Modell für jedes Merkmal oder Segment, das Sie als Baseline definiert haben, ein neues [!UICONTROL Predictive Audiences]. Wenn der Audience Manager das nächste Mal einen Besucher aus Ihrer Zielgruppe sieht, der nicht für eine Rolle klassifiziert ist (sich für keines Ihrer grundlegenden Merkmale oder Segmente qualifiziert hat), bestimmt das [!UICONTROL Predictive Audiences], zu welchem der Prognosesegmente der Besucher gehören soll, und fügt den Besucher diesem Segment hinzu.

Die vom Modell erstellten prädiktiven Segmente können Sie auf der Seite [!UICONTROL Segments] identifizieren. Jedes [!UICONTROL Predictive Audiences] hat einen eigenen Ordner unter dem [!UICONTROL Predictive Audiences] Ordner, und Sie können die Segmente jedes Modells sehen, indem Sie auf den Modellordner klicken.

![predictive-audiences-segments](assets/predictive-audiences-segments.png)

## Nutzungsszenarios {#use-cases}

Damit Sie besser verstehen können, wie und wann Sie [!UICONTROL Predictive Audiences] verwenden können, finden Sie hier einige Anwendungsfälle, die Audience Manager-Kunden mit dieser Funktion lösen können.

### Anwendungsfall #1

Als Marketing-Experte in einem E-Commerce-Unternehmen möchte ich alle meine Web- und Mobile-Besucher in verschiedene markenaffine Kategorien einteilen, damit ich ihr Benutzererlebnis personalisieren kann.

### Anwendungsfall #2

Als Marketing-Experte in einem Medienunternehmen möchte ich meine nicht authentifizierten Web- und mobilen Besucher nach bevorzugten Genres klassifizieren, damit ich ihnen personalisierte Inhalte über alle Kanäle hinweg vorschlagen kann.

### Anwendungsfall #3

Als Werbetreibender für eine Fluggesellschaft möchte ich sicherstellen, dass ich meine Zielgruppe nach ihrem Interesse an Reisezielen klassifiziere, damit ich sie in Echtzeit, innerhalb eines kurzen Retargeting-Fensters, bewerben kann.

### Anwendungsfall #4

Als Werbetreibende möchte ich mein Erstanbieter-Publikum in Echtzeit klassifizieren, damit ich schnell auf Trendnachrichten reagieren kann.

### Anwendungsfall #5

Journey Als Marketingexperte möchte ich vorhersagen, in welcher Phase sich meine Website-Besucher befinden, z. B. in der Phase der Kundenanalyse, der Interaktion, des Kaufs oder der Kundenbindung, damit ich sie entsprechend ansprechen kann.

### Anwendungsfall #6

Als Medienunternehmen möchte ich mein Publikum kategorisieren, damit ich meine Werbefläche zu Premium-Preisen verkaufen und meinen Besuchern relevante Anzeigen anbieten kann.

## Funktionsweise [!UICONTROL Predictive Audiences] Datenmodellen {#how-predictive-audiences-models-work}

Beim Erstellen eines [!UICONTROL Predictive Audiences] gehen Sie drei Schritte durch:

1. Zunächst wählen Sie mindestens zwei Eigenschaften oder zwei Segmente aus, die Ihre Personas definieren.
1. Wählen Sie dann eine Eigenschaft oder ein Segment aus, das die Zielgruppe definiert, die Sie klassifizieren möchten.
1. Schließlich wählen Sie einen Namen für das Modell, eine Datenquelle, in der die prädiktiven Segmente gespeichert werden, und eine [!UICONTROL Profile Merge Rule] für das Modell aus.

### Auswahlkriterien für Personas {#selection-personas}

Sie können beliebige Erstanbieter-Eigenschaften oder Segmente auswählen, um Ihre Personas zu definieren. Um jedoch optimale Ergebnisse zu erzielen, gibt es hier eine Reihe empfohlener Best Practices:

* Wählen Sie Ihre persönlichen Eigenschaften oder Segmente so aus, dass jede Rolle mindestens einige hundert [Geräte-IDs“ ](../../reference/ids-in-aam.md).
* Wenn Ihre Eigenschaften auf [geräteübergreifenden IDs](../../reference/ids-in-aam.md) basieren, können Sie sie in Segmente mit [Profilzusammenführungsregeln](../profile-merge-rules/merge-rules-overview.md) einschließen, die [Geräte-IDs](../../reference/ids-in-aam.md) verwenden, z. B. [!UICONTROL Device Graph]. Dadurch wird sichergestellt, dass genügend [Geräte-IDs](../../reference/ids-in-aam.md) vorhanden sind, aus denen der Algorithmus lernen kann.
* Wir empfehlen die Auswahl von Eigenschaften oder einfachen Segmenten für Ihre Personas, die aus 1 bis 3 Eigenschaften bestehen.
* Wählen Sie Grundlinien-Eigenschaften oder Segmente mit minimaler Überschneidung aus.
* Stellen Sie sicher, dass Sie in Ihren digitalen Eigenschaften granulare Eigenschaften erfassen.

### Auswahlkriterien für die Zielgruppe {#selection-audience}

Wählen Sie je nach Anwendungsfall, ob Sie Benutzer in Echtzeit, im Batch oder in beiden klassifizieren möchten, eine Zielgruppe ([!UICONTROL trait] oder [!UICONTROL segment]) mit einer signifikanten Echtzeit- und/oder Gesamtpopulation aus. Ähnlich wie bei der Persönlichkeitsauswahl empfehlen wir, dass Ihre Zielgruppe [!UICONTROL trait] oder [!UICONTROL segment] Benutzer mit umfangreichen Profilen (umfangreiche [!UICONTROL traits]) hat.

Analysieren Sie bei der Auswahl der Zielgruppe Ihren Anwendungsfall und entscheiden Sie, welche IDs Sie klassifizieren möchten: [!UICONTROL device IDs] oder [!UICONTROL cross-device IDs]. Die [!UICONTROL Profile Merge Rule], die Sie beim Erstellen des Modells auswählen, definiert die Daten, die verwendet werden, um jeden Benutzer in den prädiktiven [!UICONTROL segments] zu platzieren.

Als Best Practice empfehlen wir die Auswahl einer [!UICONTROL Profile Merge Rule], die dieselbe Konfiguration wie Ihre Zielgruppen-[!UICONTROL Profile Merge Rule] hat oder einen, der den Profiltyp (Geräteprofil oder authentifiziertes Profil) Ihrer Zielgruppe enthält.

### Trainingsphase des [!UICONTROL Predictive Audiences] {#model-training}

Bevor der Algorithmus Ihre Erstanbieter-Zielgruppe in die richtigen Personas klassifizieren kann, muss er sich selbst mit Ihren Daten trainieren.

Für jede Rolle, die Sie definieren, analysiert der Algorithmus seine jeweilige Zielgruppe und wertet jede Echtzeit- und/oder integrierte Eigenschaftsaktivität für seine Benutzer in den letzten 30 Tagen aus.
Dieser Schritt findet alle 24 Stunden statt, um Änderungen in Ihrer Erstanbieter-Zielgruppe zu berücksichtigen.

### Klassifizierungsphase des [!UICONTROL Predictive Audiences] {#model-classification}

Für die Echtzeit- und Batch-Zielgruppenklassifizierung prüft das Modell zunächst, ob ein Benutzer zur Zielgruppe gehört. Wenn sich der Benutzer für die Zielgruppe qualifiziert und zu keiner der Rollen gehört, weist das Modell ihm einen Persona-Qualifizierungswert zu.

Beim Auswerten von Erstanbieter-Zielgruppen und Zuweisen von Bewertungen verwendet das Modell die in Ihrem Konto definierte **[!UICONTROL Profile Merge Rule]**. Schließlich wird der Besucher in die Rolle klassifiziert, für die er die höchste Punktzahl erhalten hat.

![predictive-audiences-graph](assets/predictive-audiences-graph.png)

## Aspekte und Einschränkungen {#considerations}

>[!IMPORTANT]
> Lesen Sie diesen Abschnitt sorgfältig durch, bevor Sie mit der Implementierungsphase fortfahren.

Beachten Sie beim Konfigurieren Ihrer [!UICONTROL Predictive Audiences] die folgenden Überlegungen und Einschränkungen:

* Sie können bis zu 10 [!UICONTROL Predictive Audiences] erstellen.
* Für jedes Modell können Sie bis zu 50 Basiseigenschaften/Segmente auswählen.
* Zweit- und Drittanbieterdaten werden derzeit in [!UICONTROL Predictive Audiences] nicht unterstützt.
* [!UICONTROL Predictive Audiences] führt eine Zielgruppenklassifizierung anhand der Eigenschaften Ihrer Erstanbieter aus allen Ihren Erstanbieter-Datenquellen durch.
* Die Segmentauswertung für [!UICONTROL Predictive Audiences] verwendet die **[!UICONTROL Profile Merge Rule]**, die Sie bei der Modellerstellung auswählen. Weitere Informationen zu [!UICONTROL Profile Merge Rules] finden Sie in der dedizierten [Dokumentation](../profile-merge-rules/merge-rules-overview.md).
* Einige Eigenschaften und Segmente werden nicht als Baselines oder Zielgruppen unterstützt. [!UICONTROL Predictive Audiences] Modelle können nicht gespeichert werden, wenn eine der folgenden Optionen als Baselines oder Zielgruppen ausgewählt wird:
   * Prädiktive Eigenschaften und Segmente, die mit prädiktiven Eigenschaften erstellt wurden;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Eigenschaften oder Segmente;
   * Algorithmische Eigenschaften;
   * Zweit- und Drittanbieter-Eigenschaften.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] kann nicht in [!UICONTROL Audience Lab] verwendet werden.

## [!UICONTROL Data Export Controls] {#dec}

Prädiktive Segmente, die von [!UICONTROL Predictive Audiences] erstellt werden, erben [Datenexportsteuerelemente](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=de) aus den folgenden Erstanbieter-Datenquellen:

1. Die First-Party-Datenquelle, die Sie beim Erstellen des Modells auswählen.
1. Die Erstanbieter-Datenquellen Ihrer Zielgruppe. Insbesondere die Datenexportsteuerelemente der [!UICONTROL traits] oder [!UICONTROL segments], aus denen Ihre Zielgruppe besteht.
1. Die [Datenexportsteuerelemente](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=de) der [!UICONTROL Profile Merge Rule], die Sie für das Modell ausgewählt haben.

Die neu erstellten prädiktiven [!UICONTROL traits] und [!UICONTROL segments] weisen dieselben Datenschutzbeschränkungen auf wie die oben beschriebene Vereinigung der Erstanbieter-Datenquellen.

Eigenschaften mit zusätzlichen Einschränkungen, die nicht zu den [!UICONTROL Predictive Audiences] Segmentdatenschutzbeschränkungen gehören, werden aus der Trainingsphase ausgeschlossen und haben keinen Einfluss auf das Modell.

## [!UICONTROL Profile Merge Rules] {#pmr}

Allen prädiktiven Segmenten wird der [!UICONTROL Profile Merge Rule] zugewiesen, den Sie beim Erstellen des Modells ausgewählt haben. Die von Ihnen gewählte [!UICONTROL Profile Merge Rule] ist aus den folgenden Gründen wichtig:

* Sie definiert, welche Geräte und/oder authentifizierten Profile bei der Analyse der einflussreichen [!UICONTROL traits] durch das Modell zum Zeitpunkt der Klassifizierung eines Benutzers in eine prädiktive [!UICONTROL segment] berücksichtigt werden sollen.
* Sie legt fest, welche [!UICONTROL trait] (Geräteebene oder geräteübergreifende Ebene) während des Modelltrainings verwendet und als einflussreiche [!UICONTROL traits] angezeigt werden sollen. Prädiktive [!UICONTROL segments] sind Untergruppen Ihrer Zielgruppe.
   * Wenn es sich bei der Zielgruppe um ein Segment handelt, empfehlen wir, denselben [!UICONTROL Profile Merge Rule] für das Modell auszuwählen, der Ihrer Zielgruppe zugewiesen wurde, oder einen [!UICONTROL Profile Merge Rule], der den Profiltyp Ihrer Zielgruppe enthält.
   * Wenn es sich bei der Zielgruppe um eine [!UICONTROL trait] handelt, empfehlen wir die Auswahl einer [!UICONTROL Profile Merge Rule], die auf denselben Datentyp wie die Eigenschaft der Zielgruppe zugreifen kann (entweder Geräteprofildaten oder geräteübergreifende Profildaten).
* [!UICONTROL Profile Merge Rules] Verwendung der Optionen [!UICONTROL Current Authenticated Profiles] und [!UICONTROL No Device Profile] werden nur für die Echtzeit-Zielgruppenklassifizierung unterstützt. Weitere Informationen finden Sie [Optionen für Profilzusammenführungsregeln definiert](../profile-merge-rules/merge-rule-definitions.md).

Durch die Auswahl eines [!UICONTROL Profile Merge Rule], der sowohl Gerätedaten als auch geräteübergreifende Daten verwendet, wird die Anzahl der [!UICONTROL traits] maximiert, die für das Modelltraining und die Benutzerklassifizierung in der prädiktiven [!UICONTROL segments] verwendet werden können.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Die Eigenschaften und Segmente, die Sie für Personas und Zielgruppenklassifizierung auswählen, unterliegen den Audience Manager [Rollenbasierten Zugriffssteuerungen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html?lang=de).

Audience Manager können nur Eigenschaften oder Segmente für Personas und Zielgruppen auswählen, für die sie über [Berechtigung zum Anzeigen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html?lang=de#wild-card-permissions) verfügen.

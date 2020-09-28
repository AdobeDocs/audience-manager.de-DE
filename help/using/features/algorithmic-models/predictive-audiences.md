---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-title: Vorhersagekräftige Zielgruppen – Überblick
solution: Audience Manager
title: Vorhersagekräftige Zielgruppen für Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 1df6e8a76e5eae85483820926474ebc8633d5591
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 7%

---


# [!UICONTROL Predictive Audiences] Überblick {#predictive-audiences}

[!UICONTROL Predictive Audiences] hilft Ihnen, eine unbekannte Audience in Echtzeit mithilfe fortschrittlicher Datenwissenstechniken in verschiedene Personen zu klassifizieren.

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

In einem Marketing-Kontext ist eine Persona ein Zielgruppensegment, das durch Besucher, Benutzer oder potenzielle Käufer definiert wird, die bestimmte Eigenschaften wie demografische Daten, Surfgewohnheiten, Einkaufsverlauf usw. gemeinsam haben.

[!UICONTROL Predictive Audiences]-Modelle gehen noch einen Schritt weiter und ermöglichen es Ihnen, mithilfe der maschinellen Lernfunktionen von Audience Manager unbekannte Zielgruppen in eindeutige Personas zu klassifizieren. Mit Audience Manager können Sie dies erreichen, indem Sie die Neigung Ihrer unbekannten Erstanbieterzielgruppe für eine Reihe bekannter Erstanbieterzielgruppen berechnen.

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
1. Schließlich wählen Sie einen Namen für das Modell, eine Datenquelle, in der die prädiktiven Segmente gespeichert werden, und eine [!UICONTROL Profile Merge Rule] für das Modell.

### Auswahlkriterien für Personas {#selection-personas}

Sie können beliebige Eigenschaften oder Segmente Ihrer Erstanbieter auswählen, um Ihre Personas zu definieren. Für optimale Ergebnisse finden Sie jedoch eine Reihe empfohlener Best Practices:

* Wählen Sie Ihre persönlichen Eigenschaften oder Segmente aus, damit jede Person mindestens hundert [Geräte-IDs](../../reference/ids-in-aam.md)hat.
* Wenn Ihre Eigenschaften auf [geräteübergreifenden IDs](../../reference/ids-in-aam.md)basieren, können Sie sie in Segmente mit [Profil Merge Rules](../profile-merge-rules/merge-rules-overview.md) einschließen, die [Geräte-IDs](../../reference/ids-in-aam.md)verwenden, z. B. [!UICONTROL Device Graph]. Dadurch wird sichergestellt, dass genügend [Geräte-IDs](../../reference/ids-in-aam.md) vorhanden sind, von denen der Algorithmus lernen kann.
* Es wird empfohlen, Eigenschaften oder einfache Segmente für Ihre Personas auszuwählen, die aus 1 bis 3 Eigenschaften bestehen.
* Wählen Sie Grundlinieneigenschaften oder Segmente mit minimaler Überschneidung.
* Achten Sie darauf, dass Sie granulare Eigenschaften in allen digitalen Eigenschaften erfassen.

### Auswahlkriterien für die Audience der Zielgruppe {#selection-audience}

Ähnlich wie bei der Personenauswahl sollten Sie Ihre Audience auswählen [!UICONTROL trait] oder [!UICONTROL segment] die Ihre Zielgruppe so definiert, dass sie Echtzeit-Benutzer mit Rich-Set von Benutzern [!UICONTROL traits]zur Klassifizierung in die richtige Persona hat.

Wenn Sie die Audience &quot;Zielgruppe&quot;auswählen, analysieren Sie Ihren Anwendungsfall und entscheiden Sie, welche IDs klassifiziert werden sollen: [!UICONTROL device IDs] oder [!UICONTROL cross-device IDs]. Die Daten, [!UICONTROL Profile Merge Rule] die Sie beim Erstellen des Modells auswählen, werden verwendet, um jeden Benutzer in die Vorhersage zu setzen [!UICONTROL segments].

Als Best Practice empfehlen wir, eine Zielgruppe [!UICONTROL Profile Merge Rule] zu wählen, die dieselbe Konfiguration wie Ihre Audience hat [!UICONTROL Profile Merge Rule]oder die den Profil-Typ (Profil des Geräts oder authentifiziertes Profil) Ihrer Zielgruppe-Audience enthält.

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

* Sie können bis zu 10 [!UICONTROL Predictive Audiences]-Modelle erstellen.
* Für jedes Modell können Sie bis zu 50 Basiseigenschaften/Segmente auswählen.
* Zweiter- und Drittanbieterdaten werden derzeit nicht in unterstützt [!UICONTROL Predictive Audiences].
* Die Audience wird nur für Erstanbieter-Audiencen in Echtzeit klassifiziert. Die Klassifizierung der integrierten Erstanbieter-Audiencen wird in zukünftigen Aktualisierungen möglicherweise unterstützt.
   >[!IMPORTANT]
   > Wenn Sie einem regulären Segment eine prädiktive Eigenschaft hinzufügen, wird daraus ein prädiktives Segment. Folglich sind alle verknüpften Profil nicht segmentiert.

   >[!IMPORTANT]
   > Zurzeit können prädiktive Segmente nur in Echtzeit-Zielen aktiviert werden. Die [!UICONTROL Total Segment Population] und [!UICONTROL Addressable Audience] die prädiktiven Segmente werden als 0 angezeigt, und für [Batch-ausgehende Datenübertragungen](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) werden sie nicht unterstützt [!UICONTROL Predictive Audiences]. Dieses Verhalten wird sich in einem zukünftigen Update ändern.
* [!UICONTROL Predictive Audiences] führt eine Audience-Classification anhand Ihrer Erstanbieter-Eigenschaften aus allen Erstanbieter-Datenquellen durch.
* Die Segmentbewertung [!UICONTROL Predictive Audiences] verwendet die **[!UICONTROL Profile Merge Rule]** , die Sie bei der Modellerstellung auswählen. Weitere Informationen finden Sie [!UICONTROL Profile Merge Rules] in der [Dokumentation](../profile-merge-rules/merge-rules-overview.md).
* Einige Eigenschaften und Segmente werden nicht als Basis- oder Zielgruppe-Audiencen unterstützt. [!UICONTROL Predictive Audiences] die Modelle können nicht gespeichert werden, wenn eine der folgenden Audiencen als Basislinien oder Zielgruppe ausgewählt wird:
   * Prognostische Eigenschaften und Segmente, die mit Prognoseeigenschaften erstellt wurden;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) -Eigenschaften oder -Segmente;
   * Algorithmische Eigenschaften;
   * Eigenschaften von Zweitanbietern und Drittanbietern.

## [!UICONTROL Data Export Controls] {#dec}

Prognostische Segmente, die von [!UICONTROL Predictive Audiences] Modellen erstellt wurden, erben die [Datenexportsteuerelemente](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) aus den folgenden Erstanbieter-Datenquellen:

1. Die Erstanbieter-Datenquelle, die Sie beim Erstellen des Modells auswählen.
1. Die Erstanbieter-Datenquellen Ihrer Zielgruppe-Audience. Insbesondere die Datenexportsteuerelemente der oder [!UICONTROL traits][!UICONTROL segments] , aus denen die Audience der Zielgruppe besteht.
1. Die [Datenexportsteuerelemente](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) des [!UICONTROL Profile Merge Rule] , das Sie für das Modell ausgewählt haben.

Das neu erstellte Predictive [!UICONTROL traits] und [!UICONTROL segments] werden dieselben Datenschutzeinschränkungen wie die oben beschriebene Vereinigung der Erstanbieter-Datenquellen haben.

Eigenschaften mit zusätzlichen Einschränkungen, die nicht Teil der [!UICONTROL Predictive Audiences] Segmentdatenschutzbeschränkungen sind, werden aus der Schulungsphase ausgeschlossen und werden für das Modell nicht relevant.

## [!UICONTROL Profile Merge Rules] {#pmr}

Allen prädiktiven Segmenten wird die [!UICONTROL Profile Merge Rule] , die Sie beim Erstellen des Modells ausgewählt haben, zugewiesen. Die [!UICONTROL Profile Merge Rule] Auswahl ist aus folgenden Gründen wichtig:

* Es definiert, welche Geräte und/oder authentifizierten Profil bei der Analyse des Einflussbereichs berücksichtigt werden sollten [!UICONTROL traits]- zum Zeitpunkt der Klassifizierung eines Benutzers in eine Vorhersage [!UICONTROL segment].
* Es bestimmt, welche [!UICONTROL trait] Typen (Geräteebene oder Geräteebene) während des Modellschulungsschritts verwendet und als einflussreich aufgezeigt werden sollten [!UICONTROL traits]. Prognosen [!UICONTROL segments] sind Untergruppen Ihrer Zielgruppe Audience.
   * Wenn es sich bei der Zielgruppe-Audience um ein Segment handelt, empfehlen wir Ihnen, für das Modell das gleiche auszuwählen wie für die Zielgruppe-Audience oder für ein Profil, das den -Typ Ihrer Zielgruppe-Audience enthält. [!UICONTROL Profile Merge Rule] [!UICONTROL Profile Merge Rule]
   * Wenn es sich bei der Audience der Zielgruppe um eine Audience handelt, sollten Sie eine Option auswählen, [!UICONTROL trait][!UICONTROL Profile Merge Rule] die auf denselben Datentyp zugreifen kann wie die Eigenschaft der Zielgruppe (Profil- oder geräteübergreifende Profil-Daten).

Wenn Sie [!UICONTROL Profile Merge Rule] Gerätedaten und geräteübergreifende Daten verwenden, wird die Anzahl der Daten maximiert, die für Modellschulungen und die Benutzerklassifizierung in der Prognose verwendet werden könnten [!UICONTROL traits] [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

Die Eigenschaften und Segmente, die Sie für die Klassifizierung &quot;Personas&quot;und &quot;Audience&quot;auswählen, unterliegen den Audience Manager- [Rollenbasierten Zugriffskontrollen](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager können nur Eigenschaften oder Segmente für Personas- und Zielgruppen-Audiencen auswählen, die [zur Ansicht](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions)berechtigt sind.

---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-title: Vorhersagekräftige Zielgruppen – Überblick
solution: Audience Manager
title: Vorhersagekräftige Zielgruppen für Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 3c39ef38d2833d5d706641f70649251d79b2ee6f
workflow-type: tm+mt
source-wordcount: '1511'
ht-degree: 8%

---


# [!UICONTROL Predictive Audiences] Überblick {#predictive-audiences}

[!UICONTROL Predictive Audiences] hilft Ihnen, eine unbekannte Audience in Echtzeit mithilfe fortschrittlicher Datenwissenstechniken in verschiedene Personen zu klassifizieren.

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

In einem Marketing-Kontext ist eine Persona ein Zielgruppensegment, das durch Besucher, Benutzer oder potenzielle Käufer definiert wird, die bestimmte Eigenschaften wie demografische Daten, Surfgewohnheiten, Einkaufsverlauf usw. gemeinsam haben.

[!UICONTROL Predictive Audiences]-Modelle gehen noch einen Schritt weiter und ermöglichen es Ihnen, mithilfe der maschinellen Lernfunktionen von Audience Manager unbekannte Zielgruppen in eindeutige Personas zu klassifizieren. Mit Audience Manager können Sie dies erreichen, indem Sie die Neigung Ihrer unbekannten Erstanbieterzielgruppe für eine Reihe bekannter Erstanbieterzielgruppen berechnen.

Wenn Sie ein [!UICONTROL Predictive Audiences]-Modell erstellen, wählen Sie zunächst die Grundlinieneigenschaften oder Segmente aus, nach denen die Audience Ihrer Zielgruppe klassifiziert werden soll. Diese Eigenschaften oder Segmente definieren Ihre Personas.

Während der Bewertungsphase erstellt das Modell ein neues [!UICONTROL Predictive Audiences]-Segment für jede Eigenschaft oder jedes Segment, die bzw. das Sie als Ausgangswert definiert haben. Wenn Audience Manager das nächste Mal einen Besucher aus Ihrer Zielgruppe-Audience sehen, der nicht für eine Persona klassifiziert ist (die sich nicht für eine Ihrer Basiseigenschaften oder -segmente qualifiziert hat), bestimmt das [!UICONTROL Predictive Audiences]-Modell, zu welchem der Vorhersagesegmente der Besucher gehören soll, und fügt den Besucher zu diesem Segment hinzu.

Sie können die vom Modell erstellten prädiktiven Segmente auf der Seite [!UICONTROL Segments] identifizieren. Jedes [!UICONTROL Predictive Audiences]-Modell hat einen eigenen Ordner unter dem Ordner [!UICONTROL Predictive Audiences], und Sie können die Segmente jedes Modells sehen, indem Sie auf den Modellordner klicken.

![prognotive-Audiencen-segmente](assets/predictive-audiences-segments.png)

## Nutzungsszenarios {#use-cases}

Damit Sie besser verstehen können, wie und wann Sie [!UICONTROL Predictive Audiences] verwenden können, gibt es einige Anwendungsfälle, die Audience Manager mit dieser Funktion lösen können.

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

## Funktionsweise von [!UICONTROL Predictive Audiences]-Modellen {#how-predictive-audiences-models-work}

Wenn Sie ein [!UICONTROL Predictive Audiences]-Modell erstellen, führen Sie drei Schritte durch:

1. Zuerst wählen Sie mindestens zwei Eigenschaften oder zwei Segmente aus, die Ihre Person definieren.
1. Wählen Sie dann eine Eigenschaft oder ein Segment aus, das bzw. das die Audience der Zielgruppe definiert, die Sie klassifizieren möchten.
1. Schließlich wählen Sie einen Namen für das Modell, eine Datenquelle, in der die prädiktiven Segmente gespeichert werden, und eine [!UICONTROL Profile Merge Rule] für das Modell.

### Auswahlkriterien für Personas {#selection-personas}

Sie können beliebige Eigenschaften oder Segmente Ihrer Erstanbieter auswählen, um Ihre Personas zu definieren. Für optimale Ergebnisse finden Sie jedoch eine Reihe empfohlener Best Practices:

* Wählen Sie Ihre persönlichen Eigenschaften oder Segmente aus, damit jede Person mindestens hundert [Geräte-IDs](../../reference/ids-in-aam.md) hat.
* Wenn Ihre Eigenschaften auf [geräteübergreifenden IDs](../../reference/ids-in-aam.md) basieren, können Sie sie in Segmente mit [Profil-Zusammenführungsregeln](../profile-merge-rules/merge-rules-overview.md) einschließen, die [Geräte-IDs](../../reference/ids-in-aam.md) verwenden, z. B. [!UICONTROL Device Graph]. Dadurch wird sichergestellt, dass genügend [Geräte-IDs](../../reference/ids-in-aam.md) vorhanden sind, von denen der Algorithmus lernen kann.
* Es wird empfohlen, Eigenschaften oder einfache Segmente für Ihre Personas auszuwählen, die aus 1 bis 3 Eigenschaften bestehen.
* Wählen Sie Grundlinieneigenschaften oder Segmente mit minimaler Überschneidung.
* Achten Sie darauf, dass Sie granulare Eigenschaften in allen digitalen Eigenschaften erfassen.

### Auswahlkriterien für die Audience der Zielgruppe {#selection-audience}

Je nach Anwendungsfall können Sie eine Audience ([!UICONTROL trait] oder [!UICONTROL segment]) auswählen, die eine signifikante Echtzeit- und/oder Gesamtpopulation aufweist, unabhängig davon, ob Sie Benutzer in Echtzeit, im Stapel oder beides klassifizieren möchten. Ähnlich wie bei der Personenauswahl empfehlen wir, dass Ihre Zielgruppe-Audience [!UICONTROL trait] oder [!UICONTROL segment] Benutzer mit Rich-Profilen (Rich-Sätze von [!UICONTROL traits]) hat.

Wenn Sie die Audience &quot;Zielgruppe&quot;auswählen, analysieren Sie Ihren Anwendungsfall und entscheiden Sie, welche IDs klassifiziert werden sollen: [!UICONTROL device IDs] oder [!UICONTROL cross-device IDs]. Das [!UICONTROL Profile Merge Rule], das Sie beim Erstellen des Modells auswählen, definiert die Daten, die verwendet werden, um jeden Benutzer in das Prädiktiv [!UICONTROL segments] einzufügen.

Als Best Practice empfehlen wir, ein [!UICONTROL Profile Merge Rule] auszuwählen, das dieselbe Konfiguration wie Ihre Zielgruppe Audience [!UICONTROL Profile Merge Rule] hat oder das den Profil-Typ (Profil des Geräts oder authentifiziertes Profil) Ihrer Zielgruppe-Audience enthält.

### [!UICONTROL Predictive Audiences] Modellschulungsphase  {#model-training}

Bevor der Algorithmus Ihre Erstanbieter-Audience in die richtige Person klassifizieren kann, muss er sich auf Ihre Daten stützen.

Für jede von Ihnen definierte Person analysiert der Algorithmus die jeweilige Audience und bewertet jede beliebige Echtzeit- und/oder Onboard-Eigenschaften-Aktivität für seine Benutzer in den letzten 30 Tagen.
Dieser Schritt findet einmal alle 24 Stunden statt, um Änderungen in Ihrer Erstanbieter-Audience zu berücksichtigen.

### [!UICONTROL Predictive Audiences] Modellklassifizierungsphase  {#model-classification}

Bei der Audience in Echtzeit und im Stapel prüft das Modell zunächst, ob ein Benutzer zur Audience der Zielgruppe gehört. Wenn sich der Benutzer für die Audience der Zielgruppe qualifiziert und keiner der Personen angehört, weist das Modell ihnen einen persönlichen Qualifikationswert zu.

Bei der Auswertung von Erstanbieter-Audiencen und der Zuweisung von Ergebnissen verwendet das Modell die in Ihrem Konto definierte Standardeinstellung **[!UICONTROL Profile Merge Rule]**. Schließlich wird der Besucher in die Persona eingeteilt, für die er den höchsten Wert erhielt.

![prognotive-Audiencen-graph](assets/predictive-audiences-graph.png)

## Überlegungen und Einschränkungen {#considerations}

>[!IMPORTANT]
> Lesen Sie diesen Abschnitt sorgfältig durch, bevor Sie zur Implementierungsphase übergehen.

Beachten Sie beim Konfigurieren Ihrer [!UICONTROL Predictive Audiences]-Modelle die folgenden Überlegungen und Einschränkungen:

* Sie können bis zu 10 [!UICONTROL Predictive Audiences]-Modelle erstellen.
* Für jedes Modell können Sie bis zu 50 Basiseigenschaften/Segmente auswählen.
* Zweit- und Drittanbieterdaten werden derzeit in [!UICONTROL Predictive Audiences] nicht unterstützt.
* [!UICONTROL Predictive Audiences] führt eine Audience-Classification anhand Ihrer Erstanbieter-Eigenschaften aus allen Erstanbieter-Datenquellen durch.
* Die Segmentbewertung für [!UICONTROL Predictive Audiences] verwendet das **[!UICONTROL Profile Merge Rule]**, das Sie bei der Modellerstellung auswählen. Weitere Informationen zu [!UICONTROL Profile Merge Rules] finden Sie in der dedizierten [Dokumentation](../profile-merge-rules/merge-rules-overview.md).
* Einige Eigenschaften und Segmente werden nicht als Basis- oder Zielgruppe-Audiencen unterstützt. [!UICONTROL Predictive Audiences] die Modelle können nicht gespeichert werden, wenn eine der folgenden Audiencen als Basislinien oder Zielgruppe ausgewählt wird:
   * Prognostische Eigenschaften und Segmente, die mit Prognoseeigenschaften erstellt wurden;
   * [Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Plattformen oder Segmente;
   * Algorithmische Eigenschaften;
   * Eigenschaften von Zweitanbietern und Drittanbietern.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] kann nicht angewendet werden  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Prognostische Segmente, die von [!UICONTROL Predictive Audiences]-Modellen erstellt wurden, erben die [Datenexportsteuerelemente](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) aus den folgenden Erstanbieter-Datenquellen:

1. Die Erstanbieter-Datenquelle, die Sie beim Erstellen des Modells auswählen.
1. Die Erstanbieter-Datenquellen Ihrer Zielgruppe-Audience. Insbesondere die Datenexportsteuerelemente von [!UICONTROL traits] oder [!UICONTROL segments], aus denen die Audience Ihrer Zielgruppe besteht.
1. Die [Datenexportsteuerelemente](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) der [!UICONTROL Profile Merge Rule], die Sie für das Modell ausgewählt haben.

Die neu erstellten Prognosen [!UICONTROL traits] und [!UICONTROL segments] weisen dieselben Datenschutzeinschränkungen auf wie die oben beschriebene Vereinigung der Erstanbieter-Datenquellen.

Eigenschaften mit zusätzlichen Einschränkungen, die nicht Teil der [!UICONTROL Predictive Audiences]-Segmentdatenschutzbeschränkungen sind, werden aus der Schulungsphase ausgeschlossen und werden für das Modell nicht relevant.

## [!UICONTROL Profile Merge Rules] {#pmr}

Allen prädiktiven Segmenten wird das [!UICONTROL Profile Merge Rule] zugewiesen, das Sie beim Erstellen des Modells ausgewählt haben. Das [!UICONTROL Profile Merge Rule], das Sie auswählen, ist aus folgenden Gründen wichtig:

* Es definiert, welche Geräte und/oder authentifizierten Profil bei der Analyse des einflussreichen [!UICONTROL traits]-Modells zum Zeitpunkt der Klassifizierung eines Benutzers in ein vorhersagbares [!UICONTROL segment] berücksichtigt werden sollten.
* Es bestimmt, welche [!UICONTROL trait]-Typen (Geräteebene oder geräteübergreifend) während des Modellschulungsschritts verwendet und als einflussreich [!UICONTROL traits] angezeigt werden sollen. Predictive [!UICONTROL segments] sind Untergruppen Ihrer Zielgruppe Audience.
   * Wenn es sich bei der Audience der Zielgruppe um ein Segment handelt, empfehlen wir, für das Modell dasselbe [!UICONTROL Profile Merge Rule] auszuwählen wie für das Modell, das der Audience Ihrer Zielgruppe zugewiesen ist, oder ein [!UICONTROL Profile Merge Rule] auszuwählen, das den Profil-Typ Ihrer Zielgruppe-Audience enthält.
   * Wenn es sich bei der Audience der Zielgruppe um eine [!UICONTROL trait] handelt, sollten Sie ein [!UICONTROL Profile Merge Rule] auswählen, das auf denselben Datentyp zugreifen kann wie die Eigenschaft der Zielgruppe-Audience (Profil- oder geräteübergreifende Profil-Daten).
* [!UICONTROL Profile Merge Rules] Die Verwendung der  [!UICONTROL Current Authenticated Profiles] und- [!UICONTROL No Device Profile] Optionen wird nur für die Echtzeitklassifizierung der Audience unterstützt. Weitere Informationen finden Sie unter [Optionen für Profil-Zusammenführungsregeln definiert](../profile-merge-rules/merge-rule-definitions.md).

Wenn Sie ein [!UICONTROL Profile Merge Rule] auswählen, das sowohl Gerätedaten als auch geräteübergreifende Daten verwendet, wird die Anzahl der [!UICONTROL traits] maximiert, die für Modellschulungen und Benutzerklassifizierungen in das Vorhersagekriterium [!UICONTROL segments] verwendet werden könnten.

## [!UICONTROL Role-Based Access Controls] {#rbac}

Die Eigenschaften und Segmente, die Sie für die Klassifizierung &quot;Personas&quot;und &quot;Audience&quot;auswählen, unterliegen dem Audience Manager [Rollenbasierte Zugriffskontrollen](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html).

Audience Manager können nur Eigenschaften oder Segmente für Personas- und Zielgruppen-Audiencen auswählen, die [Berechtigungen für Ansicht](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions) besitzen.

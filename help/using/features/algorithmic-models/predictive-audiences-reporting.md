---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-title: Berichte zu vorhersagekräftigen Zielgruppen
solution: Audience Manager
title: Berichte zu vorhersagekräftigen Zielgruppen
feature: Algorithmische Modelle
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 6%

---

# Berichte zu vorhersagekräftigen Zielgruppen

Nachdem Sie ein [!UICONTROL Predictive Audiences]-Modell gespeichert haben, beginnt der Audience Manager damit, es zu trainieren. Innerhalb weniger Stunden beginnt das berechnete Modell mit der Analyse von Zielgruppen auf den [Datenerfassungsservern](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Die Berichterstellung ist am folgenden Tag verfügbar.

Um die Ergebnisse Ihrer [!UICONTROL Predictive Audiences]-Classification anzuzeigen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** und klicken Sie auf Ihr Modell in der Liste.

Verwenden Sie die Filteroptionen auf der linken Seite, um nach dem Modellnamen zu suchen oder die Ergebnisse nach Modelltyp zu filtern.

![predictive-audiences-filter](assets/predictive-audiences-filter-models.png)

Die Modelltabelle zeigt die folgenden Informationen an:

* **[!UICONTROL ID]**: die Modell-ID jedes Modell in Ihrem Audience Manager-Konto eindeutig identifiziert;
* **[!UICONTROL Name]**: den Namen, den Sie im Modellerstellungsschritt angegeben haben;
* **[!UICONTROL Description]**: die Beschreibung, die Sie im Schritt zur Modellerstellung angegeben haben;
* **[!UICONTROL Model Type]**: Typ der einzelnen Modelle ([!UICONTROL Look-Alike Modeling] oder  [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: Status der einzelnen Modelle:
   * **[!UICONTROL Pending]**: das Modell initialisiert wird und in Kürze Ergebnisse liefern wird;
   * **[!UICONTROL Active]**: das Modell wird erfolgreich ausgeführt und liefert Ergebnisse;
   * **[!UICONTROL Warning]**: Das Modell konnte aufgrund unzureichender Daten keine Ergebnisse erzielen (d. h. niedrige Grundlinien-Population, keine Benutzerprofile).
   * **[!UICONTROL Error]**: Das Modell konnte nicht ausgeführt werden. Wenden Sie sich an Ihren Kundenbetreuer bei der Adobe.

## Modellübersichtsbericht{#model-report}

Sobald Sie ein Modell auswählen, wird dessen Berichterstellungsseite geladen. Oben auf der Seite können Sie die 5 größten prädiktiven Segmente sehen, die auf einer 1-tägigen Echtzeit-Realisierung basieren und nach denen das Modell Ihre Zielgruppe klassifiziert hat. Die Kategorie **[!UICONTROL Other]** enthält die übrigen Personas, die nicht zu den 5 größten Vorhersagesegmenten gehörten.

Audience Manager zeigt sowohl ein farbkodiertes Ringdiagramm als auch ein Timeline-Diagramm für Ihr [!UICONTROL Predictive Audiences] an.

Wenn Sie oben auf der Seite auf die Personas-Tabs klicken, werden diese aus der Grafik und dem Diagramm entfernt.

Das Ringdiagramm zeigt Ihnen eine personalbasierte Aufschlüsselung Ihrer Zielgruppe, während das Diagramm den 1-tägigen Echtzeit-Populationstrend Ihrer prädiktiven Segmente über die letzten 6 Tage anzeigt.

Wenn der Modellstatus [!UICONTROL Pending], [!UICONTROL Warning] oder [!UICONTROL Error] lautet, wird anstelle der Diagramme der Modellstatus angezeigt.

![smart-persona-report](assets/predictive-audiences-report.png)

Die Berichtstabelle enthält für jedes [!UICONTROL Predictive Audiences]-Segment die folgenden Informationen.

1. **[!UICONTROL SEGMENT ID]**: die Segment-ID des automatisch erstellten Segments, das mit jeder Persona verknüpft ist;
1. **[!UICONTROL NAME]**: den Namen der Person;
1. **[!UICONTROL STATUS]**: Status des  [!UICONTROL Predictive Audiences] Segments:
   * **[!UICONTROL Succeeded]**: Benutzer werden in dieses Segment klassifiziert;
   * **[!UICONTROL Pending]**: das Segment wird noch initialisiert;
   * **[!UICONTROL Insufficient Training Data]**: Benutzer werden aufgrund unzureichender Daten nicht in dieses Segment klassifiziert. Die Grundgesamtheit ist zu niedrig und bietet nicht genügend Daten, um davon zu lernen.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Die Anzahl der Segmentrealisierungen für jede Persona in den letzten 24 Stunden.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: Der Prozentsatz der Segmentrealisierungen für jede Persona in den letzten 24 Stunden aus der Gesamtmodellpopulation.

## Einflussreiche Eigenschaften{#influential-traits}

[!UICONTROL Influential Traits] sind Eigenschaften, die der  [!UICONTROL Predictive Audiences] Algorithmus als die stärksten Prädikatoren zur Bestimmung der persönlichen Klassifizierung eines Besuchers erkannt hat.

Das Symbol zeigt an, ob das Vorhandensein der Eigenschaft die Wahrscheinlichkeit des Benutzers erhöht (+) oder verringert (-), der zur ausgewählten Rolle gehört.

Um die einflussreichen Eigenschaften für alle Ihre Personas anzuzeigen, klicken Sie auf [!UICONTROL View All Influential Traits].

Das Fenster [!UICONTROL Influential Traits] enthält für jede Person des ausgewählten Modells die folgenden Informationen:

![einflussreiche Eigenschaften](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: die Eigenschafts-ID jeder einflussreichen Eigenschaft für die ausgewählte Persona;
1. **[!UICONTROL NAME]**: den Namen jeder einflussreichen Eigenschaft für die ausgewählte Rolle;
1. **[!UICONTROL DESCRIPTION]**: die Beschreibung der einzelnen einflussreichen Eigenschaften für die ausgewählte Persona;
1. **[!UICONTROL WEIGHT]**: die Gewichtung der einzelnen einflussreichen Eigenschaften für die ausgewählte Persona. [!UICONTROL Influential Traits] sind standardmäßig nach Gewicht in absteigender Reihenfolge sortiert.  Der Wert der Gewichtungen zeigt ihre Vorhersagekraft an. Das Zeichen gibt an, ob das Vorhandensein der Eigenschaft die Wahrscheinlichkeit erhöht (+) oder verringert (-), zu einer Persona zu gehören.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: die Anzahl der eindeutigen Eigenschaftsrealisierungen für jede einflussreiche Eigenschaft für die ausgewählte Persona in den letzten 30 Tagen.

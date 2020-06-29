---
description: Predictive Audiencen helfen Ihnen, unbekannte Audiencen mithilfe der Datenwissenschaft in Echtzeit in verschiedene Personengruppen zu klassifizieren.
seo-description: Predictive Audiencen helfen Ihnen, unbekannte Audiencen mithilfe der Datenwissenschaft in Echtzeit in verschiedene Personengruppen zu klassifizieren.
seo-title: Berichte für prognostizierte Audiencen
solution: Audience Manager
title: Audience Manager Predictive Audiencen
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---


# Berichte für prognostizierte Audiencen

Nachdem Sie ein [!UICONTROL Predictive Audiences] Modell gespeichert haben, trainieren Audience Manager Beginn es. Innerhalb weniger Stunden werden mit dem berechneten Modell Audiencen auf den [Datenerfassungsservern](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs)analysiert. Berichte wird am folgenden Tag verfügbar sein.

Um die Ergebnisse Ihrer [!UICONTROL Predictive Audiences] Klassifizierung anzuzeigen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, und klicken Sie in der Liste auf das gewünschte Modell.

Verwenden Sie die Filteroptionen auf der linken Seite, um nach dem Modellnamen zu suchen oder die Ergebnisse nach dem Modelltyp zu filtern.

![Predictive-Audiencen-filter](assets/predictive-audiences-filter-models.png)

Die Modelltabelle enthält die folgenden Informationen:

* **[!UICONTROL ID]**: die Modell-ID identifiziert jedes Modell in Ihrem Audience Manager-Konto eindeutig.
* **[!UICONTROL Name]**: den Namen, den Sie im Modellerstellungsschritt angegeben haben;
* **[!UICONTROL Description]**: die Beschreibung, die Sie im Modellerstellungsschritt angegeben haben;
* **[!UICONTROL Model Type]**: die Art jedes Modells ([!UICONTROL Look-Alike Modeling] oder [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: der Status jedes Modells:
   * **[!UICONTROL Pending]**: das Modell wird initialisiert und in Kürze werden Beginn zu Ergebnissen führen;
   * **[!UICONTROL Active]**: das Modell läuft erfolgreich und liefert Ergebnisse;
   * **[!UICONTROL Warning]**: das Profil konnte aufgrund unzureichender Daten (d. h. geringer Grundlinienpopulation, Benutzerdaten sind nicht reich) keine Ergebnisse erzielen;
   * **[!UICONTROL Error]**: Das Modell konnte nicht ausgeführt werden. Wenden Sie sich an Ihren Adobe-Kundenbetreuer.

## Modellübersichtsbericht{#model-report}

Wenn Sie ein Berichte auswählen, wird dessen Seite geladen. Oben auf der Seite können Sie die fünf größten Prognosesegmente sehen, die auf der 1-tägigen Echtzeit-Erkenntnis basieren, nach der das Modell Ihre Zielgruppe-Audience klassifiziert hat. Die **[!UICONTROL Other]** Kategorie umfasst den Rest der Personas, die nicht in den fünf größten Vorhersagesegmenten enthalten waren.

Audience Manager zeigt sowohl ein farbkodiertes Ringdiagramm als auch ein Zeitschienendiagramm für Ihre [!UICONTROL Predictive Audiences]Daten an.

Wenn Sie auf die Registerkarten &quot;personas&quot;oben auf der Seite klicken, werden sie dem Diagramm und dem Diagramm hinzugefügt oder daraus entfernt.

Das Ringdiagramm zeigt Ihnen eine personalbasierte Aufschlüsselung Ihrer Zielgruppe-Audience, während das Diagramm den 1-tägigen Realtime-Populationstrend Ihrer Prognosesegmente in den letzten 6 Tagen anzeigt.

Wenn der Modellstatus [!UICONTROL Pending], [!UICONTROL Warning]oder [!UICONTROL Error]der Modellstatus angezeigt wird, wird anstelle der Diagramme der Modellstatus angezeigt.

![smart-persona-report](assets/predictive-audiences-report.png)

Die Berichtstabelle enthält die folgenden Informationen zu jedem [!UICONTROL Predictive Audiences] Segment.

1. **[!UICONTROL SEGMENT ID]**: die Segment-ID des automatisch erstellten Segments, das jeder Persona zugeordnet ist;
1. **[!UICONTROL NAME]**: der Personenname;
1. **[!UICONTROL STATUS]**: Status des [!UICONTROL Predictive Audiences] Segments:
   * **[!UICONTROL Succeeded]**: Benutzer werden in dieses Segment klassifiziert;
   * **[!UICONTROL Pending]**: das Segment wird noch initialisiert;
   * **[!UICONTROL Insufficient Training Data]**: Benutzer werden aufgrund unzureichender Daten nicht in dieses Segment klassifiziert. Die Grundgesamtheit ist zu niedrig und bietet nicht genügend Daten, um davon zu lernen.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Die Anzahl der Segmentrealisierungen für jede Person in den letzten 24 Stunden.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: Der Prozentsatz der Segmentrealisierungen für jede Person in den letzten 24 Stunden aus der Gesamtpopulation des Modells.

## Einflussreiche Eigenschaften{#influential-traits}

[!UICONTROL Influential Traits] Eigenschaften sind, die der [!UICONTROL Predictive Audiences] Algorithmus als die stärksten Vorhersager zur Bestimmung der persönlichen Klassifizierung eines Besuchers entdeckt hat.

Das Symbol zeigt an, ob das Vorhandensein der Eigenschaft die Wahrscheinlichkeit erhöht (+) oder verringert (-), dass der Benutzer der ausgewählten Person angehört.

Klicken Sie auf , um die einflussreichen Eigenschaften für Ihre gesamte Person Ansicht [!UICONTROL View All Influential Traits].

Im [!UICONTROL Influential Traits] Fenster werden die folgenden Informationen zu jeder Person aus dem ausgewählten Modell angezeigt:

![influenzielle Eigenschaften](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: die Eigenschafts-ID jedes einflussreichen Merkmals für die ausgewählte Person;
1. **[!UICONTROL NAME]**: den Namen jeder einflussreichen Eigenschaft der ausgewählten Persona;
1. **[!UICONTROL DESCRIPTION]**: die Beschreibung der einzelnen einflussreichen Eigenschaften der ausgewählten Persona;
1. **[!UICONTROL WEIGHT]**: die Gewichtung der einzelnen einflussreichen Eigenschaften der ausgewählten Persona. [!UICONTROL Influential Traits] sind standardmäßig in absteigender Reihenfolge nach Gewichtung sortiert.  Der Wert der Gewichtungen gibt ihre Vorhersagekraft an. Das Zeichen gibt an, ob das Vorhandensein der Eigenschaft die Wahrscheinlichkeit, zu einer Person zu gehören, erhöht (+) oder verringert (-).
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: die Anzahl der eindeutigen Eigenschaften für jede einflussreiche Eigenschaft der ausgewählten Person in den letzten 30 Tagen.

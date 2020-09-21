---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-title: Häufig gestellte Fragen zu vorhersagekräftigen Zielgruppen
solution: Audience Manager
title: Vorhersagekräftige Zielgruppen für Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 04c638289878ff79070487d7d8cbb5c9454d93d6
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 64%

---


# Häufig gestellte Fragen zu vorhersagekräftigen Zielgruppen

Häufig gestellte Fragen zu [!UICONTROL Predictive Audiences].

 

**Wann sollte ich [!UICONTROL Predictive Audiences] anstatt [!UICONTROL Look-alike modeling] verwenden?**

[!UICONTROL Predictive Audiences] und [!UICONTROL Look-alike modeling] bedienen verschiedene Anwendungsfälle. Die wichtigsten Unterschiede zwischen den beiden Algorithmen sind:

1. [!UICONTROL Look-alike modeling] erwartet eine kleine Zielgruppe als Eingabe und erweitert diese. [!UICONTROL Predictive Audiences] erwartet eine große Zielgruppe als Eingabe und teilt sie anhand der von Ihnen definierten Personas in kleinere eindeutige Zielgruppen auf.
1. Die Anzahl der Basissegmente ist für jeden Algorithmus unterschiedlich. [!UICONTROL Predictive Audiences] erfordert mindestens zwei Grundlinien, während [!UICONTROL Look-alike modeling] höchstens eine Basislinie verwendet.
1. [!UICONTROL Predictive Audiences] wertet die Segmente in Echtzeit aus, während [!UICONTROL Look-alike modeling] dies nicht tut.

Je nach Anwendungsfall sollten Sie entscheiden, welches Modell für Sie angemessener ist.

Sie können das Erstellen eines [!UICONTROL Predictive Audiences]-Modells mit einer Reihe von Grundlinien dem Erstellen der gleichen Anzahl von Look-alike-Modellen vergleichen, nur ohne die Echtzeitauswertung und mit einer sehr hohen Wahrscheinlichkeit, dass Besucher mehreren verschiedenen Personas angehören, anstatt einer eindeutigen Persona.

 

**Wie viele Personas/Modelle darf ich erstellen?**

Sie können bis zu 10 [!UICONTROL Predictive Audiences]-Modelle erstellen. Für jedes Modell können Sie bis zu 50 Grundlinieneigenschaften oder Segmente definieren.

 

**Wie kann ich neue Segmente aus einem [!UICONTROL Predictive Audiences]-Segment erstellen?**

Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** und klicken Sie auf den Ordner **[!UICONTROL Predictive Audiences]**. Suchen Sie nach dem gewünschten Segment, duplizieren Sie es und bearbeiten Sie es nach Ihren Bedürfnissen.

 

**Warum wurden einige meiner integrierten Besucher nicht klassifiziert?**

Derzeit funktioniert die Zielgruppen-Classification nur für Echtzeitqualifikationen, außer für authentifizierte Benutzer, die als Teil von [!UICONTROL Profile Merge Rules] definiert wurden.

Die Unterstützung aller integrierter Daten wird in einer zukünftigen Aktualisierung hinzugefügt.

 

**Wann kann ich die ersten Ergebnisse meines Modells sehen?**

[!UICONTROL Predictive Audiences]-Modellergebnisse sind innerhalb von 24 Stunden nach der Modellerstellung verfügbar, wenn das Modell erfolgreich ausgeführt wird.

Sollte das Modell nicht innerhalb von 24 Stunden Ergebnisse liefern, wenden Sie sich bitte an Ihren Adobe-Support-Mitarbeiter.

 

**Warum liefert mein Modell keine Ergebnisse oder zeigt den Warnungsstatus an?**

[!UICONTROL Predictive Audiences]-Modelle können aus einer Reihe von Gründen zu keinen Ergebnissen führen:

1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough user profiles. We recommend choosing your [!UICONTROL traits] or [!UICONTROL segments] so that each persona has at least a few hundred user profiles.
1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough data in their user profiles (not enough traits to analyze).
1. In den letzten 30 Tagen gab es für die entsprechende Eigenschaft/das Segment der Zielgruppe keine aktiven oder integrierten Benutzer.
1. Die Benutzer der Zielgruppe, die in den letzten 30 Tagen aktiv waren oder integriert wurden, verfügen nicht über genügend Daten in ihren Benutzerprofilen (nicht genügend Eigenschaften zum Analysieren).
1. Das Modellsegment verwendet eine andere Audience [!UICONTROL Profile Merge Rule] als die Zielgruppe, die Sie für das Modell ausgewählt haben.
1. Die Datenquelle der Eigenschaften der Zielgruppe-Audience wird möglicherweise nicht in der Datei enthalten, die Sie für das Modell [!UICONTROL Profile Merge Rule] ausgewählt haben.

To produce relevant results, the [!UICONTROL Predictive Audiences] algorithm evaluates trait and segment realizations based on real-time user activity seen by the [!DNL DCS]. Wenn Sie neue Basiseigenschaften und Segmente auswählen, für die noch nicht genügend Benutzer vorhanden sind, kann es einige Tage dauern, bis der Algorithmus Ihre Zielgruppe klassifiziert.

Um optimale Ergebnisse zu erzielen, befolgen Sie die empfohlenen Richtlinien aus den [Auswahlkriterien für Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) und den [Auswahlkriterien für Zielgruppen](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Warum zeigt mein Modell den[!UICONTROL Error]Status an?**

Das Modell konnte nicht ausgeführt werden. In such cases, please reach out to your [!DNL Adobe] representative.

 

**Wie kann ich den[!UICONTROL Profile Merge Rule]für einen[!UICONTROL Predictive Audiences][!UICONTROL segment]?**

Erstellen Sie ein neues Modell, indem Sie die gleiche Audience für Personas und Zielgruppen wie das vorherige Modell auswählen. Weisen Sie bei der Modellerstellung einen anderen zu [!UICONTROL Profile Merge Rule].

>[!WARNING]
> Alternativ können Sie mit dem [Segmentaufbau](../features/segments/segment-builder.md) manuell eine [!UICONTROL segment] mit einer vorhandenen Vorhersage erstellen [!UICONTROL trait] und ihr eine [!UICONTROL Profile Merge Rule] Ihrer Wahl zuweisen.
> 
> Wir empfehlen diese Vorgehensweise jedoch nicht, da Vorhersagekraft [!UICONTROL traits] automatisch das Modell erbt, zu dem sie gehören, und sie sind aus einflussreichen [!UICONTROL Profile Merge Rule] Elementen aufgebaut, die dem [!UICONTROL traits] [!UICONTROL Profile Merge Rule] Modell entsprechen.

 

**Was[!UICONTROL Profile Merge Rule]soll ich wählen?**

Wenn Sie das Modell [!UICONTROL Profile Merge Rule] für Ihr Modell auswählen, analysieren Sie die Anwendungsfälle genau.

Nehmen wir an, Ihre Zielgruppe-Audience [!UICONTROL segment] verwendet eine [!UICONTROL Profile Merge Rule] auf authentifizierten Profilen + [!DNL Device Graph] -Profilen, und Sie wählen das gleiche [!UICONTROL Profile Merge Rule] für die Vorhersage [!UICONTROL segments]. In diesem Fall [!UICONTROL traits] werden sowohl die Geräteebene als auch die geräteübergreifende Ebene für die Schulung des Modells und für die Platzierung des Benutzers in eine Vorhersage verwendet [!UICONTROL segment].

Wenn Sie jedoch ein [!UICONTROL Profile Merge Rule] Gerät nur auf der Grundlage von Profilen auswählen, [!UICONTROL traits] wird keines Ihrer geräteübergreifenden Elemente einflussreich und trägt nicht zur Platzierung der Benutzer in eine Vorhersage bei [!UICONTROL segment]. Dies kann sich negativ auf die Genauigkeit und Reichweite des Modells auswirken.

Analysieren Sie Ihren Anwendungsfall sorgfältig und entscheiden Sie, von welchen [!UICONTROL trait] Typen das Modell lernen soll und welche Art von Daten das Modell für die Klassifizierung verwenden soll.

 

**Kann ein vorkommen, dass ein Benutzer aus der Zielgruppe, der nicht Teil einer/s Persona-Eigenschaft/-Segments ist, nicht klassifiziert wird?**

Ja, falls im Profil des Benutzer keine Eigenschaften angegeben sind. In diesem Fall erhält der Benutzer eine Übereinstimmungsbewertung von 0 für alle Persona-Eigenschaften/-Segmente und wird daher nicht in eines der Vorhersagesegmente klassifiziert.

 

**Kann ein Benutzer, der in eines der Vorhersagesegmente klassifiziert wurde, in ein anderes [!UICONTROL Predictive Audiences]-Segment umklassifiziert werden?**

Ja. Da der Algorithmus täglich trainiert wird, wendet er die Änderungen für jede der Personas in Bezug auf die Bewertung der Eigenschaften an. Wenn ein Benutzer, der Teil eines [!UICONTROL Predictive Audiences]-Segments ist, aktiv ist, können die Änderungen in seinem Eigenschaftswert die Classification basierend auf der Aktivität der letzten 30 Tage ändern.

 

**Kann ich regulären Segmenten Vorhersageeigenschaften hinzufügen?**

Wenn Sie einem regulären Segment eine prädiktive Eigenschaft hinzufügen, wird daraus ein prädiktives Segment. Folglich sind alle verknüpften Profil nicht segmentiert. Prognostische Segmente können nur an Echtzeit-Ziele gesendet werden.

 

**Kann ich die Eigenschaften sehen, nach denen die Zielgruppe klassifiziert wurde?**

Ja, Sie können alle einflussnehmenden Eigenschaften für alle Grundlinie auf der Seite mit den Modellberichten sehen. Siehe [Einflussnehmende Eigenschaften](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Was passiert mit dem Modell, wenn ich eine seiner Grundlinieneigenschaften oder -segmente bearbeite?**

Das Modellwertet die Eigenschaften oder Segmente einmal täglich aus. Die aktualisierte Classification sollte am nächsten Tag nach der Aktualisierung angezeigt werden.

 

**Kann ich die Datenquellen auswählen, aus denen das Modell lernen soll?**

Nein, die Auswahl von Datenquellen wird nicht unterstützt. Der [!UICONTROL Predictive Audiences]-Algorithmus lernt von all Ihren Erstanbietereigenschaften.
---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-title: Häufig gestellte Fragen zu vorhersagekräftigen Zielgruppen
solution: Audience Manager
title: Häufig gestellte Fragen zu vorhersagekräftigen Zielgruppen
feature: Algorithmische Modelle
exl-id: 21073970-8457-470b-89fc-724a118a18d2
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 59%

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

 

**Wann kann ich die ersten Ergebnisse meines Modells sehen?**

[!UICONTROL Predictive Audiences]-Modellergebnisse sind innerhalb von 24 Stunden nach der Modellerstellung verfügbar, wenn das Modell erfolgreich ausgeführt wird.

Sollte das Modell nicht innerhalb von 24 Stunden Ergebnisse liefern, wenden Sie sich bitte an Ihren Adobe-Support-Mitarbeiter.

 

**Warum liefert mein Modell keine Ergebnisse oder zeigt den Warnungsstatus an?**

[!UICONTROL Predictive Audiences]-Modelle können aus einer Reihe von Gründen zu keinen Ergebnissen führen:

1. Keine der ausgewählten Persona [!UICONTROL traits] / [!UICONTROL segments] hat genug Profil. Es wird empfohlen, [!UICONTROL traits] oder [!UICONTROL segments] zu wählen, damit jede Person mindestens hundert Profil hat.
1. Keine der ausgewählten Persona [!UICONTROL traits] / [!UICONTROL segments] verfügt über genügend Daten in ihren Profilen (nicht genügend Eigenschaften zur Analyse).
1. Die Eigenschaft/das Segment der Zielgruppe-Audience hat keine aktiven oder eingebetteten Benutzer.
1. Die Benutzer der Zielgruppe, die in den letzten 30 Tagen aktiv waren oder integriert wurden, verfügen nicht über genügend Daten in ihren Benutzerprofilen (nicht genügend Eigenschaften zum Analysieren).
1. Das Segment &quot;Zielgruppe Audience&quot;verwendet ein anderes [!UICONTROL Profile Merge Rule] als das, das Sie für das Modell ausgewählt haben.
1. Die Datenquelle der Eigenschaften der Zielgruppe-Audience ist möglicherweise nicht in dem [!UICONTROL Profile Merge Rule] enthalten, das Sie für das Modell ausgewählt haben.

Um optimale Ergebnisse zu erzielen, befolgen Sie die empfohlenen Richtlinien aus den [Auswahlkriterien für Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) und den [Auswahlkriterien für Zielgruppen](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Warum zeigt mein Modell den  [!UICONTROL Error] Status an?**

Das Modell konnte nicht ausgeführt werden. In solchen Fällen wenden Sie sich bitte an Ihren [!DNL Adobe] Vertreter.

 

**Wie kann ich die  [!UICONTROL Profile Merge Rule] für eine  [!UICONTROL Predictive Audiences] [!UICONTROL segment]Änderung?**

Erstellen Sie ein neues Modell, indem Sie die gleiche Audience für Personas und Zielgruppen wie das vorherige Modell auswählen. Weisen Sie bei der Modellerstellung ein anderes [!UICONTROL Profile Merge Rule] zu.

>[!WARNING]
> Alternativ können Sie [Segmentaufbau](../features/segments/segment-builder.md) verwenden, um manuell ein [!UICONTROL segment] mit einem vorhandenen Prognose [!UICONTROL trait] zu erstellen und ihm ein [!UICONTROL Profile Merge Rule] Ihrer Wahl zuzuweisen.
> 
> Diese Vorgehensweise wird jedoch nicht empfohlen, da bei der Prognose [!UICONTROL traits] automatisch das [!UICONTROL Profile Merge Rule] des Modells, zu dem sie gehören, übernommen wird und sie aus einflussreichen [!UICONTROL traits] aufgebaut sind, die dem [!UICONTROL Profile Merge Rule] des Modells entsprechen.

 

**Was  [!UICONTROL Profile Merge Rule] soll ich wählen?**

Wenn Sie [!UICONTROL Profile Merge Rule] für Ihr Modell auswählen, analysieren Sie Ihre Anwendungsfälle genau.

Nehmen wir an, Ihre Zielgruppe Audience [!UICONTROL segment] verwendet ein [!UICONTROL Profile Merge Rule], basierend auf authentifizierten Profilen + [!DNL Device Graph]-Profilen, und Sie wählen dasselbe [!UICONTROL Profile Merge Rule] für das Vorhersagekriterium [!UICONTROL segments]. In diesem Fall werden sowohl auf Geräteebene als auch auf geräteübergreifender Ebene [!UICONTROL traits] für die Schulung des Modells und für die Platzierung des Benutzers in eine Prognose [!UICONTROL segment] verwendet.

Wenn Sie jedoch ein [!UICONTROL Profile Merge Rule] auswählen, das nur auf Profilen des Geräts basiert, wird keines Ihrer geräteübergreifenden [!UICONTROL traits]-Elemente einflussreich und trägt nicht zur Platzierung der Benutzer in ein vorhersagbares [!UICONTROL segment] bei. Dies kann sich negativ auf die Genauigkeit und Reichweite des Modells auswirken.

Analysieren Sie Ihren Anwendungsfall sorgfältig und entscheiden Sie, von welchen [!UICONTROL trait]-Typen das Modell lernen soll und welche Art von Daten das Modell für die Klassifizierung verwenden soll.

**Kann ein vorkommen, dass ein Benutzer aus der Zielgruppe, der nicht Teil einer/s Persona-Eigenschaft/-Segments ist, nicht klassifiziert wird?**

Ja, falls im Profil des Benutzer keine Eigenschaften angegeben sind. In diesem Fall erhält der Benutzer eine Übereinstimmungsbewertung von 0 für alle Persona-Eigenschaften/-Segmente und wird daher nicht in eines der Vorhersagesegmente klassifiziert.

 

**Kann ein Benutzer, der in eines der Vorhersagesegmente klassifiziert wurde, in ein anderes [!UICONTROL Predictive Audiences]-Segment umklassifiziert werden?**

Ja. Da der Algorithmus täglich trainiert wird, wendet er die Änderungen für jede der Personas in Bezug auf die Bewertung der Eigenschaften an. Wenn ein Benutzer, der Teil eines [!UICONTROL Predictive Audiences]-Segments ist, aktiv ist, können die Änderungen in seinem Eigenschaftswert die Classification basierend auf der Aktivität der letzten 30 Tage ändern.

 

**Kann ich die Eigenschaften sehen, nach denen die Zielgruppe klassifiziert wurde?**

Ja, Sie können alle einflussnehmenden Eigenschaften für alle Grundlinie auf der Seite mit den Modellberichten sehen. Siehe [Einflussnehmende Eigenschaften](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Kann ich die &quot;Time to Live&quot;(TTL) für Prognosemerkmale ändern?**

Die prodiktive Eigenschaft TTL ist auf 0 (Lebensdauer) eingestellt und kann nicht geändert werden. [!UICONTROL Predictive Audiences] Sie können Benutzer nur dann von prädiktiven Segmenten trennen, wenn sie sich für das Basissegment qualifizieren oder wenn sie in ein anderes prädiktives Segment neu klassifiziert werden.

Bei Bedarf können Sie diese Funktion umgehen, indem Sie ein neues Segment erstellen, das sowohl eine prädiktive Eigenschaft als auch eine Aktivität mit einer angegebenen TTL enthält.

 


**Was passiert mit dem Modell, wenn ich eine seiner Grundlinieneigenschaften oder -segmente bearbeite?**

Das Modellwertet die Eigenschaften oder Segmente einmal täglich aus. Die aktualisierte Classification sollte am nächsten Tag nach der Aktualisierung angezeigt werden.

 

**Kann ich die Datenquellen auswählen, aus denen das Modell lernen soll?**

Nein, die Auswahl von Datenquellen wird nicht unterstützt. Der [!UICONTROL Predictive Audiences]-Algorithmus lernt von all Ihren Erstanbietereigenschaften.

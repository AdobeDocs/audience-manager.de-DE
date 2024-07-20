---
description: Vorhersagekräftige Zielgruppen helfen Ihnen, unbekannte Zielgruppen mithilfe von Datenwissenschaft in Echtzeit in eindeutige Personas zu klassifizieren.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zu vorhersagekräftigen Zielgruppen
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '957'
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

1. Keines der ausgewählten Personas [!UICONTROL traits] / [!UICONTROL segments] verfügt über genügend Benutzerprofile. Es wird empfohlen, [!UICONTROL traits] oder [!UICONTROL segments] auszuwählen, damit jede Person mindestens hundert Benutzerprofile hat.
1. Keine der ausgewählten Persona [!UICONTROL traits] / [!UICONTROL segments] verfügt über genügend Daten in ihren Benutzerprofilen (nicht genügend Eigenschaften zur Analyse).
1. Die Eigenschaft/das Segment der Zielgruppe hat keine aktiven oder integrierten Benutzer.
1. Die Benutzer der Zielgruppe, die in den letzten 30 Tagen aktiv waren oder integriert wurden, verfügen nicht über genügend Daten in ihren Benutzerprofilen (nicht genügend Eigenschaften zum Analysieren).
1. Das Zielgruppensegment verwendet einen anderen [!UICONTROL Profile Merge Rule] als den für das Modell ausgewählten.
1. Die Datenquelle Ihrer Zielgruppen-Eigenschaften ist möglicherweise nicht in dem für das Modell ausgewählten [!UICONTROL Profile Merge Rule] enthalten.

Um optimale Ergebnisse zu erzielen, befolgen Sie die empfohlenen Richtlinien aus den [Auswahlkriterien für Personas](../features/algorithmic-models/predictive-audiences.md#selection-personas) und den [Auswahlkriterien für Zielgruppen](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Warum zeigt mein Modell den Status [!UICONTROL Error] an?**

Das Modell konnte nicht ausgeführt werden. Wenden Sie sich in solchen Fällen an Ihren [!DNL Adobe] -Support-Mitarbeiter.

 

**Wie kann ich den [!UICONTROL Profile Merge Rule] für einen [!UICONTROL Predictive Audiences] [!UICONTROL segment] ändern?**

Erstellen Sie ein neues Modell, indem Sie dieselben Personas und Zielgruppen wie im vorherigen Modell auswählen. Weisen Sie bei der Modellerstellung einen anderen [!UICONTROL Profile Merge Rule] zu.

>[!WARNING]
> Alternativ können Sie [Segmentaufbau](../features/segments/segment-builder.md) verwenden, um manuell einen [!UICONTROL segment] mit einem vorhandenen Prognosewert [!UICONTROL trait] zu erstellen und ihn mit einem [!UICONTROL Profile Merge Rule] Ihrer Wahl zuzuweisen.
> 
> Wir empfehlen diese Vorgehensweise jedoch nicht, da das prädiktive [!UICONTROL traits] automatisch das [!UICONTROL Profile Merge Rule] des Modells erbt, zu dem es gehört, und sie aus einflussreichen [!UICONTROL traits] erstellt werden, die dem [!UICONTROL Profile Merge Rule] des Modells entsprechen.

 

**Was [!UICONTROL Profile Merge Rule] soll ich wählen?**

Wenn Sie die [!UICONTROL Profile Merge Rule] für Ihr Modell auswählen, analysieren Sie Ihren Anwendungsfall genau.

Nehmen wir an, Ihre Zielgruppe [!UICONTROL segment] verwendet eine [!UICONTROL Profile Merge Rule], die auf authentifizierten Profilen basiert, und [!DNL Device Graph] Profile, und Sie wählen dieselbe [!UICONTROL Profile Merge Rule] für die Vorhersage [!UICONTROL segments] aus. In diesem Fall wird sowohl auf Geräteebene als auch auf geräteübergreifender Ebene [!UICONTROL traits] für das Trainieren des Modells und für die Platzierung des Benutzers in eine Vorhersagekraft [!UICONTROL segment] verwendet.

Wenn Sie jedoch eine [!UICONTROL Profile Merge Rule] nur auf der Grundlage von Geräteprofilen auswählen, wird keiner Ihrer geräteübergreifenden [!UICONTROL traits] einflussreich und trägt nicht zur Platzierung von Benutzern in eine prädiktive [!UICONTROL segment] bei. Dies kann sich negativ auf die Genauigkeit und Reichweite des Modells auswirken.

Analysieren Sie Ihren Anwendungsfall sorgfältig und entscheiden Sie, von welchen [!UICONTROL trait] Typen das Modell lernen soll und welche Datentypen das Modell für die Klassifizierung verwenden soll.

**Kann ein vorkommen, dass ein Benutzer aus der Zielgruppe, der nicht Teil einer/s Persona-Eigenschaft/-Segments ist, nicht klassifiziert wird?**

Ja, falls im Profil des Benutzer keine Eigenschaften angegeben sind. In diesem Fall erhält der Benutzer eine Übereinstimmungsbewertung von 0 für alle Persona-Eigenschaften/-Segmente und wird daher nicht in eines der Vorhersagesegmente klassifiziert.

 

**Kann ein Benutzer, der in eines der Vorhersagesegmente klassifiziert wurde, in ein anderes [!UICONTROL Predictive Audiences]-Segment umklassifiziert werden?**

Ja. Da der Algorithmus täglich trainiert wird, wendet er die Änderungen für jede der Personas in Bezug auf die Bewertung der Eigenschaften an. Wenn ein Benutzer, der Teil eines [!UICONTROL Predictive Audiences]-Segments ist, aktiv ist, können die Änderungen in seinem Eigenschaftswert die Classification basierend auf der Aktivität der letzten 30 Tage ändern.

 

**Kann ich die Eigenschaften sehen, nach denen die Zielgruppe klassifiziert wurde?**

Ja, Sie können alle einflussnehmenden Eigenschaften für alle Grundlinie auf der Seite mit den Modellberichten sehen. Siehe [Einflussnehmende Eigenschaften](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Kann ich die Live-Zeit (TTL) für Eigenschaften mit Prognosen ändern?**

Die prädiktive Eigenschaft TTL ist auf 0 (Lebensdauer) festgelegt und kann nicht geändert werden. [!UICONTROL Predictive Audiences] kann die Segmentierung von Benutzern aus Vorhersagesegmenten nur aufheben, wenn sie sich für das Basissegment qualifizieren oder in ein anderes Vorhersagesegment umklassifiziert werden.

Bei Bedarf können Sie diese Funktion umgehen, indem Sie ein neues Segment erstellen, das sowohl eine prädiktive Eigenschaft als auch eine Aktivitätseigenschaft mit einer angegebenen TTL enthält.

 


**Was passiert mit dem Modell, wenn ich eine seiner Grundlinieneigenschaften oder -segmente bearbeite?**

Das Modellwertet die Eigenschaften oder Segmente einmal täglich aus. Die aktualisierte Classification sollte am nächsten Tag nach der Aktualisierung angezeigt werden.

 

**Kann ich die Datenquellen auswählen, aus denen das Modell lernen soll?**

Nein, die Auswahl von Datenquellen wird nicht unterstützt. Der [!UICONTROL Predictive Audiences]-Algorithmus lernt von all Ihren Erstanbietereigenschaften.

---
description: Predictive Audiencen helfen Ihnen, unbekannte Audiencen mithilfe der Datenwissenschaft in Echtzeit in verschiedene Personengruppen zu klassifizieren.
seo-description: Predictive Audiencen helfen Ihnen, unbekannte Audiencen mithilfe der Datenwissenschaft in Echtzeit in verschiedene Personengruppen zu klassifizieren.
seo-title: Häufig gestellte Fragen zu Predictive Audiencen
solution: Audience Manager
title: Audience Manager Predictive Audiencen
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---


# Häufig gestellte Fragen zu Predictive Audiencen

Häufig gestellte Fragen zu [!UICONTROL Predictive Audiences].

 

**Wann sollte ich[!UICONTROL Predictive Audiences]im Gegensatz zu[!UICONTROL Look-alike modeling]verwenden?**

[!UICONTROL Predictive Audiences] und verschiedene Anwendungsfälle [!UICONTROL Look-alike modeling] bedienen. Die wichtigsten Unterschiede zwischen den beiden Algorithmen sind:

1. [!UICONTROL Look-alike modeling] nimmt eine kleine Audience als Eingabe und erweitert sie. [!UICONTROL Predictive Audiences] nimmt eine große Audience als Eingabe und teilt sie in kleinere, unterschiedliche Audiencen, die von Ihrer Person definiert werden.
1. Die Anzahl der Basissegmente ist für jeden Algorithmus unterschiedlich. [!UICONTROL Predictive Audiences] mindestens zwei Basislinien benötigt, während [!UICONTROL Look-alike modeling] höchstens eine Basislinie verwendet wird.
1. [!UICONTROL Predictive Audiences] eine Segmentauswertung in Echtzeit, [!UICONTROL Look-alike modeling] nicht jedoch.

Je nach Anwendungsfall sollten Sie entscheiden, welches Modell für Sie relevanter sein soll.

Man kann sich vorstellen, ein [!UICONTROL Predictive Audiences] Modell mit einer Reihe von Grundlinien zu erstellen, das dem Erstellen derselben Anzahl von Aussehen-ähnlichen Modellen entspricht, nur ohne Echtzeitbewertung und mit sehr hoher Wahrscheinlichkeit Besucher zu haben, die zu mehreren verschiedenen Persönlichkeiten gehören, anstatt zu einer bestimmten Person.

 

**Wie viele Personen/Modelle darf ich erstellen?**

Sie können bis zu 10 [!UICONTROL Predictive Audiences] Modelle erstellen. Für jedes Modell können Sie bis zu 50 Grundlinieneigenschaften oder Segmente definieren.

 

**Wie kann ich neue Segmente aus einem[!UICONTROL Predictive Audiences]Segment erstellen?**

Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** und klicken Sie auf den **[!UICONTROL Predictive Audiences]** Ordner. Suchen Sie das gewünschte Segment, erstellen Sie ein Duplikat und bearbeiten Sie es entsprechend Ihren Anforderungen.

 

**Warum sind einige meiner an Bord befindlichen Besucher nicht klassifiziert?**

Derzeit funktioniert die Audience-Classification nur für Echtzeitqualifikationen, mit Ausnahme authentifizierter , die als Teil von [!UICONTROL Profile Merge Rules]definiert wurden.

Die volle Unterstützung für Daten, die mit dem Boot-System integriert werden, wird in einer zukünftigen Aktualisierung hinzugefügt.

 

**Wann kann ich die ersten Ergebnisse sehen, die von meinem Modell produziert wurden?**

[!UICONTROL Predictive Audiences] Modellergebnisse sind innerhalb von 24 Stunden nach der Modellerstellung verfügbar, wenn das Modell erfolgreich ausgeführt wird.

Sollte das Modell nicht innerhalb von 24 Stunden Ergebnisse liefern, wenden Sie sich bitte an Ihren Adobe-Kundenbetreuer.

 

**Warum liefert mein Modell keine Ergebnisse oder zeigt den Warnungsstatus an?**

[!UICONTROL Predictive Audiences] Aus zahlreichen Gründen können die Ergebnisse von Modellen fehlschlagen:

1. Keiner der ausgewählten persönlichen Eigenschaften/Segmente hat genug Profil. Es wird empfohlen, die Eigenschaften oder Segmente auszuwählen, damit jede Person mindestens hundert Profil hat.
1. Keiner der ausgewählten persönlichen Eigenschaften/Segmente verfügt über genügend Daten in ihren Profilen (nicht genügend Eigenschaften zur Analyse).
1. In den letzten 30 Tagen waren keine aktiven oder eingebetteten Audiencen für die Zielgruppe vorhanden.
1. Die Benutzer der Zielgruppe-Audience, die in den letzten 30 Tagen aktiv oder an Bord waren, verfügen nicht über genügend Daten in ihren Benutzerdaten (nicht genügend Eigenschaften zur Analyse).

Um relevante Ergebnisse zu erzielen, bewertet der [!UICONTROL Predictive Audiences] Algorithmus Eigenschaften- und Segmentrealisierungen auf der Grundlage der vom DCS erkannten Echtzeit-Aktivität des Benutzers. Wenn Sie neue Basiseigenschaften und Segmente auswählen, für die noch nicht genügend Benutzer vorhanden sind, kann es einige Tage dauern, bis der Algorithmus Ihre Audience klassifiziert.

Um optimale Ergebnisse zu erzielen, befolgen Sie die empfohlenen Richtlinien aus den [Auswahlkriterien für Personen](../features/algorithmic-models/predictive-audiences.md#selection-personas) und den [Auswahlkriterien für die Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience)des Targets.

 

**Warum zeigt mein Modell den Fehlerstatus an?**

Das Modell konnte nicht ausgeführt werden. In solchen Fällen wenden Sie sich bitte an Ihren Adobe-Kundenbetreuer.

 

**Wie kann ich die Profil-Merge-Regel für ein Predictive Audiencen-Segment ändern?**

Duplikat des [!UICONTROL Predictive Audiences] Segments und Ändern Sie die [!UICONTROL Profile Merge Rule] Einstellung für das duplizierte Segment.

 

**Kann ein Benutzer aus der Audience der Zielgruppe, der nicht Teil einer persönlichen Eigenschaft/eines Segments ist, nicht klassifiziert werden?**

Ja, falls der Benutzer keine Eigenschaften in seinem Profil hat. In diesem Fall erhält der Benutzer eine Übereinstimmungsbewertung von 0 zu allen persönlichen Eigenschaften/Segmenten und wird daher nicht in eines der Vorhersagesegmente klassifiziert.

 

**Kann ein Benutzer, der in eines der prädiktiven Segmente klassifiziert wurde, in ein anderes[!UICONTROL Predictive Audiences]Segment neu klassifiziert werden?**

Ja. Da der Algorithmus täglich geschult wird, wendet er die Änderungen für jede der Personen in Bezug auf die Bewertung der Eigenschaften an. Wenn ein Benutzer, der Teil eines [!UICONTROL Predictive Audiences] Segments ist, aktiv ist, können die Änderungen in seinem Eigenschaftswert die Klassifizierung anhand der Aktivität der letzten 30 Tage ändern.

 

**Kann ich die Eigenschaften sehen, nach denen die Audience klassifiziert wurde?**

Ja, Sie können alle einflussreichen Eigenschaften für alle Basislinien auf der Modellseite sehen. Siehe [Einflussreiche Eigenschaften](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Was passiert mit dem Modell, wenn ich eine seiner Grundlinieneigenschaften oder -segmente editiere?**

Das Modell bewertet die Eigenschaften oder Segmente einmal täglich. Die aktualisierte Klassifizierung sollte am nächsten Tag nach der Aktualisierung angezeigt werden.

 

**Kann ich die Datenquellen auswählen, aus denen das Modell lernen soll?**

Nein, die Auswahl von Datenquellen wird nicht unterstützt. Der [!UICONTROL Predictive Audiences] Algorithmus lernt von all Ihren Erstanbietereigenschaften.
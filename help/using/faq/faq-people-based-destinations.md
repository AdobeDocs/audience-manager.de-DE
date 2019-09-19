---
description: 'Antworten auf häufig gestellte Fragen zu benutzerspezifischen Zielen.  '
seo-description: 'Antworten auf häufig gestellte Fragen zu benutzerspezifischen Zielen.  '
seo-title: Häufig gestellte Fragen zu benutzerspezifischen Zielen
solution: Audience Manager
title: Häufig gestellte Fragen zu benutzerspezifischen Zielen
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Häufig gestellte Fragen zu benutzerspezifischen Zielen {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Ich kann[!DNL People-Based Destinations]das Audience Manager-Konto nicht sehen. Was muss ich über Verfügbarkeit wissen?**

[!DNL People-Based Destinations] ist eine Premium-Audience Manager-Funktion, die beim Kauf verfügbar ist. Informationen zu Preisen und Verfügbarkeit erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter.

## Daten bei der Einschiffung {#data-onboarding}

**Wie kann ich E-Mail-Adressen von Kunden in Audience Manager einbinden, damit ich sie verwenden kann[!DNL People-Based Destinations]?**

Es gibt zwei Möglichkeiten, Ihre Offlinedaten in Audience Manager zu laden [!DNL People-Based Destinations].

* **Verwenden Sie die dateibasierte ID-Synchronisierung**. Einzelheiten dazu, wie ID-Synchronisierungsdateien aussehen sollten, finden Sie unter [Name und Inhaltsanforderungen für ID-Synchronisierungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) . Bei Verwendung dieser Methode können Sie alle Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank als Ziel auswählen.
* **Verwenden Sie deklarierte IDs** , um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode aktiviert Audience Manager nur die Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die über Facebook aktivierten E-Mail-Adressen sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit aktiviert.

**Kann ich Hash-E-Mail-Adressen über ein Webformular oder eine mobile App erfassen oder müssen sie in einer Batch-Datei vorliegen?**

Sie können Hash-E-Mail-Adressen mithilfe der Web-Authentifizierung [!DNL ECID] mit [deklarierten IDs](../features/declared-ids.md)erfassen. Mit der Stapelverarbeitungsdatei können Sie auch Hash-E-Mail-Adressen erfassen, die nicht über eine Authentifizierung gesendet werden können (z. B. ruhende Benutzer in Ihren ([!DNL CRM]), und sie in benutzerbasierten Zielen aktivieren.

**Wie unterscheidet sich die Erfassung von Hash-E-Mail-Adressen über Webformulare vom Hochladen von Hash-E-Mail-Adressen über Batch-Dateien?**

Die Offline-Datenerfassung unterstützt Anwendungsfälle ohne Authentifizierung. Eine neue Regel zur Profilzusammenführung ([!UICONTROL All Cross-Device Profiles]), die auf allen Offline- [!DNL CRM] Profilen unabhängig von der Authentifizierung ausgeführt wird, ist als Teil [!DNL People-Based Destinations]verfügbar. Diese Methode soll die Erfassung authentifizierter Zielgruppen aus Online-Quellen ergänzen.

**Wie oft kann ich Hash-E-Mail-Adressen maximal senden/aktualisieren?**

* Bei Verwendung deklarierter IDs sendet Audience Manager die Hash-E-Mail-Adressen in Echtzeit an das Ziel.
* Wenn Daten über ID-Synchronisierungsdateien aufgenommen werden, verarbeitet Audience Manager sie täglich.

**Woher weiß ich, ob das Hashing der E-Mail-Adresse korrekt ausgeführt wurde?**

Audience Manager nimmt die unverarbeitete E-Mail-Adresse nicht auf und wir können nicht überprüfen, ob der Hash korrekt ausgeführt wurde. Weitere Informationen dazu, wie Sie die Daten mit [Daten im Internet hash sollten, finden Sie unter Voraussetzungen und Überlegungen](../features/destinations/people-based-destinations-prerequisites.md) .

## Regeln zum Profilzusammenführen {#profile-merge-rules}

**Gibt es eine neue Regel zum Zusammenführen von Profilen, die ich verwenden kann[!DNL People-Based Destinations]?**

Ja. Kunden, die einen Kauf tätigen, [!DNL People-Based Destinations] erhalten außerdem Zugriff auf eine neue Regel zur Profilzusammenführung für die Offlinegmentierung. Die Regel wird aufgerufen [!DNL All Cross-Device Profiles] und für die ausschließliche Offline-Segmentierung verwendet. Wenn Sie sich für anmelden, [!DNL People-Based Destinations]ist dies die vierte Regel zum Profilzusammenführen, die Sie erstellen können, abgesehen von den drei vorhandenen authentifizierungsbasierten Regeln.

**Muss ich meine vorhandenen Zielgruppensegmente duplizieren, um sie zu aktivieren[!DNL People-Based Destinations]?**

Es hängt von Ihrem Anwendungsfall ab. Wenn Sie planen, vorhandene Erstanbieter-Segmente in benutzerbasierten Kanälen zu aktivieren, müssen Sie keine neuen Segmente erstellen. Sie können die Segmente einfach einem benutzerbasierten Ziel zuordnen.

Wenn Sie planen, neue Offline-Zielgruppen in benutzerbasierten Kanälen zu aktivieren, müssen Sie neue Erstanbieter-Segmente mithilfe der [!DNL All Cross-Device Profiles] Zusammenführungsregel erstellen.
>[!NOTE]
>
> Sie können nur Segmente mit Erstanbieter-Daten zuordnen zu [!DNL People-Based Destinations]. Unsere Zielplattformen akzeptieren keine Segmente mit Daten von Zweitanbietern und Drittanbietern.

## Übereinstimmungsraten {#match-rates}

**Haben Sie[!DNL People-Based Destinations]Einblicke in Übereinstimmungsraten oder adressierbare Zielgruppen?**

Nein. Beim Senden von Zielgruppensegmenten an [!DNL People-Based Destinations]erfolgt die Zielgruppenzuordnung auf der Partnerseite. Adobe hat keinen Zugriff auf diese Metriken. Audience Manager zeigt Ihnen die maximale freigegebene Zielgruppe für jedes Ziel und die Echtzeitanzahl der Personen, die zu einem Segment gehören. Diese Informationen können Ihnen bei der Planung und Prognose von Kampagnen helfen.

**Wie würden Raten theoretisch mit anderen Methoden zum Senden von Zielgruppen an Zielplattformen verglichen[!DNL People-Based Destinations]werden?**

Solange die E-Mail-Adresse richtig gehackt und erfasst wird, sollte es keinen Unterschied in der Übereinstimmungsrate zwischen [!DNL People-Based Destinations] und anderen Methoden geben. Der einzige Grund, warum eine Übereinstimmungsrate unter 100 % liegt, ist, wenn die in Audience Manager eingebrachten E-Mail-Adressen nicht mit einer E-Mail-Adresse in der Benutzerbasis der Zielplattform übereinstimmen können.

**Ich sammle Arbeits-E-Mail-Adressen meiner Kunden, die sich von den in sozialen Netzwerken verwendeten persönlichen E-Mail-Adressen unterscheiden. Wie ordnen Sie Identitäten über mehrere E-Mail-Adressen hinweg zu?**

Audience Manager kann bis zu 10 E-Mails pro Benutzer sammeln und an Zielplattformen senden. Die E-Mail-Adressen müssen jedoch über Synchronisierungsdateien erfasst werden. Nachdem Audience Manager die E-Mail-Adressen an Zielplattformen gesendet hat, müssen die Plattformen die E-Mail-Adressen mit der eigenen Benutzerbasis abgleichen. Einige Plattformen verfügen möglicherweise über zusätzliche Diagramme für E-Mail-Adressen, die von Audience Manager an Benutzerprofile gesendet werden.

## Datenexportkontrolle {#data-export-controls}

**Wie[!DNL Data Export Controls]wirkt[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] blockiert alle Segmente, die Daten von Zweit- und Drittanbietern enthalten, an die Benutzer zu senden versuchen [!DNL People-Based Destinations]. [!DNL People-Based Destinations] Nur Erstanbieter-Daten dürfen für Targeting verwendet werden. [!DNL Data Export Controls] auch Segmente mit [!DNL Profile Merge Rules] Gerätediagrammen blockieren. [!DNL People-Based Destinations] werden mit den entsprechenden Beschriftungen für den Datenexport erstellt und Sie können die Exporteinstellungen nicht überschreiben.

## Partnerspezifische Fragen {#partner-specific-questions}

### [!DNL Facebook]

**Was muss ich tun, bevor ich Zielgruppensegmente senden kann[!DNL Facebook]?**

Bevor Sie Zielgruppensegmente [!DNL People-Based Destinations] [!DNL Facebook]an senden können, müssen Sie die folgenden Konfigurationsaufgaben ausführen:

1. Fügen Sie das Adobe Experience Cloud-Geschäftskonto als Werbepartner in Ihrem [!DNL Facebook Ad Account]Konto hinzu. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter Partner zu Ihrem Business Manager hinzufügen.

   >[!IMPORTANT]
   >
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung "Kampagnen verwalten"aktivieren. Dies ist für die [!DNL People-Based Destinations] Integration erforderlich.

1. Lesen und unterschreiben Sie die [!DNL Facebook Custom Audiences Terms of Service]. Um das zu tun, gehen Sie zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wo `accountID` ist Ihr [!DNL Facebook Ad Account ID].

**Unterstützt[!DNL People-Based Destinations]das Zielgruppen-Targeting in anderen[!DNL Facebook]Apps, z. B.[!DNL Instagram]?**

Sie können Apps [!DNL People-Based Destinations] aus [!DNL Facebook]der gesamten Familie verwenden, die von [!DNL Custom Audiences], einschließlich [!DNL Facebook], [!DNL Instagram]und [!DNL Audience Network][!DNL Messenger] unterstützt werden. Die Auswahl der App, für die Sie eine Kampagne ausführen möchten, wird auf Platzierungsebene in angezeigt [!DNL Facebook Ads Manager].

**Was ist der Unterschied zwischen[!DNL People-Based Destinations]und[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] nutzt die [!DNL Custom Audiences (CA)] Integration mit [!DNL Facebook]. Der Unterschied zwischen [!DNL WCA] und [!DNL CA] Integrationen ist der Schlüssel, den Kunden beim Senden von Zielgruppen an verwenden [!DNL Facebook]. [!DNL WCA] verwendet das [!DNL Facebook] Pixel (d. h. eine Website-Benutzer-ID), während [!DNL People-Based Destinations] Hash-E-Mail-Adressen zur Integration in verwendet werden [!DNL CA].

Sie können die [!DNL Facebook][!DNL WCA] Integration von Audience Manager ohne zusätzliche Kosten über die [!DNL URL Destinations] Funktion nutzen.

Diese beiden Integrationen ergänzen sich. Sie können beide verwenden, um eine bessere Abdeckung der Zielgruppe sicherzustellen. Beispiel: Sie [!DNL WCA] können zum Aufsuchen verwendet werden, wenn ein Unternehmen auf Besucher der Website abzielt, die kein Konto registriert haben, während Sie [!DNL People-Based Destinations] möglicherweise vorhandenen Kunden, die ihre E-Mail-Adresse angegeben haben, aber möglicherweise nicht die Website besucht haben, helfen können.

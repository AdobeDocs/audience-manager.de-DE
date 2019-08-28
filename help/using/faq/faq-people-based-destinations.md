---
description: 'Antworten auf häufig gestellte Fragen zu benutzerbasierten Zielen.  '
seo-description: 'Antworten auf häufig gestellte Fragen zu benutzerbasierten Zielen.  '
seo-title: Häufig gestellte Fragen zu benutzerbasierten Zielen
solution: Audience Manager
title: Häufig gestellte Fragen zu benutzerbasierten Zielen
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Häufig gestellte Fragen zu benutzerbasierten Zielen {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Ich kann[!DNL People-Based Destinations]in meinem Audience Manager-Konto nicht sehen. Was muss ich über Verfügbarkeit wissen?**

[!DNL People-Based Destinations] ist eine Premium Audience Manager-Funktion, die beim Kauf verfügbar ist. Einzelheiten zu Preisen und Verfügbarkeit erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter.

## Datenonboarding {#data-onboarding}

**Wie kann ich Kunden-E-Email-Adressen in Audience Manager aufrufen, damit ich sie verwende[!DNL People-Based Destinations]?**

Sie können Ihre Offline-Daten auf zweierlei Weise in Audience Manager übernehmen.[!DNL People-Based Destinations]

* **Verwenden Sie die dateibasierte ID-Synchronisierung**. Unter [Name und Content-Anforderungen für ID-Synchronisierungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) finden Sie Informationen darüber, wie die ID-Synchronisierungsdateien aussehen sollten. Wenn Sie diese Methode verwenden, können Sie alle Hash-E-Mail-Adressen aus Ihrer [!DNL CRM] Datenbank auswählen.
* **Verwenden Sie deklarierte IDs** , um Hash-E-Email-Adressen beim Übermitteln authentifizierter Kunden-IDs zu deklarieren. Bei Verwendung dieser Methode aktiviert Audience Manager nur die Hash-E-Email-Adressen von Benutzern, die online authentifiziert wurden. Die per Facebook aktivierten E-Email-Adressen sind nur diejenigen in den deklarierten ID-Ereignisaufrufen. Andere E-Email-Adressen, die mit der Kunden-ID verknüpft sind, werden nicht in Echtzeit aktiviert.

**Kann ich Hash-E-Email-Adressen über ein Webformular oder eine mobile App erfassen oder brauchen sie eine Stapelverarbeitungsdatei?**

Sie können Hash-E-Email-Adressen über die Webauthentifizierung mit [!DNL ECID][Deklarierten IDs erfassen](../features/declared-ids.md). Mit der Stapelverarbeitungsdatei können Sie außerdem Hash-E-Mail-Adressen erfassen, die nicht über die Authentifizierung gesendet werden können (z. B. benutzerdefinierte Benutzer in Ihrer ([!DNL CRM]), und sie in benutzerbasierten Zielen aktivieren.

**Wie wird die Erfassung von Hash-E-Mail-Adressen über Webformulare anders als das Hochladen von Hash-E-Mail-Adressen über Batch-Dateien?**

Die Offline-Datenerfassung unterstützt die Unterstützung von Anwendungsfällen ohne Authentifizierung und eine neue Regel zur Profilzusammenführung ([!UICONTROL All Cross-Device Profiles]), die unabhängig von der Authentifizierung in allen Offline [!DNL CRM] -Profilen ausgeführt wird [!DNL People-Based Destinations]. Diese Methode soll die Erfassung authentifizierter Zielgruppen aus Online-Quellen ergänzen.

**Wie häufig ist die Häufigkeit, mit der ich Hash-E-Email-Adressen senden/aktualisieren kann?**

* Wenn Sie Deklarierte IDs verwenden, sendet Audience Manager die Hash-E-Email-Adressen in Echtzeit an das Ziel.
* Beim Erfassen von Daten mittels ID-Synchronisierungsdateien verarbeitet Audience Manager sie täglich.

**Woher weiß ich, ob die Hash-Funktion für E-Email-Adressen richtig ausgeführt wird?**

Der Audience Manager übernimmt keine eingehende E-Email-Adresse und wir können nicht überprüfen, ob der Hash richtig ausgeführt wurde. Einzelheiten dazu, wie Sie die onboardierten Daten hash sollten, finden Sie unter [Voraussetzungen und Überlegungen](../features/destinations/people-based-destinations-prerequisites.md) .

## Regeln für die Profilzusammenführung {#profile-merge-rules}

**Gibt es eine neue Regel zur Profilzusammenführung, die ich verwenden[!DNL People-Based Destinations]kann?**

Ja. Kunden, die einen Kauf erwerben [!DNL People-Based Destinations] , erhalten auch Zugriff auf eine neue Regel zur Profilzusammenführung für die Offline-Segmentierung. Die Regel wird aufgerufen [!DNL All Cross-Device Profiles] und dient zur Offline-Segmentierung. Nach der Anmeldung ist dies [!DNL People-Based Destinations]die vierte Regel zur Profilzusammenführung, die Sie erstellen können, und zwar abgesehen von den drei vorhandenen authentifizierten Regeln.

**Muss ich meine vorhandenen Zielgruppensegmente duplizieren, um[!DNL People-Based Destinations]sie zu aktivieren?**

Dies hängt von Ihrem Verwendungsfall ab. Wenn Sie vorhandene Erstanbietersegmente in benutzerbasierten Kanälen aktivieren möchten, müssen Sie keine neuen Segmente erstellen. Sie können die Segmente einfach einem benutzerbasierten Ziel zuordnen.

Wenn Sie in benutzerbasierten Kanälen neue Offline-Zielgruppen aktivieren möchten, müssen Sie neue Erstanbietersegmente mit der [!DNL All Cross-Device Profiles] Zusammenführungsregel erstellen.
>[!NOTE]
>
> Sie können Segmente nur mit Erstanbieterdaten zuordnen [!DNL People-Based Destinations]. Unsere Zielplattformen akzeptieren keine Segmente mit Daten aus Drittanbietern und Drittanbietern.

## Übereinstimmungsraten {#match-rates}

**Haben Sie Sichtbarkeitsraten[!DNL People-Based Destinations]oder adressierbare Zielgruppen?**

Nein. Beim Senden von Zielgruppensegmenten [!DNL People-Based Destinations]erfolgt die Zielgruppenzuordnung auf dem Partner. Adobe hat keinen Zugriff auf diese Metriken. Audience Manager zeigt Ihnen die maximal zulässige Zielgruppe für jedes Ziel und die Echtzeit-Anzahl der Personen, die zu einem Segment gehören. Diese Informationen können Ihnen bei der Kampagnenplanung und den Prognosen helfen.

**Wie würden Übereinstimmungsraten mit[!DNL People-Based Destinations]den anderen Methoden zum Senden von Zielgruppen an Zielplattformen verglichen?**

Solange die E-Mail-Adresse Hash und korrekt erfasst wird, sollten die Übereinstimmungsraten zwischen [!DNL People-Based Destinations] und anderen Methoden nicht unterschieden werden. Der einzige Grund für eine Übereinstimmungsrate wäre unter 100%, wenn die in Audience Manager eingehenden E-Email-Adressen nicht mit einer E-Email-Adresse in der Benutzerbasis der Zielplattform abgeglichen werden können.

**Ich erfasse Arbeits-E-Mail-Adressen von meinen Kunden, die sich von den persönlichen E-Mail-Adressen in sozialen Netzwerken unterscheiden. Wie stimmen Sie mit Identitäten über mehrere E-Mail-Adressen überein?**

Audience Manager kann pro Benutzer bis zu 10 E-Emails erfassen und an Zielplattformen senden. Die E-Email-Adressen müssen jedoch über Synchronisierungsdateien erfasst werden. Nachdem Audience Manager die E-Email-Adressen an die Zielplattformen sendet, müssen die Plattformen mit den E-Email-Adressen für ihre eigene Benutzerbasis übereinstimmen. Einige Plattformen verfügen möglicherweise über zusätzliche E-Email-Adressdiagramme, um Adressen abzugleichen, die von Audience Manager an Benutzerprofile gesendet werden.

## Datenexportkontrolle {#data-export-controls}

**Wie[!DNL Data Export Controls][!DNL People-Based Destinations]arbeiten Sie mit?**

[!DNL Data Export Controls] blockiert alle Segmente, die Daten aus Drittanbietern und Drittanbietern enthalten, an [!DNL People-Based Destinations]die Benutzer zu senden versuchen. [!DNL People-Based Destinations] dürfen nur Erstanbieterdaten für das Targeting verwendet werden. [!DNL Data Export Controls] sperren Sie auch Segmente [!DNL Profile Merge Rules] mit Gerätediagrammen. [!DNL People-Based Destinations] mit den entsprechenden, markierten Datenexportbeschriftungen erstellt und Sie können die Exporteinstellungen nicht überschreiben.

## Partnerspezifische Fragen {#partner-specific-questions}

### [!DNL Facebook]

**Was muss ich tun, bevor ich Zielgruppensegmente senden[!DNL Facebook]kann?**

Bevor Sie Zielgruppensegmente [!DNL People-Based Destinations] an Sie senden können, [!DNL Facebook]müssen Sie die folgenden Konfigurationsaufgaben ausführen:

1. Fügen Sie das Adobe Experience Cloud-Geschäftskonto als Werbepartner in Ihrem [!DNL Facebook Ad Account]Unternehmen hinzu. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter Partner zu Ihrem Business Manager hinzufügen.

   >[!IMPORTANT]
   >
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung Kampagnen verwalten aktivieren. Dies ist für die [!DNL People-Based Destinations] Integration erforderlich.

1. Lesen und signieren Sie die [!DNL Facebook Custom Audiences Terms of Service]. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wo `accountID` ist Ihre [!DNL Facebook Ad Account ID].

**[!DNL People-Based Destinations]Unterstützen Sie Zielgruppen-Targeting in anderen[!DNL Facebook]Apps, wie[!DNL Instagram]z. B.?**

Sie können [!DNL People-Based Destinations] die gesamte [!DNL Facebook]Familie von Apps verwenden, [!DNL Custom Audiences]die von, einschließlich [!DNL Facebook], [!DNL Instagram]und [!DNL Audience Network][!DNL Messenger]. Die Auswahl der App, mit der Sie Kampagne ausführen möchten, wird auf Platzierungsebene in [!DNL Facebook Ads Manager]angegeben.

**Was ist der Unterschied[!DNL People-Based Destinations]zwischen und[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] nutzt die [!DNL Custom Audiences (CA)] Integration mit [!DNL Facebook]. Der Unterschied zwischen und [!DNL WCA][!DNL CA] Integrationen ist der Schlüssel, den [!DNL Facebook]Kunden beim Senden von Zielgruppen verwenden. [!DNL WCA] verwendet das [!DNL Facebook] Pixel (was eine Website-ID ist), während [!DNL People-Based Destinations] Hash-E-Email-Adressen zur Integration verwendet werden [!DNL CA].

Sie können die [!DNL Facebook][!DNL WCA] Integration von Audience Manager über die [!DNL URL Destinations] Funktion ohne zusätzliche Kosten nutzen.

Diese beiden Integrationen ergänzen sich; Sie können beide verwenden, um eine bessere Zielgruppenabdeckung zu gewährleisten. Es kann beispielsweise [!DNL WCA] verwendet werden, wenn ein Unternehmen Ziel-Website-Besucher anstrebt, die ein Konto nicht registriert haben. Sie [!DNL People-Based Destinations] können jedoch auch bestehende Kunden ansprechen, die ihre E-Mail-Adresse angegeben haben, aber möglicherweise nicht die Website besucht haben.

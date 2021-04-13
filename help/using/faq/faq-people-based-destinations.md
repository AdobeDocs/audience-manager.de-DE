---
description: 'Antworten auf häufige Fragen zu benutzerbezogenen Zielen.  '
seo-description: 'Antworten auf häufige Fragen zu benutzerbezogenen Zielen.  '
seo-title: Häufig gestellte Fragen zu benutzerbezogenen Zielen
solution: Audience Manager
title: Häufig gestellte Fragen zu benutzerbezogenen Zielen
feature: Benutzerbasierte Ziele
exl-id: 56506bf0-45f1-49df-81ac-10f57a2487eb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 94%

---

# Häufig gestellte Fragen zu benutzerbezogenen Zielen {#people-based-destinations-faq}

Antworten auf häufige Fragen zu [!DNL People-Based Destinations].

## Verfügbarkeit {#availability}

**Ich kann in meinem Audience Manager-Konto keine [!DNL People-Based Destinations]. Was muss ich über die Verfügbarkeit wissen?**

[!DNL People-Based Destinations] ist eine Premium-Funktion von Audience Manager, die bei Kauf verfügbar ist. Informationen zu Preisen und Verfügbarkeit erhalten Sie von Ihrem Adobe-Vertriebsmitarbeiter.

## Datenintegration {#data-onboarding}

**Wie kann ich Kunden-E-Mail-Adressen in Audience Manager einbinden, damit ich sie in [!DNL People-Based Destinations] verwenden kann?**

Es gibt zwei Möglichkeiten, Ihre Offline-Daten für [!DNL People-Based Destinations] in Audience Manager zu laden.

* **Verwenden Sie die dateibasierte ID-Synchronisierung**. Einzelheiten dazu, wie ID-Synchronisierungsdateien aussehen sollten, finden Sie unter [Anforderungen an den Namen und den Inhalt von ID-Synchronisierungsdateien](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). Bei Verwendung dieser Methode können Sie alle Hash-E-Mail-Adressen aus Ihrer [!DNL CRM]-Datenbank ansprechen.
* **Verwenden Sie deklarierte IDs**, um beim Übergeben authentifizierter Kunden-IDs Hash-E-Mail-Adressen zu deklarieren. Bei Verwendung dieser Methode aktiviert Audience Manager nur die Hash-E-Mail-Adressen von Benutzern, die sich online authentifiziert haben. Die über Facebook aktivierten E-Mail-Adressen sind nur die Adressen in den deklarierten ID-Ereignisaufrufen. Andere mit der Kunden-ID verknüpfte E-Mail-Adressen werden nicht in Echtzeit aktiviert.

**Kann ich Hash-E-Mail-Adressen über ein Webformular oder eine App erfassen oder müssen sie in einer Batch-Datei vorliegen?**

Sie können Hash-E-Mail-Adressen durch Web-Authentifizierung mithilfe von [!DNL ECID] mit [deklarierten IDs](../features/declared-ids.md) erfassen. Mit der Batch-Datei können Sie auch Hash-E-Mail-Adressen erfassen, die nicht über eine Authentifizierung gesendet werden können (z. B. ruhende Benutzer in Ihrem ([!DNL CRM]), und sie in benutzerbezogenen Zielen aktivieren.

**Wie unterscheidet sich die Erfassung von Hash-E-Mail-Adressen über Web-Formulare vom Hochladen von Hash-E-Mail-Adressen über Batch-Dateien?**

Die Offline-Datenerfassung unterstützt Anwendungsfälle ohne Authentifizierung. Eine neue Profilzusammenführungsrichtlinie ([!UICONTROL All Cross-Device Profiles]), die unabhängig von der Authentifizierung für alle Offline-[!DNL CRM]-Profile ausgeführt wird, ist als Teil von [!DNL People-Based Destinations] verfügbar. Diese Methode soll die Erfassung authentifizierter Zielgruppen aus Online-Quellen ergänzen.

**Wie oft kann ich Hash-E-Mail-Adressen maximal senden/aktualisieren?**

* Bei Verwendung deklarierter IDs sendet Audience Manager die Hash-E-Mail-Adressen in Echtzeit an das Ziel.
* Beim Erfassen von Daten über ID-Synchronisierungsdateien verarbeitet Audience Manager diese täglich.

**Woher weiß ich, ob das Hashing der E-Mail-Adresse korrekt ausgeführt wurde?**

Audience Manager erfasst keine unverarbeiteten E-Mail-Adressen. Daher können wir nicht überprüfen, ob das Hashing korrekt ausgeführt wurde. Weitere Informationen dazu, wie Sie die integrierten Daten hashen sollten, finden Sie unter [Voraussetzungen und Überlegungen](../features/destinations/people-based-destinations-prerequisites.md).

## Profilzusammenführungsrichtlinien {#profile-merge-rules}

**Gibt es eine neue Profilzusammenführungsrichtlinie, die ich mit [!DNL People-Based Destinations] verwenden kann?**

Ja. Kunden, die [!DNL People-Based Destinations] gekauft haben, erhalten außerdem Zugriff auf eine neue Profilzusammenführungsrichtlinie für die Offline-Segmentierung. Die Richtlinie heißt [!DNL All Cross-Device Profiles] und wird für die reine Offline-Segmentierung verwendet. Wenn Sie sich für [!DNL People-Based Destinations] anmelden, ist dies die vierte Profilzusammenführungsrichtlinie, die Sie erstellen können, abgesehen von den drei vorhandenen authentifizierungsbasierten Richtlinien.

**Muss ich meine bestehenden Zielgruppensegmente duplizieren, um sie in [!DNL People-Based Destinations] zu aktivieren?**

Das hängt von Ihrem Anwendungsfall ab. Wenn Sie planen, vorhandene Erstanbietersegmente in benutzerbezogenen Kanälen zu aktivieren, müssen Sie keine neuen Segmente erstellen. Sie können die Segmente einfach einem benutzerbezogenen Ziel zuordnen.

Wenn Sie planen, neue Offline-Zielgruppen in benutzerbezogenen Kanälen zu aktivieren, müssen Sie neue Erstanbietersegmente mithilfe der Zusammenführungsrichtlinie [!DNL All Cross-Device Profiles] erstellen.
>[!NOTE]
>
> Sie können [!DNL People-Based Destinations] nur Segmente mit Erstanbieter-Daten zuordnen. Unsere Zielplattformen akzeptieren keine Segmente mit Daten von Zweit- und Drittanbietern.

## Übereinstimmungsraten {#match-rates}

**Haben [!DNL People-Based Destinations] Einblick in Übereinstimmungsraten oder adressierbare Zielgruppen?**

Nein. Beim Senden von Zielgruppensegmenten an [!DNL People-Based Destinations] erfolgt der Zielgruppenabgleich auf der Partnerseite. Adobe hat keinen Zugriff auf diese Metriken. Audience Manager zeigt Ihnen die maximal teilbare Zielgruppe für jedes Ziel und die Echtzeitanzahl der Personen, die zu einem Segment gehören. Diese Informationen können Ihnen bei der Planung und Prognose von Kampagnen helfen.

**Wie würden die Übereinstimmungsraten unter Verwendung von [!DNL People-Based Destinations] theoretisch im Vergleich zu anderen Methoden zum Senden von Zielgruppen an Zielplattformen aussehen?**

Solange die E-Mail-Adresse richtig gehashed und erfasst wird, sollte es keinen Unterschied in der Übereinstimmungsrate zwischen [!DNL People-Based Destinations] und anderen Methoden geben. Der einzige Grund, warum eine Übereinstimmungsrate unter 100 % liegt, ist, dass die in Audience Manager eingebrachten E-Mail-Adressen nicht mit einer E-Mail-Adresse in der Benutzerbasis der Zielplattform übereinstimmen können.

**Ich erfasse die geschäftlichen E-Mail-Adressen meiner Kunden, die sich von den in sozialen Netzwerken verwendeten persönlichen E-Mail-Adressen unterscheiden. Wie ordnet man Identitäten über mehrere E-Mail-Adressen hinweg zu?**

Audience Manager kann bis zu 10 E-Mails pro Benutzer sammeln und an Zielplattformen senden. Die E-Mail-Adressen müssen jedoch über Synchronisierungsdateien erfasst werden. Nachdem Audience Manager die E-Mail-Adressen an Zielplattformen gesendet hat, müssen die Plattformen die E-Mail-Adressen mit der eigenen Benutzerbasis abgleichen. Einige Plattformen verfügen möglicherweise über zusätzliche Diagramme für E-Mail-Adressen, die von Audience Manager an Benutzerprofile gesendet werden.

**Kann ich  [!DNL People-Based Destinations] in verwenden  [!DNL Audience Lab]?**

Nein. Derzeit sind alle [!DNL People-Based Destinations]-Ziele von [!DNL Audience Lab] ausgeschlossen. Da für [!DNL People-Based Destinations]- und nachfrageseitige Plattformen unterschiedliche IDs verwendet werden, können Sie die Performance nicht mit Audiencen testen und messen, die gleichmäßig auf sie aufgeteilt sind.

## Datenexportkontrollen {#data-export-controls}

**Wie funktionieren [!DNL Data Export Controls] mit [!DNL People-Based Destinations]?**

[!DNL Data Export Controls] blockiert alle Segmente, die Daten von Zweit- und Drittanbietern enthalten, die Benutzer versuchen, an [!DNL People-Based Destinations] zu senden. [!DNL People-Based Destinations] erlaubt nur die Verwendung von Erstanbieterdaten für die Zielgruppenbestimmung. [!DNL Data Export Controls] blockiert auch Segmente mit [!DNL Profile Merge Rules] Gerätediagrammen. [!DNL People-Based Destinations] werden mit den entsprechenden Beschriftungen für den Datenexport erstellt. Sie können die Exporteinstellungen nicht überschreiben.

## Partnerspezifische Fragen {#partner-specific-questions}

### [!DNL Facebook]

**Was muss ich tun, bevor ich Zielgruppensegmente an [!DNL Facebook] senden kann?**

Bevor Sie [!DNL People-Based Destinations] verwenden können, um Zielgruppensegmente an [!DNL Facebook] zu senden, müssen Sie die folgenden Konfigurationsaufgaben durchführen:

1. Fügen Sie das Adobe Experience Cloud-Geschäftskonto in Ihrem [!DNL Facebook Ad Account] als Werbepartner hinzu. Verwenden Sie `business ID=206617933627973`. Weitere Informationen finden Sie unter „Hinzufügen von Partnern zu Ihrem Business Manager“.

   >[!IMPORTANT]
   >
   > Beim Konfigurieren der Berechtigungen für Adobe Experience Cloud müssen Sie die Berechtigung „Kampagnen verwalten“ aktivieren. Dies ist für die Integration von [!DNL People-Based Destinations] erforderlich.

1. Lesen und unterschreiben Sie die [!DNL Facebook Custom Audiences Terms of Service]. Gehen Sie dazu zu `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, wobei `accountID` Ihre [!DNL Facebook Ad Account ID] ist.

**Unterstützt [!DNL People-Based Destinations] die Zielgruppenbestimmung in anderen [!DNL Facebook]-Apps wie z. B. [!DNL Instagram]?**

Sie können [!DNL People-Based Destinations] für die gesamte Familie von [!DNL Facebook]-Apps verwenden, die von [!DNL Custom Audiences] unterstützt werden, einschließlich [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] und [!DNL Messenger]. Die Auswahl der App, für die Sie die Kampagne ausführen möchten, wird auf der Platzierungsebene in [!DNL Facebook Ads Manager] angezeigt.

**Was ist der Unterschied zwischen [!DNL People-Based Destinations] und [!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] nutzt die Integration von [!DNL Custom Audiences (CA)] mit [!DNL Facebook]. Der Unterschied zwischen [!DNL WCA]-und [!DNL CA]-Integrationen ist der Schlüssel, den Kunden beim Senden von Zielgruppen an [!DNL Facebook] verwenden. [!DNL WCA] verwendet das [!DNL Facebook]-Pixel (d. h. eine Website-Benutzer-ID), während [!DNL People-Based Destinations] Hash-E-Mail-Adressen zur Integration mit [!DNL CA] verwenden.

Sie können die [!DNL Facebook] [!DNL WCA]-Integration von Audience Manager über die [!DNL URL Destinations]-Funktion ohne zusätzliche Kosten nutzen.

Diese beiden Integrationen ergänzen sich. Sie können beide verwenden, um eine bessere Zielgruppenabdeckung sicherzustellen. Beispielsweise kann [!DNL WCA] für die Identifizierung von potenziellen Kunden verwendet werden, wenn eine Firma Website-Besuchern ansprechen möchte, die noch kein Konto registriert haben, während [!DNL People-Based Destinations] Ihnen beim Ansprechen bestehender Kunden helfen können, die ihre E-Mail-Adresse angegeben, aber möglicherweise nicht die Website besucht haben.

**Wird durch die  [!DNL People-Based Destinations] Integration mit  [!DNL Facebook] Support die Qualifizierung von Benutzern für eine Audience aufgehoben, wenn diese sich nicht mehr dafür qualifizieren?**

Ja, die Integration unterstützt das Entfernen von Benutzern aus den [!DNL Facebook]-Audiencen, wenn sie sich nicht mehr für diese qualifizieren.

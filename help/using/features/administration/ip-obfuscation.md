---
description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Verschleierung von IP-Adressen
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 12%

---

# Verschleierung von IP-Adressen {#ip-obfuscation}

Verwenden Sie diese Funktion, um im Audience Manager erfasste IP-Adressen zu verschleiern.

## Überblick und Methodik {#overview-and-methodology}

Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.

### IP-Verschleierungsmethode

Gemäß den Grundsätzen des „eingebauten Datenschutzes“ ermöglicht Adobe Audience Manager Kunden die Aktivierung der IP-Verschleierung über die Benutzeroberfläche, entweder global über alle geografischen Regionen oder für bestimmte Länder. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in den Audience Manager aufgenommen wird. Der Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

* Vor der Verschleierung: `255.255.255.255`
* Nach der Verschleierung: `255.255.255.0`

Siehe auch Erfassen von IP-Adressen und Verschleierung von IP-Adressen in unserem [Abschnitt Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md).

### Priorität der IP-Verschleierung {#precedence}

[IP-Verschleierung auf Datenstromebene](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=de#create) hat Vorrang vor allen im Audience Manager festgelegten IP-Verschleierungsoptionen und wird auf alle IP-Adressen angewendet. Die Option [!UICONTROL IP obfuscation] auf Datenstromebene wirkt sich auf alle vom Audience Manager durchgeführten Geolokalisierungs-Suchen aus. Eine Geolokalisierung in Audience Manager, die auf einer vollständig verschleierten IP basiert, führt zu einer unbekannten Region, und alle Segmente, die auf den resultierenden Geolokalisierungsdaten basieren, werden nicht realisiert.

## Anforderungen an die IP-Adressverschleierung {#ip-obfuscation-requirements}

Die Verschleierung von IP-Adressen ist nur für Audience Manager-Administratorkonten verfügbar. Unter [Benutzer erstellen](/help/using/features/administration/administration-overview.md#create-users) erfahren Sie, wie Sie einem Benutzer Administratorberechtigungen zuweisen.

>[!NOTE]
>
> Aufgrund der großen Datenmenge, die vom Audience Manager verarbeitet wird, kann es bis zu 4 Stunden dauern, bis Änderungen an der IP-Verschleierung wirksam werden, sobald Sie die Einstellungen aktualisieren.

## Konfigurieren der Verschleierung von IP-Adressen {#configure-ip-obfuscation}

Gehen Sie wie folgt vor, um die Verschleierung von IP-Adressen zu konfigurieren.

1. Melden Sie sich mit einem Administratorkonto bei Audience Manager an und gehen Sie zu **Administration > Datenschutz**.
2. Wählen Sie die Art der IP-Verschleierung aus, die Sie verwenden möchten.
   1. **Alle IP-Adressen verschleiern:** Sie diese Option aus, damit der Audience Manager das letzte Oktett aller Besucher-IP-Adressen unabhängig von der Region verschleiert, aus der sie stammen.
   2. **IP-Adressen für bestimmte Länder verschleiern:** Sie diese Option aus, damit der Audience Manager das letzte Oktett von Besucher-IP-Adressen für bestimmte Länder verschleiert. Verwenden Sie die **Liste der Länder** oder das entsprechende Feld **Suche**, um die Länder zu finden, für die die IP-Verschleierung aktiviert werden soll, und klicken Sie auf das Symbol + , um sie der Liste **Für Verschleierung ausgewählt** hinzuzufügen. Nachdem Sie alle erforderlichen Länder zur Liste **Für Verschleierung ausgewählt“ hinzugefügt haben** klicken Sie auf **Speichern**.

![](assets/ip-obfuscation.png)

## Verschleierung von IP-Adressen deaktivieren {#disable-ip-obfuscation}

Um die Verschleierung von IP-Adressen global zu deaktivieren, gehen Sie zu **Administration > Datenschutz**, wählen Sie **IP-Adressen nicht verschleiern** und klicken Sie auf **Speichern**.

Um die Verschleierung von IP-Adressen für bestimmte Länder zu deaktivieren, suchen Sie die Länder in der Liste **Für Verschleierung ausgewählt** und klicken Sie dann auf das entsprechende **X**-Symbol. Klicken **abschließend** Speichern“.

## Verwandte Konzepte {#related-concepts}

* [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Videodemonstration zur Verschleierung von IP-Adressen
>[!VIDEO](https://video.tv.adobe.com/v/34968?captions=ger)

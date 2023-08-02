---
description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Verschleierung von IP-Adressen
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 14%

---

# Verschleierung von IP-Adressen {#ip-obfuscation}

Verwenden Sie diese Funktion, um in Audience Manager erfasste IP-Adressen zu verschleiern.

## Übersicht und Methodik {#overview-and-methodology}

Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.

### IP-Verschleierungsmethode

Gemäß den Grundsätzen von &quot;Privacy By Design&quot;ermöglicht es Adobe Audience Manager Kunden, die IP-Verschleierung über die Benutzeroberfläche zu aktivieren, entweder global in allen geografischen Regionen oder für bestimmte Länder. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in Audience Manager aufgenommen wird. Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

* Vor der Verschleierung: `255.255.255.255`
* Nach der Verschleierung: `255.255.255.0`

Siehe auch Erfassen von IP-Adressen und Verschleiern von IP-Adressen in unserer [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md).

### IP-Verschleierung - Rangfolge {#precedence}

[IP-Verschleierung auf Datenspeicherebene](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#create) hat Vorrang vor allen in Audience Manager festgelegten IP-Verschleierungsoptionen und wird auf alle IP-Adressen angewendet. Jede vom Audience Manager durchgeführte Geolocation-Suche wird von der Datenasterebene beeinflusst [!UICONTROL IP obfuscation] -Option. Eine auf einer vollständig verschleierten IP basierende Geolocation-Suche in Audience Manager führt zu einer unbekannten Region, und alle auf den resultierenden Geolocation-Daten basierenden Segmente werden nicht realisiert.

## Anforderungen an die Verschleierung von IP-Adressen {#ip-obfuscation-requirements}

Die Verschleierung von IP-Adressen ist nur für Audience Manager-Administratorkonten verfügbar. Siehe [Benutzer erstellen](/help/using/features/administration/administration-overview.md#create-users) um zu verstehen, wie Sie einem Benutzer Administratorberechtigungen zuweisen.

>[!NOTE]
>
> Aufgrund der großen Datenmenge, die von Audience Manager verarbeitet wird, kann es bis zu 4 Stunden dauern, bis Änderungen an der IP-Verschleierung wirksam werden, sobald Sie die Einstellungen aktualisieren.

## IP-Adressenverschleierung konfigurieren {#configure-ip-obfuscation}

Gehen Sie wie folgt vor, um die Verschleierung von IP-Adressen zu konfigurieren.

1. Melden Sie sich mit einem Administratorkonto bei Audience Manager an und wechseln Sie zu **Administration > Datenschutz**.
2. Wählen Sie den Typ der IP-Verschleierung aus, die Sie verwenden möchten.
   1. **Alle IP-Adressen verschleiern:** Wählen Sie diese Option aus, damit der Audience Manager das letzte Oktett aller Besucher-IP-Adressen verschleiert, unabhängig von der Region, aus der er stammt.
   2. **IP-Adressen für bestimmte Länder verschleiern:** Wählen Sie diese Option aus, damit der Audience Manager das letzte Oktett der Besucher-IP-Adressen für bestimmte Länder verschleiert. Verwenden Sie die **Liste der Länder** oder die entsprechenden **Suche** ein, um die Länder zu finden, für die die IP-Verschleierung aktiviert werden soll, und auf das Symbol + klicken, um sie zum **Auswahl zur Verschleierung** Liste. Nachdem Sie alle erforderlichen Länder zum **Auswahl zur Verschleierung** Liste, klicken Sie **Speichern**.

![](assets/ip-obfuscation.png)

## IP-Adressenverschleierung deaktivieren {#disable-ip-obfuscation}

Um die Verschleierung von IP-Adressen global zu deaktivieren, navigieren Sie zu **Administration > Datenschutz** auswählen **IP-Adressen nicht verschleiern** und klicken Sie auf **Speichern**.

Um die Verschleierung von IP-Adressen für bestimmte Länder zu deaktivieren, suchen Sie die Länder in der **Auswahl zur Verschleierung** Liste und klicken Sie dann auf die entsprechenden **X** Symbol. Klicks **Speichern** wenn Sie fertig sind.

## Verwandte Konzepte {#related-concepts}

* [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video-Demonstration zur Verschleierung von IP-Adressen
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

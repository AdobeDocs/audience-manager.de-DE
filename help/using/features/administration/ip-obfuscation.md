---
description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
seo-description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
solution: Audience Manager
title: Verschleierung von IP-Adressen
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# Verschleierung von IP-Adressen {#ip-obfuscation}

Verwenden Sie diese Funktion, um in Audience Manager erfasste IP-Adressen zu verschleiern.

## Übersicht und Methodik {#overview-and-methodology}

Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.

### IP-Verschleierungsmethode

Nach den Prinzipien von &quot;Datenschutz nach Design&quot; erlaubt Adobe Audience Manager Kunden, IP-Verschleierung aus der Benutzeroberfläche zu aktivieren, entweder global in allen geografischen Regionen oder in bestimmten Ländern. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in Audience Manager übernommen wird. Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (einschließlich vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

* Vor der Verschleierung: `255.255.255.255`
* Nach der Verschleierung: `255.255.255.0`

Siehe auch Erfassen von IP-Adressen und IP-Adressenverschleierung in unserem [Abschnitt Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Voraussetzungen für die Verschleierung von IP-Adressen {#ip-obfuscation-requirements}

Die IP-Adressenverschleierung ist nur für Audience Manager-Administratorkonten verfügbar. Siehe [Erstellen von Benutzern](/help/using/features/administration/administration-overview.md#create-users) zum Zuweisen von Administratorberechtigungen für einen Benutzer.

>[!NOTE]
>
> Aufgrund des großen Datenvolumens von Audience Manager können die IP-Verschleierungsänderungen bis zu 4 Stunden in Kraft treten, bis Sie die Einstellungen aktualisieren.

## IP-Adressenverschleierung konfigurieren {#configure-ip-obfuscation}

Gehen Sie wie folgt vor, um die IP-Adressenverschleierung zu konfigurieren.

1. Melden Sie sich bei Audience Manager mit einem Administratorkonto an und wechseln Sie zu **Administration &gt; Datenschutz**.
2. Wählen Sie den Typ der IP-Verschleierung aus, die Sie verwenden möchten.
   1. **Alle IP-Adressen verschleiern:** Wählen Sie diese Option, damit Audience Manager das letzte Oktett aller Besucher-IP-Adressen unabhängig von der Region, von der sie stammen, verschleiern lassen.
   2. **IP-Adressen für bestimmte Länder verschleiern:** Wählen Sie diese Option, damit Audience Manager das letzte Oktett der Besucher-IP-Adressen für bestimmte Länder verschleiern kann. Verwenden Sie **die Liste der Länder** oder das entsprechende **Suchfeld** , um die Länder zu finden, um die IP-Verschleierung zu aktivieren, und klicken Sie auf das +-Symbol, um sie zur Option **&quot;Für Verschleierung** ausgewählt&quot; hinzuzufügen. Nachdem Sie alle erforderlichen Länder zur Liste **&quot;Ausgewählt&quot; hinzugefügt haben, klicken** Sie auf **Speichern**.

![](assets/ip-obfuscation.png)

## IP-Adressenverschleierung deaktivieren {#disable-ip-obfuscation}

Um die IP-Adressenverschleierung global zu deaktivieren, wechseln Sie zu **Administration &gt; Datenschutz**, wählen Sie **IP-Adressen nicht verschleiern** und klicken Sie auf **Speichern**.

Um die IP-Adressenverschleierung für bestimmte Länder zu deaktivieren, suchen Sie die Länder in der Liste **&quot;Für Verschleierung** ausgewählt&quot; und klicken Sie dann auf das entsprechende **X** -Symbol. Klicken **Sie auf Speichern,** wenn Sie fertig sind.

## Verwandte Konzepte {#related-concepts}

* [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP-Adressenverschleierung der Videodemonstration
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=ger)


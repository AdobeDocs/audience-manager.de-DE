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

Gemäß den Grundsätzen von "Privacy By Design"ermöglicht Adobe Audience Manager Kunden, die IP-Verschleierung über die Benutzeroberfläche zu aktivieren, entweder global über alle geografischen Regionen oder für bestimmte Länder. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in Audience Manager aufgenommen wird. Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

* Vor Verschleierung: `255.255.255.255`
* Nach Verschleierung: `255.255.255.0`

Siehe auch Erfassen von IP-Adressen und IP-Adressenverschleierung in unserem [Datenschutz-Abschnitt](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Anforderungen an die IP-Adressenverschleierung {#ip-obfuscation-requirements}

Die Verschleierung der IP-Adresse ist nur für Audience Manager-Administratorkonten verfügbar. Informationen zum Zuweisen von Administratorberechtigungen für einen Benutzer finden Sie unter Benutzer [erstellen](/help/using/features/administration/administration-overview.md#create-users) .

>[!NOTE]
>
> Aufgrund der großen Datenmenge, die von Audience Manager verarbeitet wird, können Änderungen der IP-Verschleierung bis zu 4 Stunden in Kraft treten, sobald Sie die Einstellungen aktualisieren.

## IP-Adressenverschleierung konfigurieren {#configure-ip-obfuscation}

Gehen Sie wie folgt vor, um die IP-Adressenverschleierung zu konfigurieren.

1. Melden Sie sich mit einem Administratorkonto bei Audience Manager an und gehen Sie zu **Administration &gt; Datenschutz**.
2. Wählen Sie die Art der IP-Verschleierung, die Sie verwenden möchten.
   1. **** Alle IP-Adressen verschleiern: Wählen Sie diese Option, damit Audience Manager das letzte Oktett aller Besucher-IP-Adressen unabhängig von der Region verschleiert, aus der sie stammen.
   2. **** IP-Adressen für bestimmte Länder verschleiern: Wählen Sie diese Option, damit Audience Manager das letzte Oktett der Besucher-IP-Adressen für bestimmte Länder verschleiert. Verwenden Sie das Feld **Liste der Länder** oder das entsprechende Feld **Suche** , um die Länder zu finden, für die die IP-Verschleierung aktiviert werden soll, und klicken Sie auf das Symbol +, um sie der Liste **Ausgewählte zur Verschleierung** hinzuzufügen. Nachdem Sie alle erforderlichen Länder zur Liste " **Ausgewählte zur Verschleierung** "hinzugefügt haben, klicken Sie auf **Speichern**.

![](assets/ip-obfuscation.png)

## IP-Adressenverschleierung deaktivieren {#disable-ip-obfuscation}

Um die IP-Adressenverschleierung global zu deaktivieren, wählen Sie **Administration &gt; Datenschutz**, wählen Sie **IP-Adressen** nicht verschleiern und klicken Sie auf **Speichern**.

Um die IP-Adressenverschleierung für bestimmte Länder zu deaktivieren, suchen Sie die Länder in der Liste **Ausgewählte zur Verschleierung** und klicken Sie dann auf das entsprechende **X** -Symbol. Click **Save** when you're done.

## Verwandte Konzepte {#related-concepts}

* [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video-Demonstration zur IP-Adressenverschleierung
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=ger)


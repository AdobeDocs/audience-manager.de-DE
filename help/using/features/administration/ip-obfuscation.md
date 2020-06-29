---
description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
seo-description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
solution: Audience Manager
title: Verschleierung von IP-Adressen
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 22%

---


# Verschleierung von IP-Adressen {#ip-obfuscation}

Verwenden Sie diese Funktion, um in Audience Manager erfasste IP-Adressen zu verschleiern.

## Übersicht und Methodik {#overview-and-methodology}

Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.

### IP-Verschleierungsmethode

Gemäß den Grundsätzen von &quot;Privacy By Design&quot;ermöglicht Adobe Audience Manager Kunden die Aktivierung der IP-Verschleierung über die Benutzeroberfläche, entweder global in allen geografischen Regionen oder für bestimmte Länder. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in Audience Manager aufgenommen wird. Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

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

1. Melden Sie sich mit einem Administratorkonto bei Audience Manager an und gehen Sie zu **Administration > Datenschutz**.
2. Wählen Sie die Art der IP-Verschleierung, die Sie verwenden möchten.
   1. **Alle IP-Adressen verschleiern:** Wählen Sie diese Option, um Audience Manager das letzte Oktett aller Besucher-IP-Adressen unabhängig von der Region, aus der sie stammen, zu verschleiern.
   2. **IP-Adressen für bestimmte Länder verschleiern:** Wählen Sie diese Option, um Audience Manager für das letzte Oktett der IP-Adressen von Besuchern für bestimmte Länder zu verschleiern. Verwenden Sie die **Liste von Ländern** oder das entsprechende Feld für die **Suche** , um die Länder zu finden, für die die IP-Verschleierung aktiviert werden soll, und klicken Sie auf das +-Symbol, um sie der Liste &quot;Zur Verschleierung **ausgewählt&quot;hinzuzufügen** . Nachdem Sie alle erforderlichen Länder zur Liste **Ausgewählte zur Verschleierung** hinzugefügt haben, klicken Sie auf **Speichern**.

![](assets/ip-obfuscation.png)

## IP-Adressenverschleierung deaktivieren {#disable-ip-obfuscation}

Um die IP-Adressenverschleierung global zu deaktivieren, wählen Sie **Administration > Datenschutz**, wählen Sie **IP-Adressen** nicht verschleiern und klicken Sie auf **Speichern**.

Um die Verschleierung der IP-Adresse für bestimmte Länder zu deaktivieren, suchen Sie die Länder in der Liste **Ausgewählte zur Verschleierung** und klicken Sie dann auf das entsprechende **X** -Symbol. Click **Save** when you&#39;re done.

## Verwandte Konzepte {#related-concepts}

* [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video-Demonstration zur IP-Adressenverschleierung
>[!VIDEO](https://video.tv.adobe.com/v/27218/)


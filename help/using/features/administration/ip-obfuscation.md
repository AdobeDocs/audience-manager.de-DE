---
description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
seo-description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
solution: Audience Manager
title: Verschleierung von IP-Adressen
feature: Datenverwaltung und Datenschutz
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# Verschleierung von IP-Adressen {#ip-obfuscation}

Verwenden Sie diese Funktion, um in Audience Manager erfasste IP-Adressen zu verschleiern.

## Übersicht und Methodik {#overview-and-methodology}

Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.

### IP-Verschleierungsmethode

Gemäß den Grundsätzen von &quot;Privacy By Design&quot;ermöglicht es Adobe Audience Manager Kunden, die IP-Verschleierung über die Benutzeroberfläche zu aktivieren, entweder global in allen geografischen Regionen oder für bestimmte Länder. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in Audience Manager aufgenommen wird. Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

* Vor Verschleierung: `255.255.255.255`
* Nach Verschleierung: `255.255.255.0`

Siehe auch Erfassen von IP-Adressen und IP-Adressenverschleierung in unserem [Datenschutz-Abschnitt](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP-Adressenverschleierung {#ip-obfuscation-requirements}

Die Verschleierung der IP-Adresse ist nur für Audience Manager-Administratorkonten verfügbar. Informationen zum Zuweisen von Administratorberechtigungen für einen Benutzer finden Sie unter [Benutzer erstellen](/help/using/features/administration/administration-overview.md#create-users).

>[!NOTE]
>
> Aufgrund der großen Datenmenge, die von Audience Manager verarbeitet wird, können Änderungen der IP-Verschleierung bis zu 4 Stunden in Kraft treten, sobald Sie die Einstellungen aktualisieren.

## IP-Adressenverschleierung konfigurieren {#configure-ip-obfuscation}

Gehen Sie wie folgt vor, um die IP-Adressenverschleierung zu konfigurieren.

1. Melden Sie sich bei Audience Manager mit einem Administratorkonto an und gehen Sie zu **Administration > Privacy**.
2. Wählen Sie die Art der IP-Verschleierung, die Sie verwenden möchten.
   1. **Alle IP-Adressen verschleiern:** Wählen Sie diese Option, damit Audience Manager das letzte Oktett aller Besucher-IP-Adressen verschleiern kann, unabhängig davon, aus welcher Region sie stammen.
   2. **IP-Adressen für bestimmte Länder verschleiern:** Wählen Sie diese Option, um den Audience Manager über das letzte Oktett der IP-Adressen von Besuchern für bestimmte Länder hinwegtäuschen zu lassen. Verwenden Sie das Feld **Liste der Länder** oder das entsprechende Feld **Suche**, um die Länder zu finden, für die IP-Verschleierung aktiviert werden soll, und klicken Sie auf das Symbol +, um sie der Liste **Ausgewählte für Verschleierung** hinzuzufügen. Nachdem Sie alle erforderlichen Länder zur Liste **Ausgewählte für Verschleierung** hinzugefügt haben, klicken Sie auf **Speichern**.

![](assets/ip-obfuscation.png)

## IP-Adressenverschleierung {#disable-ip-obfuscation} deaktivieren

Um die IP-Adressenverschleierung global zu deaktivieren, gehen Sie zu **Administration > Privacy**, wählen Sie **IP-Adressen nicht verschleiern** und klicken Sie auf **Speichern**.

Um die IP-Adressenverschleierung für bestimmte Länder zu deaktivieren, suchen Sie die Länder in der Liste **Ausgewählte für Verschleierung** und klicken Sie dann auf das entsprechende Symbol **X**. Klicken Sie auf **Speichern**, wenn Sie fertig sind.

## Verwandte Konzepte {#related-concepts}

* [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video-Demonstration zur IP-Adressenverschleierung
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

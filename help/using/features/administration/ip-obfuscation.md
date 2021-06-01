---
description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
seo-description: Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.
solution: Audience Manager
title: Verschleierung von IP-Adressen
feature: Data Governance und Datenschutz
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
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

* Vor der Verschleierung: `255.255.255.255`
* Nach der Verschleierung: `255.255.255.0`

Siehe auch Erfassen von IP-Adressen und Verschleierung von IP-Adressen in unserem [Datenschutz-Abschnitt](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Anforderungen an die Verschleierung von IP-Adressen {#ip-obfuscation-requirements}

Die Verschleierung von IP-Adressen ist nur für Audience Manager-Administratorkonten verfügbar. Informationen zum Zuweisen von Administratorrechten für einen Benutzer finden Sie unter [Benutzer erstellen](/help/using/features/administration/administration-overview.md#create-users) .

>[!NOTE]
>
> Aufgrund der großen Datenmenge, die von Audience Manager verarbeitet wird, kann es bis zu 4 Stunden dauern, bis Änderungen an der IP-Verschleierung wirksam werden, sobald Sie die Einstellungen aktualisieren.

## IP-Adressenverschleierung konfigurieren {#configure-ip-obfuscation}

Gehen Sie wie folgt vor, um die Verschleierung von IP-Adressen zu konfigurieren.

1. Melden Sie sich mit einem Administratorkonto bei Audience Manager an und gehen Sie zu **Administration > Datenschutz**.
2. Wählen Sie den gewünschten IP-Verschleierungstyp aus.
   1. **Alle IP-Adressen verschleiern:** Wählen Sie diese Option, damit Audience Manager das letzte Oktett aller Besucher-IP-Adressen verschleiern kann, unabhängig davon, aus welcher Region sie stammen.
   2. **IP-Adressen für bestimmte Länder verschleiern:** Wählen Sie diese Option, damit der Audience Manager das letzte Oktett der Besucher-IP-Adressen für bestimmte Länder verschleiert. Verwenden Sie das Feld **Liste der Länder** oder das entsprechende Feld **Suche**, um die Länder zu finden, für die die IP-Verschleierung aktiviert werden soll, und klicken Sie auf das Symbol + , um sie zur Liste **Ausgewählte Länder für Verschleierung** hinzuzufügen. Nachdem Sie alle erforderlichen Länder zur Liste **Ausgewählt für Verschleierung** hinzugefügt haben, klicken Sie auf **Speichern**.

![](assets/ip-obfuscation.png)

## IP-Adressenverschleierung deaktivieren {#disable-ip-obfuscation}

Um die Verschleierung von IP-Adressen global zu deaktivieren, gehen Sie zu **Administration > Datenschutz**, wählen Sie **IP-Adressen nicht verschleiern** aus und klicken Sie auf **Speichern**.

Um die Verschleierung von IP-Adressen für bestimmte Länder zu deaktivieren, suchen Sie die Länder in der Liste **Ausgewählt für Verschleierung** und klicken Sie dann auf das entsprechende Symbol **X**. Klicken Sie auf **Speichern** , wenn Sie fertig sind.

## Verwandte Konzepte {#related-concepts}

* [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Video-Demonstration zur Verschleierung von IP-Adressen
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

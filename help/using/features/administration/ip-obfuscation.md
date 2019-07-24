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

## Overview and Methodology {#overview-and-methodology}

Aufgrund globaler Datenschutzregeln muss Ihr Unternehmen in einigen Ländern möglicherweise IP-Adressen verschleiern. Mit Audience Manager können Sie die IP-Adressen der Besucher auf globaler oder Länderebene verschleiern.

### IP-Verschleierungsmethode

Nach den Prinzipien von "Datenschutz nach Design" erlaubt Adobe Audience Manager Kunden, IP-Verschleierung aus der Benutzeroberfläche zu aktivieren, entweder global in allen geografischen Regionen oder in bestimmten Ländern. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in Audience Manager übernommen wird. Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (einschließlich vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

Die IP-Adressenverschleierung ist nur für Audience Manager-Administratorkonten verfügbar. See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> Aufgrund des großen Datenvolumens von Audience Manager können die IP-Verschleierungsänderungen bis zu 4 Stunden in Kraft treten, bis Sie die Einstellungen aktualisieren.

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

Gehen Sie wie folgt vor, um die IP-Adressenverschleierung zu konfigurieren.

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. Wählen Sie den Typ der IP-Verschleierung aus, die Sie verwenden möchten.
   1. **Alle IP-Adressen verschleiern:** Wählen Sie diese Option, damit Audience Manager das letzte Oktett aller Besucher-IP-Adressen unabhängig von der Region, von der sie stammen, verschleiern lassen.
   2. **IP-Adressen für bestimmte Länder verschleiern:** Wählen Sie diese Option, damit Audience Manager das letzte Oktett der Besucher-IP-Adressen für bestimmte Länder verschleiern kann. Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you've added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you're done.

## Verwandte Konzepte {#related-concepts}

* [Datenschutz](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP-Adressenverschleierung der Videodemonstration
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=ger)


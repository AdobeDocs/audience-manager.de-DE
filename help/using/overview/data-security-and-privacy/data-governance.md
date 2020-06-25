---
description: In diesem Dokument wird erläutert, wie Kundendaten in Audience Manager geregelt werden.
seo-description: In diesem Dokument wird erläutert, wie die Kundendaten im Audience Manager geregelt werden.
seo-title: Datenverwaltung
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Datenverwaltung
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 1%

---


# Datenverwaltung

## Überblick {#overview}

Die Datenverwaltung in Audience Manager bezieht sich auf den Lebenszyklus Ihrer Kundendaten in Audience Manager und umfasst die [Erfassung und Verschleierung von IP-Adressen](data-governance.md#collecting-ip-addresses), die [Datenaufbewahrung](data-governance.md#data-retention)und [grenzüberschreitende Datenübertragungen](data-governance.md#data-transfers).

## Erfassen von IP-Adressen und IP-Adressenverschleierung {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**IP-Verschleierungsmethode:** Gemäß den Grundsätzen von &quot;Privacy By Design&quot;ermöglicht Adobe Audience Manager Kunden, die [!DNL IP] Verschleierung der Benutzeroberfläche zu aktivieren, entweder global über alle geografischen Regionen oder für bestimmte Länder. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der [!DNL IP] Adresse sofort verworfen, wenn die [!DNL IP] Adresse in Audience Manager aufgenommen wird. Audience Manager verwirft diesen Teil der [!DNL IP] Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der [!DNL IP] Adresse). Beispiel:

* Bevor: `255.255.255.255`
* Nachher: `255.255.255.0`

>[!NOTE]
>
>Siehe [IP-Adressenverschleierung](../../features/administration/ip-obfuscation.md) , um zu erfahren, wie Sie die [!DNL IP] Adressenverschleierung in der Benutzeroberfläche des Audience Managers aktivieren.

Sehen Sie sich das unten stehende Video an, um zu verstehen, wie [!DNL IP] Adressenverschleierung in Audience Manager funktioniert.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geografische Segmentierung:** Wenn Sie die [!DNL IP] Adressenverschleierung aktivieren, können die verbleibenden Oktette der [!DNL IP] Adresse weiterhin für die Geo-Segmentierung und den Berichte in Audience Manager verwendet werden. Wenn Sie die [!DNL IP] Adressenverschleierung nicht aktivieren, verwendet Audience Manager die vollständige [!DNL IP] Adresse. Sie können die Funktion Geografische Segmentierung verwenden, mit der Sie einen Standort in jedem Fall nach geografischem Gebiet identifizieren können. Bei der Verwendung der [!DNL IP] [!DNL IP] Verschleierung ist die Genauigkeit jedoch etwas geringer. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. Das Abrufen von Informationen auf Regions- und Landesebene sollte nur geringfügig beeinträchtigt werden. Geografische Segmentierungsdaten sind nur auf der Ebene der Stadt oder der Postleitzahl granular und nicht auf der Ebene der einzelnen Personen. Erfahren Sie mehr über das [Geo-Targeting](../../features/traits/trait-geotarget-keys.md) und das Einrichten von Eigenschaften mit geografischen Variablen.

## Datenaufbewahrung im Audience Manager {#data-retention}

Die Anwendung geeigneter, sicherer und zeitnaher Datenaufbewahrungsrichtlinien auf Ihre Daten ist ein wichtiger Teil der Einhaltung der Datenschutzbestimmungen. Audience Manager Kunden haben die Möglichkeit, benutzerspezifische Aufbewahrungszeiträume für Eigenschaften und Segmente festzulegen, indem sie die erforderliche TTL (Time to Live) definieren. Weitere Informationen zu Aufbewahrungszeiträumen finden Sie unter Häufig gestellte Fragen zur [Datenaufbewahrung](../../faq/faq-privacy.md) .

## Grenzübergreifende Datenübertragung {#data-transfers}

Wenn Audience Manager personenbezogene Daten von Kunden über Landesgrenzen hinweg übermittelt, erfolgt dies in Übereinstimmung mit dem geltenden Recht. Weitere Informationen erhalten Sie im [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) .
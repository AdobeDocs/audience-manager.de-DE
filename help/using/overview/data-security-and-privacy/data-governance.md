---
description: In diesem Dokument wird erläutert, wie Kundendaten im Audience Manager verwaltet werden.
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: DSGVO-Benutzeroberfläche, DSGVO-API, CCPA, Datenschutz, Einverständnis, Verschleierung, Governance
title: Data Governance
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 90%

---

# Data Governance

## Überblick {#overview}

Data Governance in Audience Manager bezieht sich auf den Lebenszyklus Ihrer Kundendaten in Audience Manager und umfasst das [Erfassen und Verschleiern von IP-Adressen](data-governance.md#collecting-ip-addresses), die [Aufbewahrung von Daten](data-governance.md#data-retention) und [grenzüberschreitende Datenübertragungen](data-governance.md#data-transfers).

## Erfassen von IP-Adressen und Verschleierung von IP-Adressen {#collecting-ip-addresses}

Die [!DNL IP]-Adresse eines Besuchers auf der Website eines Kunden wird an das [!DNL Data Processing Center] von Adobe ([!DNL DPC]) übertragen, wo die [!DNL IP]-Adresse möglicherweise gespeichert wird. Abhängig von der Netzwerkkonfiguration des Besuchers entspricht die [!DNL IP]-Adresse nicht unbedingt der [!DNL IP]-Adresse des Computers des Besuchers. Bei der [!DNL IP]-Adresse kann es sich z. B. um die externe [!DNL IP]-Adresse einer Network Address Translation-(NAT-)Firewall, eines [!DNL HTTP]-Proxys oder eines Internet-Gateways handeln.

**IP-Verschleierungsmethode:** Nach den Grundsätzen von „Privacy By Design“ können Kunden mit Adobe Audience Manager die [!DNL IP]-Verschleierung über die Benutzeroberfläche entweder global in allen geografischen Regionen oder für bestimmte Länder aktivieren. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der [!DNL IP]-Adresse sofort verworfen, wenn die [!DNL IP]-Adresse in Audience Manager erfasst wird. Audience Manager verwirft diesen Teil der [!DNL IP]-Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der [!DNL IP]-Adresse). Beispiel:

* Vorher: `255.255.255.255`
* Nachher: `255.255.255.0`

>[!NOTE]
>
>Unter [IP-Adressverschleierung](../../features/administration/ip-obfuscation.md) erfahren Sie, wie Sie die [!DNL IP] in der Benutzeroberfläche des Audience Managers aktivieren.

Sehen Sie sich das folgende Video an, um zu verstehen, wie die Verschleierung von [!DNL IP]-Adressen in Audience Manager funktioniert.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geografische Segmentierung:** Wenn Sie die Verschleierung von [!DNL IP]-Adressen aktivieren, können die verbleibenden Oktette der [!DNL IP]-Adresse weiterhin für die Geo-Segmentierung und das Reporting in Audience Manager verwendet werden. Wenn Sie die Verschleierung von [!DNL IP]-Adressen nicht aktivieren, verwendet Audience Manager die vollständige [!DNL IP]-Adresse. Sie können die Funktion zur geografischen Segmentierung verwenden, mit der Sie in beiden Fällen einen [!DNL IP]-Standort nach geografischem Gebiet identifizieren können, jedoch mit einem leichten Genauigkeitsverlust, wenn die [!DNL IP]-Verschleierung verwendet wird. Das Ermitteln von Information auf Stadtebene wird durch die Verschleierung der [!DNL IP]-Adresse wahrscheinlich merklich beeinträchtigt. Das Ermitteln von Informationen auf Regionen- und Landesebene dürfte nur leicht beeinträchtigt sein. Die geographischen Segmentierungsdaten sind nur auf Stadt- oder Postleitzahlenebene und nicht auf individueller Ebene detailliert. Erfahren Sie mehr über das [Geotargeting](../../features/traits/trait-geotarget-keys.md) und das Einrichten von Eigenschaften mit geografischen Variablen.

## Datenaufbewahrung im Audience Manager {#data-retention}

Die Anwendung geeigneter, sicherer und zeitgerechter Datenaufbewahrungsrichtlinien auf Ihre Daten ist ein wichtiger Teil der Einhaltung der Datenschutzbestimmungen. Audience Manager-Kunden können benutzerdefinierte Aufbewahrungsfristen für Eigenschaften und Segmente festlegen, indem sie die erforderliche TTL (Time to Live) definieren. Weitere Informationen zu Aufbewahrungsfristen finden Sie unter [Häufig gestellte Fragen zur Datenaufbewahrung](../../faq/faq-privacy.md).

## Grenzüberschreitende Datenübermittlungen {#data-transfers}

Wenn Audience Manager personenbezogene Daten von Kunden über Landesgrenzen hinweg übermittelt, geschieht dies in Übereinstimmung mit geltendem Recht. Weitere Informationen finden Sie im [Datenschutzzentrum von Adobe](https://www.adobe.com/de/privacy/eudatatransfers.html).

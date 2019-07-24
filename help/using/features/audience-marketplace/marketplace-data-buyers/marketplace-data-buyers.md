---
description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern aus Audience Manager kaufen möchten
seo-description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern aus Audience Manager kaufen möchten
seo-title: Audience Marketplace für Datenkäufer
solution: Audience Manager
title: Audience Marketplace für Datenkäufer
topic: DIL-API
uuid: f 505 b 5 f 4-4231-4 e 84-993 a-cd 64128 b 540 f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace for Data Buyers {#audience-marketplace-for-data-buyers}

Overview and workflow for data buyers who want to purchase third-party data from within [!DNL Audience Manager].

>[!NOTE]
>[Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf [!UICONTROL Audience Marketplace] Funktionen.
>
>* Administratoren können Datenfeeds erstellen, Abonnenten verwalten und Datenfeeds abonnieren.
>* Benutzer können Feeds nur suchen und anzeigen.


## The Marketplace: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

The [!UICONTROL Marketplace] is an [!DNL Audience Manager] feature for data buyers that lists data feeds you can subscribe to. It lists flat rate, [!DNL CPM], or private data feeds. These feeds are provided by third-party vendors that use [!DNL Audience Manager] to sell data. In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your traits and those in a subscribed data feed. Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). Mit diesen Funktionen können Sie effektive Datenquellen suchen, ohne die Suche nach einem Datenanbieter zu verlieren.

>[!TIP]
> 
>Use the **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** to find high quality data feeds that you can subscribe to. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

The [!UICONTROL Marketplace] list contains information that you can sort and search to find the data feed that's right for you. Items in the [!UICONTROL Marketplace] buyer's list include:

* **[!UICONTROL Search]:** Suchen Sie Datenfeeds nach Name oder Textbeschreibung.
* **[!UICONTROL Name]:** Name des Datenfeeds.
* **[!UICONTROL Description]:** Informationen über den Inhalt eines Datenfeeds.
* **[!UICONTROL Provider]:** Name des Datenproviders.
* **[!UICONTROL Traits]:** Die Anzahl der Eigenschaften in einem Datenfeed.
* **[!UICONTROL 30 Day Provider Unique Users]:** Die Anzahl der Unique Users, die in den letzten 30 Tagen angesehen wurden.
* **[!UICONTROL 30 Day Overlapped Uniques]:** Die Anzahl der Benutzer in Ihrem Konto, die mit den Benutzern im Konto des Anbieters überlappen.
* **[!UICONTROL Feed Overlap]:** Der 30-Tage-Wert für individuelle Werte, der in Prozentsätzen angezeigt wurde, berechnet als: Datenkäufer 30 Tage überlappend individuelle/Datenkäufer 30 Tag pro Tag) x 100.
* **[!UICONTROL Private Feeds]:** Siehe [Private Datenfeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]:** Die Anzahl der Abonnements mit einem Datenanbieter.

## Private Daten-Feeds {#private-data-feeds}

In the [!UICONTROL Marketplace] list, sometimes the provider's name and trait data are marked as private. This indicates a [private data feed](../../../features/audience-marketplace/marketplace-private-feeds.md). Ein privater Datenfeed ermöglicht den Käufern den Zugriff auf ihre Daten einzuschränken. Verkäufer können Feeds privat schalten, wenn sie spezielle Angebote, Rabatte oder Zugriffsrechte und Zugriffssteuerungsmöglichkeiten anbieten. Als Käufer müssen Sie eine Abonnementanfrage an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed benötigen. See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_ LIKE_ THIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)


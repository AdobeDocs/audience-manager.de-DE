---
description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern in Audience Manager erwerben möchten
seo-description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern in Audience Manager erwerben möchten
seo-title: Audience Marketplace für Datenkäufer
solution: Audience Manager
title: Audience Marketplace für Datenkäufer
topic: DIL-API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace für Datenkäufer {#audience-marketplace-for-data-buyers}

Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern von innerhalb [!DNL Audience Manager]der Website erwerben möchten.

>[!NOTE]
>[Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf [!UICONTROL Audience Marketplace] Funktionen.
>
>* Administratoren können Datenfeeds erstellen, Abonnenten verwalten und Datenfeeds abonnieren.
>* Benutzer können nur Feeds suchen und anzeigen.


## Der Marktplatz: Info {#about-marketplace}

<!-- c_marketplace_about.xml -->

Das [!UICONTROL Marketplace] ist eine [!DNL Audience Manager] Funktion für Datenkäufer, die Datenfeeds auflistet, die Sie abonnieren können. Er listet pauschale, [!DNL CPM]oder private Datenfeeds auf. Diese Feeds werden von Drittanbietern bereitgestellt, die Daten [!DNL Audience Manager] zum Verkauf verwenden. Mit den [!UICONTROL Marketplace]Berichterstellungstools können Sie die Nutzung von Feeds und die Überschneidung zwischen Ihren Eigenschaften und denen in einem abonnierten Data Feed verfolgen. Schließlich, mit [!UICONTROL Audience Marketplace]der [!DNL Adobe] kümmert sich um Rechnungen und Gebührenzahlungen (obwohl Sie die Nutzung selbst melden müssen, wenn Sie ein Feed abonniert [!DNL CPM] ). Mit diesen Funktionen können Sie effektive Datenquellen finden, ohne Zeit mit der Suche nach einem Datenanbieter zu verschwenden.

>[!TIP]
> 
>Verwenden Sie den **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** , um hochwertige Datenfeeds zu finden, die Sie abonnieren können. Gehen Sie dann zurück zur Benutzeroberfläche von Audience Manager oder verwenden Sie die [Audience Marketplace-Käufer-API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) , um die von Ihnen gefundenen Feeds zu abonnieren.

![](assets/buyer_marketplace.png)

Die [!UICONTROL Marketplace] Liste enthält Informationen, die Sie sortieren und suchen können, um den für Sie richtigen Datenfeed zu finden. Die Liste der [!UICONTROL Marketplace] Käufer enthält unter anderem:

* **[!UICONTROL Search]** : Suchen Sie nach Datenfeeds anhand des Namens oder der Textbeschreibung.
* **[!UICONTROL Name]** : Name des Datenfeeds.
* **[!UICONTROL Description]** : Informationen zum Inhalt eines Datenfeeds.
* **[!UICONTROL Provider]** : Name des Datenanbieters.
* **[!UICONTROL Traits]** : Die Anzahl der Eigenschaften in einem Datenfeed.
* **[!UICONTROL 30 Day Provider Unique Users]** : Die Anzahl der Unique Users, die in den letzten 30 Tagen gesehen wurden.
* **[!UICONTROL 30 Day Overlapped Uniques]** : Die Anzahl der Benutzer in Ihrem Konto, die sich mit den Benutzern im Konto des Anbieters überschneiden.
* **[!UICONTROL Feed Overlap]** : Der 30-Tage-Überschneidungswert für individuelle Werte, in Prozent angezeigt, berechnet als: Data Buffer 30 day überlappte Uniques / Data Buffer 30 day Uniques) x 100.
* **[!UICONTROL Private Feeds]** : Siehe [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]** : Die Anzahl der Abonnements, die Sie bei einem Datenanbieter haben.

## Private Daten-Feeds {#private-data-feeds}

In der [!UICONTROL Marketplace] Liste werden manchmal der Name und die Eigenschaften des Anbieters als privat gekennzeichnet. Dies zeigt einen [privaten Datenfeed](../../../features/audience-marketplace/marketplace-private-feeds.md)an. Mit einem privaten Datenfeed können Verkäufer den Zugriff auf ihre Daten einschränken. Verkäufer können Feeds privat gestalten, wenn sie spezielle Angebote, Rabatte oder Zugriffskontrollen anbieten. Als Käufer müssen Sie eine Abonnementanforderung an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed haben möchten. Weitere Informationen finden Sie unter [Abonnieren eines privaten Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) .

>[!MORE_LIKE_THIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)


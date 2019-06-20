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


# Audience Marketplace für Datenkäufer {#audience-marketplace-for-data-buyers}

Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern innerhalb von [!DNL Audience Manager]ihnen kaufen möchten.

>[!NOTE]
>[Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf [!UICONTROL Audience Marketplace] Funktionen.
>
>* Administratoren können Datenfeeds erstellen, Abonnenten verwalten und Datenfeeds abonnieren.
>* Benutzer können Feeds nur suchen und anzeigen.


## Der Marketplace: Info {#about-marketplace}

<!-- c_marketplace_about.xml -->

Das [!UICONTROL Marketplace] ist eine [!DNL Audience Manager] Funktion für Datenkäufer, die Datenfeeds auflisten, die Sie abonnieren können. Er listet eine einfache Rate oder [!DNL CPM]private Datenfeeds auf. Diese Feeds werden von Anbietern von Drittanbietern bereitgestellt, die [!DNL Audience Manager] die Daten verkaufen. In [!UICONTROL Marketplace]den Berichtstools können Sie die Feed-Nutzung und die Überlappung zwischen Ihren Eigenschaften und denen in einem abonnierten Datenfeed nachverfolgen. Schließlich [!UICONTROL Audience Marketplace][!DNL Adobe] werden Rechnungen und Zahlungsgebühren berücksichtigt (obwohl Sie die Nutzung selbst bei Abonnement in einem [!DNL CPM] Feed selbst erfassen müssen). Mit diesen Funktionen können Sie effektive Datenquellen suchen, ohne die Suche nach einem Datenanbieter zu verlieren.

>[!TIP]
> 
>Verwenden Sie die **[Adobe Audience Finder,](https://www.adobe-audience-finder.com/)** um hochwertige Datenfeeds zu finden, die Sie abonnieren können. Wechseln Sie dann zurück zur Benutzeroberfläche des Audience Manager oder verwenden Sie die [Audience Marketplace Käufer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) , um die Feeds zu abonnieren.

![](assets/buyer_marketplace.png)

Die [!UICONTROL Marketplace] Liste enthält Informationen, die Sie sortieren und suchen können, um den richtigen Datenfeed zu finden. Zu den Elementen in der Liste [!UICONTROL Marketplace] des Käufers gehören:

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

In der [!UICONTROL Marketplace] Liste werden der Name des Anbieters und seine Daten manchmal als privat markiert. Dies deutet auf einen [privaten Datenfeed](../../../features/audience-marketplace/marketplace-private-feeds.md)hin. Ein privater Datenfeed ermöglicht den Käufern den Zugriff auf ihre Daten einzuschränken. Verkäufer können Feeds privat schalten, wenn sie spezielle Angebote, Rabatte oder Zugriffsrechte und Zugriffssteuerungsmöglichkeiten anbieten. Als Käufer müssen Sie eine Abonnementanfrage an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed benötigen. Weitere Informationen finden Sie unter [Abonnieren eines privaten Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) .

>[!MORE_ LIKE_ THIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)


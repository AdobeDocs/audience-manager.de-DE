---
description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern innerhalb des Audience Managers erwerben möchten
seo-description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern innerhalb des Audience Managers erwerben möchten
seo-title: Audience Marketplace für Datenkäufer
solution: Audience Manager
title: Audience Marketplace für Datenkäufer
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 3%

---


# [!UICONTROL Audience Marketplace] für Datenkäufer  {#audience-marketplace-for-data-buyers}

Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern innerhalb von [!DNL Audience Manager] erwerben möchten.

>[!NOTE]
>[Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf [!UICONTROL Audience Marketplace] Funktionen.
>
>* Administratoren können Datenfeeds erstellen, Abonnenten verwalten und Datenfeeds abonnieren.
>* Benutzer können nur Feeds suchen und Ansichten bereitstellen.


## Die [!UICONTROL Marketplace]: Über {#about-marketplace}

[!UICONTROL Marketplace] ist eine [!DNL Audience Manager]-Funktion für Datenkäufer, mit der Datenfeeds Liste werden, die Sie abonnieren können. Es werden pauschale, [!DNL CPM] und private Datenfeeds Liste. Diese Feeds werden von Drittanbietern bereitgestellt, die [!DNL Audience Manager] verwenden, um Daten zu verkaufen.

Mit den [!UICONTROL Marketplace]-Berichte-Tools können Sie die Feed-Nutzung und die Überschneidung zwischen [!UICONTROL traits] und denen in einem abonnierten Data Feed verfolgen. Mit [!UICONTROL Audience Marketplace] kümmert sich [!DNL Adobe] um Rechnungen und Gebührenzahlungen (obwohl Sie die Nutzung selbst melden müssen, wenn Sie einen [!DNL CPM]-Feed abonniert haben). Mit diesen Funktionen können Sie effektive Datenquellen finden, ohne Zeit mit der Suche nach einem Datenanbieter zu verschwenden.

>[!TIP]
>
>Verwenden Sie den **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**, um qualitativ hochwertige Datenfeeds zu finden, die Sie abonnieren können. Gehen Sie dann zurück zur [!DNL Audience Manager]-Benutzeroberfläche oder verwenden Sie die [Audience Marketplace-Käufer-API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API), um die von Ihnen gefundenen Feeds zu abonnieren.

![Käufermarktplatz-overview](assets/buyer-marketplace-overview.png)

Die [!UICONTROL Marketplace]-Liste enthält Informationen, die Sie sortieren und suchen können, um den für Sie richtigen Datenfeed zu finden. Zu den Elementen in der Liste [!UICONTROL Marketplace] des Käufers gehören:

* **[!UICONTROL Search]**: Suchen Sie nach Datenfeeds anhand des Namens oder der Textbeschreibung.
* **[!UICONTROL Similar Traits]**: Zeigt die Anzahl der Ähnlichkeiten  [!UICONTROL traits] aus einem Datenfeed an. Diese Spalte wird angezeigt, nachdem Sie ein [!UICONTROL trait] oder [!UICONTROL segment] eingegeben haben, um nach dem **[!UICONTROL Similarity To]**-Abschnitt zu filtern.
* **[!UICONTROL Name]**: Name des Datenfeeds.
* **[!UICONTROL Description]**: Informationen zum Inhalt eines Datenfeeds.
* **[!UICONTROL Provider]**: Name des Datenanbieters.
* **[!UICONTROL Traits]**: Die Anzahl der Daten  [!UICONTROL traits] in einem Datenfeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Die Anzahl der Unique Users, die in den letzten 30 Tagen gesehen wurden.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Die Anzahl der Benutzer in Ihrem Konto, die sich mit den Benutzern im Konto des Anbieters überschneiden.
* **[!UICONTROL Feed Overlap]**: Der 30-Tage-Überschneidungswert für individuelle Werte, in Prozent angezeigt, berechnet als: Data Buffer 30 day überlappte Uniques / Data Buffer 30 day Uniques) x 100.
* **[!UICONTROL Private Feeds]**: Siehe  [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Die Anzahl der Abonnement, die Sie mit einem Datenanbieter haben.

 

Verwenden Sie die folgenden Filter links auf der Seite [!UICONTROL Marketplace], um die besten Datenfeeds für Ihre Anforderungen leicht zu finden:

* **[!UICONTROL Similarity To]**: Filtern Sie Datenfeeds auf Grundlage ihrer Ähnlichkeit mit einem  [!UICONTROL trait] oder  [!UICONTROL segment] Ihrer Wahl. Beim Eingeben der [!UICONTROL trait]- oder des Segments, mit dem Sie vergleichen möchten, können Sie die [!UICONTROL trait]- oder [!UICONTROL segment]-ID oder deren entsprechende Namen verwenden.
* **[!UICONTROL Similarity Cutoff]**: Ziehen Sie den Schieberegler, um die Datenfeeds nach der Ähnlichkeit der Feeds mit  [!UICONTROL traits] den ausgewählten  [!UICONTROL trait] oder  [!UICONTROL segment]ausgewählten zu filtern. Weitere Informationen zu [!UICONTROL trait]-Ähnlichkeitswerten finden Sie unter [Bewertung der Ähnlichkeit von Eigenschaften](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtern Sie die Datenfeeds nach Ihrem Abonnement-Status.
* **[!UICONTROL Plan Use Case]**: Filtern Sie Datenfeeds nach unterstützten Anwendungsfällen:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** und  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtern Sie Datenfeeds nach ihrem Preistyp.

## Ähnliche [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] gibt Ihnen die Möglichkeit,  [!UICONTROL traits] aus verschiedenen Datenfeeds zu suchen, basierend auf deren Ähnlichkeit mit Ihren vorhandenen  [!UICONTROL traits] oder Segmenten. So geht das:

1. Gehen Sie zu **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Verwenden Sie den Selektor **[!UICONTROL Similarity To]**, um zwischen Filtern zu wählen, die auf einem [!UICONTROL trait] oder [!UICONTROL segment] basieren. Sie können nach [!UICONTROL trait]/[!UICONTROL segment]-ID oder -Name filtern. Das Suchfeld zeigt Ihnen anhand Ihrer Eingabe automatisch relevante Vorschläge an.
3. Nachdem Sie die Eigenschaft oder das Segment identifiziert haben, nach der Sie filtern möchten, klicken Sie in der Liste Vorschläge darauf.
4. Um die Ergebnisse einzugrenzen, verwenden Sie den Schieberegler **[!UICONTROL Similarity Cutoff]**, um von weniger ähnlichen [!UICONTROL traits] zu ähnlichen zu wechseln.

Nach Abschluss der Filterung wird eine neue Spalte auf der Ergebnisseite angezeigt: **[!UICONTROL Similar Traits]**. Diese Spalte zeigt Ihnen die Anzahl der Ähnlichkeiten zwischen [!UICONTROL traits] und der von Ihnen gefilterten Anzahl aus jedem Datenfeed, der die Filterkriterien erfüllt.

Um die vollständige Liste ähnlicher Eigenschaften anzuzeigen, klicken Sie auf die Zahl in der Spalte **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> In Audience Marketplace werden die 500 beliebtesten ähnlichen [!UICONTROL trait]-Ergebnisse aus allen Datenfeeds angezeigt.

Sehen Sie sich das unten stehende Video an, um einen vollständigen Überblick darüber zu erhalten, wie ähnliche [!UICONTROL traits] gefunden werden können.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Private Daten-Feeds {#private-data-feeds}

In der Liste [!UICONTROL Marketplace] werden manchmal der Name des Anbieters und [!UICONTROL trait]-Daten als privat gekennzeichnet. Dies bedeutet einen [privaten Datenfeed](../../../features/audience-marketplace/marketplace-private-feeds.md). Mit einem privaten Datenfeed können Verkäufer den Zugriff auf ihre Daten einschränken. Verkäufer können Feeds privat gestalten, wenn sie spezielle Angebote, Rabatte oder wenn Privatsphäre und Zugriffskontrolle für sie wichtig sind. Als Käufer müssen Sie eine Abonnement-Anfrage an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed wünschen. Weitere Informationen finden Sie unter [Einen privaten Datenfeed abonnieren](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

>[!MORELIKETHIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)


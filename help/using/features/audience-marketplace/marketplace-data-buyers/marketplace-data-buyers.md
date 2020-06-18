---
description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern innerhalb des Audience Managers erwerben möchten
seo-description: Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern innerhalb des Audience Managers erwerben möchten
seo-title: Audience Marketplace für Datenkäufer
solution: Audience Manager
title: Audience Marketplace für Datenkäufer
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---


# Audience Marketplace für Datenkäufer {#audience-marketplace-for-data-buyers}

Übersicht und Arbeitsablauf für Datenkäufer, die Daten von Drittanbietern von innerhalb [!DNL Audience Manager]der Website erwerben möchten.

>[!NOTE]
>[Rollenbasierte Berechtigungen](../../../reporting/reports-dashboard.md) steuern den Zugriff auf [!UICONTROL Audience Marketplace] Funktionen.
>
>* Administratoren können Datenfeeds erstellen, Abonnenten verwalten und Datenfeeds abonnieren.
>* Benutzer können nur Feeds suchen und Ansichten bereitstellen.


## Der Marktplatz: Info {#about-marketplace}

<!-- c_marketplace_about.xml -->

Das [!UICONTROL Marketplace] ist eine [!DNL Audience Manager] Funktion für Datenkäufer, mit der Listen von Datenfeeds erstellt werden, die Sie abonnieren können. Es werden pauschale [!DNL CPM]und private Datenfeeds Liste. Diese Feeds werden von Drittanbietern bereitgestellt, die Daten [!DNL Audience Manager] zum Verkauf verwenden.

Mit den [!UICONTROL Marketplace]Berichte-Tools können Sie die Feed-Nutzung und die Überschneidung zwischen Ihren Eigenschaften und denen in einem abonnierten Data Feed verfolgen. Schließlich, mit [!UICONTROL Audience Marketplace]der [!DNL Adobe] kümmert sich um Rechnungen und Gebührenzahlungen (obwohl Sie die Nutzung selbst melden müssen, wenn Sie ein Feed abonniert [!DNL CPM] ). Mit diesen Funktionen können Sie effektive Datenquellen finden, ohne Zeit mit der Suche nach einem Datenanbieter zu verschwenden.

>[!TIP]
>
>Verwenden Sie den **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**, um qualitativ hochwertige Datenfeeds zu finden, die Sie abonnieren können. Gehen Sie dann zurück zur[!DNL Audience Manager]Benutzeroberfläche oder verwenden Sie die[Audience Marketplace-Käufer-API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API), um die von Ihnen gefundenen Feeds zu abonnieren.

![Käufermarktplatz-overview](assets/buyer-marketplace-overview.png)

Die [!UICONTROL Marketplace] Liste enthält Informationen, die Sie sortieren und suchen können, um den für Sie richtigen Datenfeed zu finden. Die Liste des [!UICONTROL Marketplace] Käufers umfasst:

* **[!UICONTROL Search]**: Suchen Sie nach Datenfeeds anhand des Namens oder der Textbeschreibung.
* **[!UICONTROL Similar Traits]**: Zeigt die Anzahl ähnlicher Eigenschaften aus einem Datenfeed an. Diese Spalte wird angezeigt, nachdem Sie eine Eigenschaft oder ein Segment eingegeben haben, nach der im **[!UICONTROL Similarity To]** Abschnitt gefiltert werden soll.
* **[!UICONTROL Name]**: Name des Datenfeeds.
* **[!UICONTROL Description]**: Informationen zum Inhalt eines Datenfeeds.
* **[!UICONTROL Provider]**: Name des Datenanbieters.
* **[!UICONTROL Traits]**: Die Anzahl der Eigenschaften in einem Datenfeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Die Anzahl der Unique Users, die in den letzten 30 Tagen gesehen wurden.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Die Anzahl der Benutzer in Ihrem Konto, die sich mit den Benutzern im Konto des Anbieters überschneiden.
* **[!UICONTROL Feed Overlap]**: Der 30-Tage-Überschneidungswert für individuelle Werte, in Prozent angezeigt, berechnet als: Data Buffer 30 day überlappte Uniques / Data Buffer 30 day Uniques) x 100.
* **[!UICONTROL Private Feeds]**: Siehe [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Die Anzahl der Abonnement, die Sie mit einem Datenanbieter haben.

 

Verwenden Sie die folgenden Filter links auf der [!UICONTROL Marketplace] Seite, um die besten Datenfeeds für Ihre Anforderungen leicht zu finden:

* **[!UICONTROL Similarity To]**: Filtern Sie Datenfeeds basierend auf ihrer Ähnlichkeit mit einer Eigenschaft oder einem Segment Ihrer Wahl. Beim Eingeben der Eigenschaft oder des Segments, mit der bzw. dem Sie vergleichen möchten, können Sie die Eigenschaften- oder Segment-ID oder deren jeweilige Namen verwenden.
* **[!UICONTROL Similarity Cutoff]**: Ziehen Sie den Schieberegler, um die Datenfeeds nach der Ähnlichkeit ihrer Eigenschaften mit der ausgewählten Eigenschaft oder dem ausgewählten Segment zu filtern. Weitere Informationen zu den Ergebnissen von [Eigenschaften-Ähnlichkeitswerten finden Sie unter Bewertung der Eigenschafts-Ähnlichkeit](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtern Sie die Datenfeeds nach Ihrem Abonnement-Status.
* **[!UICONTROL Plan Use Case]**: Filtern Sie Datenfeeds nach unterstützten Anwendungsfällen: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** und **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtern Sie Datenfeeds nach ihrem Preistyp.

## Suchen ähnlicher Eigenschaften {#finding-similar-traits}

[!UICONTROL Audience Marketplace] gibt Ihnen die Möglichkeit, Eigenschaften aus verschiedenen Data Feeds zu suchen, die auf der Ähnlichkeit mit Ihren vorhandenen Eigenschaften oder Segmenten basieren. So geht das:

1. Gehen Sie zu **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Verwenden Sie den **[!UICONTROL Similarity To]** Selektor, um zwischen der Filterung auf Grundlage einer Eigenschaft oder eines Segments zu wählen. Sie können nach Eigenschaften-/Segment-ID oder Namen filtern. Das Suchfeld zeigt Ihnen anhand Ihrer Eingabe automatisch relevante Vorschläge an.
3. Nachdem Sie die Eigenschaft oder das Segment identifiziert haben, nach der Sie filtern möchten, klicken Sie in der Liste Vorschläge darauf.
4. Um die Ergebnisse einzugrenzen, verwenden Sie den **[!UICONTROL Similarity Cutoff]** Schieberegler, um von weniger ähnlichen Eigenschaften zu ähnlichen Eigenschaften zu wechseln.

Nach Abschluss der Filterung wird eine neue Spalte auf der Ergebnisseite angezeigt: **[!UICONTROL Similar Traits]**. Diese Spalte zeigt Ihnen die Anzahl ähnlicher Eigenschaften, nach denen Sie gefiltert sind, aus jedem Datenfeed, der die Filterkriterien erfüllt.

Um die vollständige Liste ähnlicher Eigenschaften anzuzeigen, klicken Sie auf die Zahl in der **[!UICONTROL Similar Traits]** Spalte.

>[!NOTE]
>
> Audience Marketplace zeigt die 500 beliebtesten ähnlichen Eigenschaften an, die aus allen Datenfeeds resultieren.

Sehen Sie sich das unten stehende Video an, um einen vollständigen Überblick darüber zu erhalten, wie ähnliche Eigenschaften gefunden werden können.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Private Daten-Feeds {#private-data-feeds}

In der [!UICONTROL Marketplace] Liste werden die Angaben zum Namen und zur Eigenschaft des Anbieters manchmal als &quot;privat&quot;gekennzeichnet. Dies zeigt einen [privaten Datenfeed](../../../features/audience-marketplace/marketplace-private-feeds.md)an. Mit einem privaten Datenfeed können Verkäufer den Zugriff auf ihre Daten einschränken. Verkäufer können Feeds privat gestalten, wenn sie spezielle Angebote, Rabatte oder wenn Privatsphäre und Zugriffskontrolle für sie wichtig sind. Als Käufer müssen Sie eine Abonnement-Anfrage an den Verkäufer senden, wenn Sie Zugriff auf einen privaten Feed wünschen. Weitere Informationen finden Sie unter [Abonnieren eines privaten Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) .

>[!MORELIKETHIS]
>
>* [Grundlegendes zur Abo-Detailseite im Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatte für Datenkäufer](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)


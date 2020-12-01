---
description: Erstellen Sie neue Eigenschaften aus allen Signalen, einschließlich derjenigen, die bereits in Eigenschaften verwendet werden, und erfassen Sie zukünftige Audiencen, die sich nach der Erstellung von Eigenschaften qualifizieren.
seo-description: Erstellen Sie neue Eigenschaften aus allen Signalen, einschließlich derjenigen, die bereits in Eigenschaften verwendet werden, und erfassen Sie zukünftige Audiencen, die sich nach der Erstellung von Eigenschaften qualifizieren.
seo-title: Erstellen von Eigenschaften aus Signalen
title: Erstellen von Eigenschaften aus Signalen
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 3%

---


# Erstellen von Eigenschaften aus Signalen

Erstellen Sie neue Eigenschaften aus allen Signalen, einschließlich derjenigen, die bereits in Eigenschaften verwendet werden, und erfassen Sie zukünftige Audiencen, die sich nach der Erstellung von Eigenschaften qualifizieren. Sehen Sie sich das Video für eine kurze Demonstration an oder lesen Sie es für detaillierte Informationen:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Eigenschaften aus Signal-Dashboard {#create-traits-from-signal-dashboard} erstellen

Mit dem [!UICONTROL Signal Dashboard] können Sie neue Eigenschaften aus den [!UICONTROL Top Unused Signals]-, [!UICONTROL New Unused Signals]- und Ihren gespeicherten Suchvorgängen erstellen.

Wenn Sie eine neue Eigenschaft erstellen, wird der Eigenschaftstyp basierend auf dem Signaltyp vorgegeben:

* **[!UICONTROL Rule-based]** Eigenschaften für Echtzeitsignale, umsetzbare Protokolldateien und  [!DNL Adobe Analytics] Signale;

* **[!UICONTROL Onboarded]** Eigenschaften für Bordsignale.

Um neue Eigenschaften von **[!UICONTROL Signal Dashboard]** zu erstellen, müssen Sie das Signal, das Sie in der Eigenschaft verwenden möchten, identifizieren und dann auf den entsprechenden Link **[!UICONTROL Create Rule-Based Trait]** oder **[!UICONTROL Create Onboarded Trait]** klicken.

![](assets/signals-create-trait.png)

Sie werden zum **[Eigenschaften-Aufbau](../../features/traits/about-trait-builder.md)** umgeleitet, um Ihre neuen Eigenschaften zu erstellen.

## Eigenschaften aus der Signalsuche erstellen {#create-traits-from-signal-search}

Erstellen Sie Eigenschaften basierend auf verwendeten oder nicht verwendeten Signalen, die nicht in [!UICONTROL Signal Dashboard] angezeigt werden.

Suchen Sie nach bestimmten Signalen und erstellen Sie auf Basis der Ergebnisse regelbasierte oder Onboard-Eigenschaften. So geht das:

1. Gehen Sie zu **[!UICONTROL Audience Data > Signals > Search]** und führen Sie eine Suche auf Grundlage der Schlüssel-Wert-Paare durch, nach denen Sie suchen, oder klicken Sie auf **[!UICONTROL Search]**, ohne ein Schlüssel-Wert-Paar einzugeben, um alle Ergebnisse anzuzeigen.
2. Identifizieren Sie die Signale, die Sie in der Liste der Ergebnisse in der Eigenschaft verwenden möchten.
   * Um eine Eigenschaft aus einem Signal zu erstellen, klicken Sie auf den entsprechenden Link **[!UICONTROL Create Rule-Based Trait]** oder **[!UICONTROL Create Onboarded Trait]**.
   * Um eine Eigenschaft aus mehreren Signalen zu erstellen, klicken Sie auf das entsprechende Kontrollkästchen der einzelnen Signale und dann auf **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Sie können Eigenschaften nur aus Signalen desselben Typs erstellen. Sie können keine Eigenschaften erstellen, die auf einer Kombination aus einem Echtzeit-Signal und einem Onboard-Signal basieren.
   >
   > ![](assets/signals-create-trait-search.png)
   >Sie können Eigenschaften auch aus den verwendeten Signalen erstellen. Signale, die bereits in Eigenschaften verwendet werden, weisen die Anzahl der Eigenschaften in der Spalte **[!UICONTROL Included in Traits]** auf. Klicken Sie auf den Pfeil, um die Eigenschaften anzuzeigen, die das Signal enthalten.
   >
   >![](assets/signals-used-traits.png)

3. Verwenden Sie den **[Eigenschaften-Aufbau](../../features/traits/about-trait-builder.md)**, um Ihre neuen Eigenschaften zu erstellen.

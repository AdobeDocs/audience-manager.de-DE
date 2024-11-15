---
description: Erstellen Sie neue Eigenschaften aus allen Signalen, einschließlich derjenigen, die bereits in Eigenschaften verwendet werden, und erfassen Sie zukünftige Zielgruppen, die sich nach der Erstellung von Eigenschaften qualifizieren.
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: Erstellen von Eigenschaften aus Signalen
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Erstellen von Eigenschaften aus Signalen

Erstellen Sie neue Eigenschaften aus allen Signalen, einschließlich derjenigen, die bereits in Eigenschaften verwendet werden, und erfassen Sie zukünftige Zielgruppen, die sich nach der Erstellung von Eigenschaften qualifizieren. Sehen Sie sich das Video für eine kurze Demonstration an oder lesen Sie für detaillierte Informationen:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Erstellen von Eigenschaften über das Signal-Dashboard {#create-traits-from-signal-dashboard}

Mit dem [!UICONTROL Signal Dashboard] können Sie neue Eigenschaften aus den [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] und Ihren gespeicherten Suchvorgängen erstellen.

Wenn Sie eine neue Eigenschaft erstellen, ist der Eigenschaftstyp basierend auf dem Signaltyp vordefiniert:

* **[!UICONTROL Rule-based]** Eigenschaften für Echtzeitsignale, ausführbare Protokolldateien und [!DNL Adobe Analytics] Signale;

* **[!UICONTROL Onboarded]** Eigenschaften für integrierte Signale.

Um neue Eigenschaften aus dem **[!UICONTROL Signal Dashboard]** zu erstellen, identifizieren Sie das Signal, das Sie in der Eigenschaft verwenden möchten, und klicken Sie dann auf den entsprechenden **[!UICONTROL Create Rule-Based Trait]** - oder **[!UICONTROL Create Onboarded Trait]** -Link.

![](assets/signals-create-trait.png)

Sie werden zum **[Trait Builder](../../features/traits/about-trait-builder.md)** umgeleitet, um Ihre neuen Eigenschaften zu erstellen.

## Erstellen von Eigenschaften aus der Signalsuche {#create-traits-from-signal-search}

Erstellen Sie Eigenschaften basierend auf verwendeten oder nicht verwendeten Signalen, die nicht in der [!UICONTROL Signal Dashboard] angezeigt werden.

Suchen Sie nach bestimmten Signalen und erstellen Sie regelbasierte oder integrierte Eigenschaften basierend auf den Ergebnissen. Gehen Sie dazu folgendermaßen vor:

1. Wechseln Sie zu &quot;**[!UICONTROL Audience Data > Signals > Search]**&quot;, führen Sie eine Suche basierend auf den von Ihnen gesuchten Schlüssel-Wert-Paaren durch oder klicken Sie auf &quot;**[!UICONTROL Search]**&quot;, ohne ein Schlüssel-Wert-Paar einzugeben, um alle Ergebnisse anzuzeigen.
2. Identifizieren Sie in der Ergebnisliste die Signale, die Sie in der Eigenschaft verwenden möchten.
   * Um eine Eigenschaft aus einem Signal zu erstellen, klicken Sie auf den entsprechenden Link **[!UICONTROL Create Rule-Based Trait]** oder **[!UICONTROL Create Onboarded Trait]** .
   * Um eine Eigenschaft aus mehreren Signalen zu erstellen, klicken Sie auf das entsprechende Kontrollkästchen jedes Signals und dann auf **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Sie können Eigenschaften nur aus Signalen desselben Typs erstellen. Sie können eine Eigenschaft nicht basierend auf einer Kombination aus einem Echtzeit-Signal und einem integrierten Signal erstellen.
   >
   > ![](assets/signals-create-trait-search.png)
   >Sie können Eigenschaften auch aus verwendeten Signalen erstellen. Signale, die bereits in Eigenschaften verwendet werden, weisen die Anzahl der Eigenschaften auf, die in der Spalte **[!UICONTROL Included in Traits]** angezeigt werden. Klicken Sie auf den Pfeil, um die Eigenschaften anzuzeigen, die das Signal enthalten.
   >
   >![](assets/signals-used-traits.png)

3. Verwenden Sie den **[Trait Builder](../../features/traits/about-trait-builder.md)** , um Ihre neuen Eigenschaften zu erstellen.

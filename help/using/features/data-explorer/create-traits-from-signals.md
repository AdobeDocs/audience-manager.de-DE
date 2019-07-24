---
description: Erstellen Sie neue Eigenschaften aus allen Signalen, einschließlich derjenigen, die bereits in Eigenschaften verwendet werden, und erfassen Sie zukünftige Zielgruppen, die sich nach der Erstellung von Eigenschaften qualifizieren.
seo-description: Erstellen Sie neue Eigenschaften aus allen Signalen, einschließlich derjenigen, die bereits in Eigenschaften verwendet werden, und erfassen Sie zukünftige Zielgruppen, die sich nach der Erstellung von Eigenschaften qualifizieren.
seo-title: Eigenschaften aus Signalsignalen erstellen
title: Eigenschaften aus Signalsignalen erstellen
uuid: 4 f 324404-0 c 24-4 e 3 b -96 c 1-7 c 1 b 28 a 4536 d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Eigenschaften aus Signalsignalen erstellen

Erstellen Sie neue Eigenschaften aus allen Signalen, einschließlich derjenigen, die bereits in Eigenschaften verwendet werden, und erfassen Sie zukünftige Zielgruppen, die sich nach der Erstellung von Eigenschaften qualifizieren. Sehen Sie sich das Video für eine schnelle Demonstration an oder lesen Sie es, um detaillierte Informationen zu erhalten:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=ger)

## Create Traits from Signal Dashboard {#create-traits-from-signal-dashboard}

The [!UICONTROL Signal Dashboard] allows you to create new traits from the [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals], and your saved searches.

Wenn Sie eine neue Eigenschaft erstellen, wird der Eigenschaftstyp basierend auf dem Signaltyp voreingestellt:

* **[!UICONTROL Rule-based]** Eigenschaften für Echtzeitsignale, ausführbare Protokolldateien und [!DNL Adobe Analytics] Signale;

* **[!UICONTROL Onboarded]** Eigenschaften für onboarded-Signale.

To create new traits from the **[!UICONTROL Signal Dashboard]**, identify the signal that you want to use in the trait, then click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.

![](assets/signals-create-trait.png)

You'll be redirected to the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new trait(s).

## Create Traits from Signal Search {#create-traits-from-signal-search}

Create traits based on used or unused signals that are not shown in the [!UICONTROL Signal Dashboard].

Suchen Sie nach bestimmten Signalen und erstellen Sie regelbasierte oder onboardierte Eigenschaften basierend auf den Ergebnissen. Gehen Sie wie folgt vor:

1. Go to **[!UICONTROL Audience Data > Signals > Search]** and run a search based on the key-value pairs that you are looking for, or click **[!UICONTROL Search]** without entering any key-value pair to display all results.
2. Identifizieren Sie die Signale, die Sie in der Eigenschaft verwenden möchten, in der Ergebnisliste.
   * To create a trait from one signal, click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.
   * To create a trait from multiple signals, click the corresponding check box of each signal, then click **[!UICONTROL Create Trait from Multiple Signals]**.
   >[!NOTE]
   >Sie können Eigenschaften nur aus Signale desselben Typs erstellen. Sie können keine Eigenschaften basierend auf einer Kombination aus Echtzeit-Signal und Onboardansicht erstellen.
   >
   > ![](assets/signals-create-trait-search.png)
   >Sie können auch Eigenschaften aus verwendeten Signalen erstellen. Signals that are already used in traits have the number of traits displayed in the **[!UICONTROL Included in Traits]** column. Klicken Sie auf den Pfeil, um die Eigenschaften anzuzeigen, die das Signal enthalten.
   >
   >![](assets/signals-used-traits.png)

3. Use the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new traits.

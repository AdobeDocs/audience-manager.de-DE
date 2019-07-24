---
description: Ein abgeleitetes Signal qualifiziert Site-Besucher auf zusätzliche Eigenschaften basierend auf einer bereits gesehenen Eigenschaft. Mit anderen Worten, zusätzliche Eigenschaften für Eigenschaften können von einer zur Zeit ausgefüllten Eigenschaft abgeleitet werden, auch wenn ein Benutzer die neue Eigenschaft zuvor noch nie gesehen hat.
seo-description: Ein abgeleitetes Signal qualifiziert Site-Besucher auf zusätzliche Eigenschaften basierend auf einer bereits gesehenen Eigenschaft. Mit anderen Worten, zusätzliche Eigenschaften für Eigenschaften können von einer zur Zeit ausgefüllten Eigenschaft abgeleitet werden, auch wenn ein Benutzer die neue Eigenschaft zuvor noch nie gesehen hat.
seo-title: Abgeleitete Signale
solution: Audience Manager
title: Abgeleitete Signale
uuid: e 52600 e 3-26 d 1-4607-9 b 96-afd 6086 a 252 d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Derived Signals {#derived-signals}

A [!UICONTROL derived signal] qualifies site visitors for additional traits based on a trait they've already seen. Mit anderen Worten, zusätzliche Eigenschaften für Eigenschaften können von einer zur Zeit ausgefüllten Eigenschaft abgeleitet werden, auch wenn ein Benutzer die neue Eigenschaft zuvor noch nie gesehen hat.

<!-- c_tb_derived_signal.xml -->

## Zweck von abgeleiteten Signalen

In [!DNL Audience Manager], you can create a relationship between signals (or trait rules) passed in during an event call to other, specified signals or traits. For example, assume an event call passes in a signal composed of the key-value [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] das Signal mit anderen, mit dem [!UICONTROL derived signals] Tool erstellten Benutzern verbinden. Although the associated signals can be any key-values you specify, they are most useful when linked to existing signals already set up as [!UICONTROL Trait Builder] rules. For example, in the illustration below, when a user action fires the signal [!DNL "product = new car"] that user can also qualify for traits defined by the target key and value signals.

![](assets/derived_signal_example.png)

## Position der abgeleiteten Signale

Create and manage [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** from the sidebar navigation.

## Create a Derived Signal {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. Select **[!UICONTROL Derived Signals]** from the [!UICONTROL Tools] menu.
1. Geben Sie einen:
   * *(Optional)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klicken Sie auf **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>The character limit for the [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key], and [!UICONTROL Target Value] fields is 228 characters.

## Edit a Derived Signal {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. Hover over the signal, then click **[!UICONTROL Edit]**.
2. Make the required code, key, or value changes, then click **[!UICONTROL Save]**.

## Delete a Derived Signal {#delete}

<!-- t_tb_delete_derived.xml -->

To delete a [!UICONTROL derived signal], hover over the signal, then click **[!UICONTROL Delete]**.

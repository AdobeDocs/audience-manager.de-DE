---
description: Ein abgeleitetes Signal qualifiziert Site-Besucher für zusätzliche Eigenschaften, basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten, eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit dargestellten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie zuvor gesehen hat.
seo-description: Ein abgeleitetes Signal qualifiziert Site-Besucher für zusätzliche Eigenschaften, basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten, eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit dargestellten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie zuvor gesehen hat.
seo-title: Abgeleitete Signale
solution: Audience Manager
title: Abgeleitete Signale
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 2%

---


# Abgeleitete Signale {#derived-signals}

Ein [!UICONTROL derived signal] qualifiziert Site-Besucher für zusätzliche Eigenschaften, basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten, eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit dargestellten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie zuvor gesehen hat.

<!-- c_tb_derived_signal.xml -->

## Zweck abgeleiteter Signale

In [!DNL Audience Manager] können Sie eine Beziehung zwischen Signalen (oder Eigenschaftsregeln) erstellen, die während eines Ereignis-Aufrufs an andere angegebene Signale oder Eigenschaften weitergegeben werden. Nehmen wir beispielsweise an, dass ein Ereignis-Aufruf in einem Signal, das aus dem Schlüssel-Wert [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`) besteht, weitergegeben wird. [!DNL Audience Manager] würde dieses Signal mit allen anderen, die mit dem  [!UICONTROL derived signals] Tool erstellt wurden, verbinden. Die zugehörigen Signale können alle von Ihnen angegebenen Schlüsselwerte sein, sind jedoch am nützlichsten, wenn sie mit vorhandenen Signalen verknüpft werden, die bereits als [!UICONTROL Trait Builder]-Regeln eingerichtet wurden. Beispiel: Wenn eine Benutzeraktion das Signal [!DNL "product = new car"] auslöst, kann dieser Benutzer sich auch für Eigenschaften qualifizieren, die durch die Schlüssel- und Wertsignale der Zielgruppe definiert werden.

![](assets/derived_signal_example.png)

## Ort der abgeleiteten Signale

Erstellen und verwalten Sie [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** aus der Seitenleistennavigation.

## Abgeleitetes Signal {#create} erstellen

<!-- t_tb_create_derived.xml -->

So erstellen Sie ein [!UICONTROL derived signal]:

1. Wählen Sie **[!UICONTROL Derived Signals]** aus dem Menü [!UICONTROL Tools].
1. Geben Sie ein:
   * *(Optional)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klicken **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Die Zeichenbeschränkung für die Felder [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] und [!UICONTROL Target Value] beträgt 228 Zeichen.

## Abgeleitetes Signal bearbeiten {#edit}

<!-- t_tb_edit_derived.xml -->

So bearbeiten Sie ein [!UICONTROL derived signal]:

1. Bewegen Sie den Mauszeiger über das Signal und klicken Sie dann auf **[!UICONTROL Edit]**.
2. Nehmen Sie die erforderlichen Code-, Schlüssel- oder Wertänderungen vor und klicken Sie dann auf **[!UICONTROL Save]**.

## Abgeleitetes Signal {#delete} löschen

<!-- t_tb_delete_derived.xml -->

Um ein [!UICONTROL derived signal] zu löschen, halten Sie den Mauszeiger über das Signal und klicken Sie dann auf **[!UICONTROL Delete]**.

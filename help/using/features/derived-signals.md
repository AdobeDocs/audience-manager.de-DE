---
description: 'Ein abgeleitetes Signal qualifiziert Website-Besuchende für zusätzliche Eigenschaften, die auf einer Eigenschaft basieren, die sie bereits gesehen haben. Mit anderen Worten: Eine zusätzliche Eigenschaftsqualifizierung kann aus einer aktuell angezeigten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie zuvor gesehen hat.'
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: Abgeleitete Signale
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Abgeleitete Signale {#derived-signals}

Eine [!UICONTROL derived signal] qualifiziert Website-Besuchende für zusätzliche Eigenschaften, die auf einer bereits erkannten Eigenschaft basieren. Mit anderen Worten: Eine zusätzliche Eigenschaftsqualifizierung kann aus einer aktuell angezeigten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie zuvor gesehen hat.

<!-- c_tb_derived_signal.xml -->

## Zweck abgeleiteter Signale

In [!DNL Audience Manager] können Sie eine Beziehung zwischen Signalen (oder Eigenschaftsregeln) erstellen, die während eines Ereignisaufrufs an andere, angegebene Signale oder Eigenschaften übergeben werden. Angenommen, ein Ereignisaufruf wird in einem Signal übergeben, das aus dem Schlüssel-Wert-[!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`) besteht. [!DNL Audience Manager] würde dieses Signal mit allen anderen verbinden, die mit dem [!UICONTROL derived signals]-Tool erstellt wurden. Obwohl es sich bei den zugehörigen Signalen um beliebige von Ihnen angegebene Schlüsselwerte handeln kann, sind sie am nützlichsten, wenn sie mit vorhandenen Signalen verknüpft sind, die bereits als [!UICONTROL Trait Builder] festgelegt sind. Wenn beispielsweise in der folgenden Abbildung eine Benutzeraktion das Signal auslöst, kann [!DNL "product = new car"] Benutzer auch für Eigenschaften qualifiziert sein, die durch die Schlüssel- und Wertesignale des Ziels definiert sind.

![](assets/derived_signal_example.png)

## Ort der abgeleiteten Signale

Erstellen und verwalten Sie [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** über die Seitenleisten-Navigation.

## Abgeleitetes Signal erstellen {#create}

<!-- t_tb_create_derived.xml -->

So erstellen Sie eine [!UICONTROL derived signal]:

1. Wählen Sie im Menü **[!UICONTROL Derived Signals]** die Option [!UICONTROL Tools] aus.
1. Geben Sie ein:
   * *(optional)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klicken Sie auf **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Die Zeichenbeschränkung für die Felder [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] und [!UICONTROL Target Value] beträgt 228 Zeichen.

## Abgeleitetes Signal bearbeiten {#edit}

<!-- t_tb_edit_derived.xml -->

So bearbeiten Sie eine [!UICONTROL derived signal]:

1. Bewegen Sie den Mauszeiger über das Signal und klicken Sie dann auf **[!UICONTROL Edit]**.
2. Nehmen Sie die erforderlichen Code-, Schlüssel- oder Wertänderungen vor und klicken Sie dann auf **[!UICONTROL Save]**.

## Abgeleitetes Signal löschen {#delete}

<!-- t_tb_delete_derived.xml -->

Um ein [!UICONTROL derived signal] zu löschen, bewegen Sie den Mauszeiger über das Signal und klicken Sie dann auf **[!UICONTROL Delete]**.

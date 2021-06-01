---
description: 'Ein abgeleitetes Signal qualifiziert Site-Besucher für zusätzliche Eigenschaften basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten: Eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit angezeigten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie gesehen hat.'
seo-description: 'Ein abgeleitetes Signal qualifiziert Site-Besucher für zusätzliche Eigenschaften basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten: Eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit angezeigten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie gesehen hat.'
seo-title: Abgeleitete Signale
solution: Audience Manager
title: Abgeleitete Signale
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: 'Eigenschaften '
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---

# Abgeleitete Signale {#derived-signals}

Ein [!UICONTROL derived signal] qualifiziert Sitebesucher für zusätzliche Eigenschaften basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten: Eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit angezeigten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie gesehen hat.

<!-- c_tb_derived_signal.xml -->

## Zweck der abgeleiteten Signale

In [!DNL Audience Manager] können Sie eine Beziehung zwischen Signalen (oder Eigenschaftsregeln) erstellen, die während eines Ereignisaufrufs an andere angegebene Signale oder Eigenschaften übergeben werden. Angenommen, ein Ereignisaufruf geht an ein Signal über, das aus dem Schlüssel-Wert [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`) besteht. [!DNL Audience Manager] würde dieses Signal mit allen anderen verbinden, die mit dem  [!UICONTROL derived signals] Tool erstellt wurden. Die zugehörigen Signale können zwar alle von Ihnen angegebenen Schlüsselwerte sein, sind jedoch am nützlichsten, wenn sie mit vorhandenen Signalen verknüpft sind, die bereits als [!UICONTROL Trait Builder]-Regeln eingerichtet wurden. Wenn beispielsweise in der folgenden Abbildung eine Benutzeraktion das Signal [!DNL "product = new car"] auslöst, kann der Benutzer auch für Eigenschaften qualifiziert sein, die durch die Schlüssel- und Wertsignale der Zielgruppe definiert sind.

![](assets/derived_signal_example.png)

## Ort abgeleiteter Signale

Erstellen und verwalten Sie [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** in der Seitenleistennavigation.

## Abgeleitetes Signal erstellen {#create}

<!-- t_tb_create_derived.xml -->

So erstellen Sie eine [!UICONTROL derived signal]:

1. Wählen Sie **[!UICONTROL Derived Signals]** aus dem Menü [!UICONTROL Tools] aus.
1. Stellen Sie Folgendes bereit:
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

So bearbeiten Sie eine [!UICONTROL derived signal]:

1. Bewegen Sie den Mauszeiger über das Signal und klicken Sie dann auf **[!UICONTROL Edit]**.
2. Nehmen Sie die erforderlichen Code-, Schlüssel- oder Wertänderungen vor und klicken Sie dann auf **[!UICONTROL Save]**.

## Abgeleitetes Signal löschen {#delete}

<!-- t_tb_delete_derived.xml -->

Um einen [!UICONTROL derived signal] zu löschen, bewegen Sie den Mauszeiger über das Signal und klicken Sie dann auf **[!UICONTROL Delete]**.

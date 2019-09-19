---
description: Ein abgeleitetes Signal qualifiziert Site-Besucher für zusätzliche Eigenschaften, basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten, eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit dargestellten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie zuvor gesehen hat.
seo-description: Ein abgeleitetes Signal qualifiziert Site-Besucher für zusätzliche Eigenschaften, basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten, eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit dargestellten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie zuvor gesehen hat.
seo-title: Abgeleitete Signale
solution: Audience Manager
title: Abgeleitete Signale
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Abgeleitete Signale {#derived-signals}

Ein [!UICONTROL derived signal] qualifiziert Site-Besucher für zusätzliche Eigenschaften, basierend auf einer Eigenschaft, die sie bereits gesehen haben. Mit anderen Worten, eine zusätzliche Eigenschaftsqualifikation kann von einer derzeit dargestellten Eigenschaft abgeleitet werden, selbst wenn ein Benutzer die neue Eigenschaft noch nie zuvor gesehen hat.

<!-- c_tb_derived_signal.xml -->

## Zweck abgeleiteter Signale

In [!DNL Audience Manager]diesem Fall können Sie eine Beziehung zwischen Signalen (oder Eigenschaftsregeln) herstellen, die während eines Ereignisaufrufs an andere, angegebene Signale oder Eigenschaften weitergegeben werden. Nehmen wir beispielsweise an, dass ein Ereignisaufruf in einem Signal, das aus dem Schlüsselwert [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`) besteht, weitergegeben wird. [!DNL Audience Manager] würde dieses Signal mit allen anderen, die mit dem [!UICONTROL derived signals] Tool erstellt wurden, verbinden. Die zugehörigen Signale können alle von Ihnen angegebenen Schlüsselwerte sein, sind jedoch am nützlichsten, wenn sie mit bereits als [!UICONTROL Trait Builder] Regeln eingerichteten Signalen verknüpft werden. Beispiel: Wenn eine Benutzeraktion das Signal auslöst, kann [!DNL "product = new car"] der Benutzer in der unten stehenden Abbildung auch Eigenschaften erkennen, die durch die Zielschlüssel- und -wertsignale definiert wurden.

![](assets/derived_signal_example.png)

## Ort der abgeleiteten Signale

Erstellen und verwalten Sie [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** der Seitenleistennavigation.

## Abgeleitetes Signal erstellen {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. Wählen Sie **[!UICONTROL Derived Signals]** aus dem [!UICONTROL Tools] Menü.
1. Geben Sie ein:
   * *(Optional)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klicken Sie auf **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Die Zeichenbeschränkung für die [!UICONTROL Source Key]-, [!UICONTROL Source Value]-, [!UICONTROL Target Key]- und [!UICONTROL Target Value] -Felder beträgt 228 Zeichen.

## Abgeleitetes Signal bearbeiten {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. Bewegen Sie den Mauszeiger über das Signal und klicken Sie auf **[!UICONTROL Edit]**.
2. Nehmen Sie die erforderlichen Code-, Schlüssel- oder Wertänderungen vor und klicken Sie auf **[!UICONTROL Save]**.

## Abgeleitetes Signal löschen {#delete}

<!-- t_tb_delete_derived.xml -->

Um ein Signal zu löschen, halten Sie den Mauszeiger über das Signal und klicken Sie auf [!UICONTROL derived signal]**[!UICONTROL Delete]**.

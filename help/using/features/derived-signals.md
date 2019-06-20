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


# Abgeleitete Signale {#derived-signals}

A [!UICONTROL derived signal] qualifiziert Site-Besucher für zusätzliche Eigenschaften basierend auf einer bereits gesehenen Eigenschaft. Mit anderen Worten, zusätzliche Eigenschaften für Eigenschaften können von einer zur Zeit ausgefüllten Eigenschaft abgeleitet werden, auch wenn ein Benutzer die neue Eigenschaft zuvor noch nie gesehen hat.

<!-- c_tb_derived_signal.xml -->

## Zweck von abgeleiteten Signalen

In [!DNL Audience Manager]können Sie eine Beziehung zwischen Signalen (oder Trait-Regeln) erstellen, die während eines Ereignisaufrufs an andere, angegebene Signale oder Eigenschaften weitergegeben werden. Angenommen, ein Ereignisaufruf geht von einem Signal aus, das aus dem Schlüsselwert [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`) besteht. [!DNL Audience Manager] das Signal mit anderen, mit dem [!UICONTROL derived signals] Tool erstellten Benutzern verbinden. Obwohl die zugehörigen Signale alle von Ihnen angegebenen Schlüsselwerte sein können, sind sie am nützlichsten, wenn sie mit vorhandenen Signalen verknüpft sind, die bereits als [!UICONTROL Trait Builder] Regeln eingerichtet wurden. Beispiel: Wenn eine Benutzeraktion das Signal [!DNL "product = new car"] auslöst, dass der Benutzer auch für die durch den Zielschlüssel und die Wertsignalen definierten Eigenschaften qualifiziert ist.

![](assets/derived_signal_example.png)

## Position der abgeleiteten Signale

Erstellen und verwalten [!UICONTROL derived signals] Sie in **[!UICONTROL Tools > Derived Signals]** der Seitenleiste.

## Erstellen eines abgeleiteten Signals {#create}

<!-- t_tb_create_derived.xml -->

So erstellen [!UICONTROL derived signal]Sie eine:

1. Wählen **[!UICONTROL Derived Signals]** Sie aus dem [!UICONTROL Tools] Menü.
1. Geben Sie einen:
   * *(Optional)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klicken Sie auf **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>Die Zeichenbeschränkung für den [!UICONTROL Source Key][!UICONTROL Source Value][!UICONTROL Target Key], und [!UICONTROL Target Value] die Felder beträgt 228 Zeichen.

## Abgeleitete Signale bearbeiten {#edit}

<!-- t_tb_edit_derived.xml -->

So bearbeiten Sie eine [!UICONTROL derived signal]:

1. Bewegen Sie den Mauszeiger über das Signal und klicken **[!UICONTROL Edit]** Sie auf.
2. Nehmen Sie den erforderlichen Code, den erforderlichen Schlüssel oder den erforderlichen Wert vor und klicken **[!UICONTROL Save]** Sie dann auf.

## Löschen eines abgeleiteten Signals {#delete}

<!-- t_tb_delete_derived.xml -->

Um einen [!UICONTROL derived signal]Mauszeiger zu löschen, bewegen Sie den Mauszeiger über das Signal und klicken **[!UICONTROL Delete]** Sie dann auf.

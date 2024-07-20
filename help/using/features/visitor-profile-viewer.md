---
description: Verwenden Sie den Visitor Profile Viewer, um den aktuellen Status eines Benutzerprofils für den aktuellen Browser anzuzeigen, einschließlich seiner Eigenschaften und Segmente. Für jede Eigenschaft können Sie ihre SID, ihren Namen, Details zur Implementierung von Besuchereigenschaften (Erst- oder Drittanbieter), das Implementierungsdatum und die Häufigkeit der Realisierungen anzeigen. Sie können für jedes Segment die SID, den Namen und das Mitgliedsdatum des Segments anzeigen. Sie können auch das Besucherprofil für eine andere Audience Manager-Profil-ID (UUID) anzeigen. Der Besucherprofil-Betrachter ist hilfreich bei der Fehlerbehebung.
keywords: location;location-Parameter
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: Besucherprofil-Betrachter
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Besucherprofil-Betrachter {#visitor-profile-viewer}

Verwenden Sie den [!UICONTROL Visitor Profile Viewer] , um den aktuellen Status eines Benutzerprofils für den aktuellen Browser anzuzeigen, einschließlich seiner Eigenschaften und Segmente. Für jede Eigenschaft können Sie ihre [!UICONTROL SID], ihren Namen, Details zur Implementierung von Besuchereigenschaften (Erst- oder Drittanbieter), das Implementierungsdatum und die Häufigkeit der Realisierungen anzeigen. Sie können für jedes Segment dessen [!UICONTROL SID], seinen Namen und das Mitgliedsdatum des Segments anzeigen. Sie können auch das Besucherprofil für eine andere Audience Manager-Profil-ID ([!UICONTROL UUID]) anzeigen. Der [!UICONTROL Visitor Profile Viewer] ist für die Fehlerbehebung hilfreich.

>[!NOTE]
>
>* Für den Zugriff sind [!UICONTROL Administrator] -Berechtigungen erforderlich.
>* Es dauert 24 Stunden, bis Informationen zu realisierten Segmenten und integrierten Eigenschaften in der Benutzeroberfläche angezeigt werden.

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Klicken Sie auf **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *(Optional)* Klicken Sie auf den Eigenschaftsnamen, um diese Eigenschaft im [!UICONTROL Trait Builder] anzuzeigen.

   Weitere Informationen finden Sie unter [Eigenschaften](../features/traits/trait-details-page.md).

1. *(Optional)* Klicken Sie auf den Segmentnamen, um dieses Segment im [!UICONTROL Segment Builder] anzuzeigen.

   Weitere Informationen finden Sie unter [Segmente](../features/segments/segments-purpose.md).

1. *(Bedingt)* Geben Sie im Feld **[!UICONTROL UUID]** eine weitere Audience Manager-Profil-ID an und klicken Sie dann auf **[!UICONTROL Refresh]** , um die Eigenschaften und Segmente für diesen Benutzer anzuzeigen.

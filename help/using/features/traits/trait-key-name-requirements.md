---
description: In diesem Artikel werden die Namenskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Namensanforderungen für Schlüsselvariablen
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
TQID: 'https://experienceleague.adobe.com/OEw-vhgEQtUfiyA4FzKp7rnxeFOZh2nL3r1-YudPAhc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b89b323a-1e91-40b1-8d20-96b5b726d55a
    internal-label: Audience management
subfeature_v2:
  - id: b1ecf375-97f8-4f5a-a937-6129552209be
    internal-label: Traits
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%
---
# Namensanforderungen für Schlüsselvariablen {#name-requirements-for-key-variables}

In diesem Artikel werden die Namenskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.

## Benennungsanforderungen für Schlüssel

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder] kann der Name einer Schlüsselvariablen in einem Schlüssel-Wert-Paar aus einer beliebigen Anzahl von Ziffern bestehen, gefolgt von einem (oder mehreren) Buchstaben, einem Bindestrich, einem Unterstrich und zusätzlichen Ziffern.

* Gültige Schlüsselnamen: `price123`, `123price`, `price-123`, `c_price123`.

* Ungültige Schlüsselnamen: `123`, `price!123`.

## Präfix von Schlüsselvariablen mit `c_`

Das `c_`-Präfix ist *immer* erforderlich, wenn die Parameter, die Daten über eine Ereignisaufruf-URL senden, diese Syntax verwenden.

---
title: "RuntimeClassType 列挙型 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassType 列挙型"
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RuntimeClassType 列挙型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

サポートされている [RuntimeClass](../windows/runtimeclass-class.md) インスタンスの種類を指定します。  
  
## 構文  
  
```  
enum RuntimeClassType;  
```  
  
## メンバー  
  
### 値  
  
|名前|説明|  
|--------|--------|  
|`ClassicCom`|標準的な COM ランタイム クラス。|  
|`Delegate`|これは、**ClassicCom** に相当します。|  
|`InhibitFtmBase`|`__WRL_CONFIGURATION_LEGACY__` を定義するが無効な `FtmBase` サポート。|  
|`InhibitWeakReference`|無効の弱い参照サポート。|  
|`WinRt`|[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] クラス。|  
|`WinRtClassicComMix`|`WinRt` と `ClassicCom` の組み合わせです。|  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)
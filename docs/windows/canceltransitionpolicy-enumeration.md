---
title: "CancelTransitionPolicy 列挙型 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled"
  - "module/Microsoft::WRL::CancelTransitionPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CancelTransitionPolicy 列挙型"
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CancelTransitionPolicy 列挙型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

完了の終了状態への遷移への非同期操作の例では、クライアント要求された取り消された状態に対してまたはエラーがどのように動作するかを示します。  
  
## 構文  
  
```  
enum CancelTransitionPolicy;  
```  
  
## メンバー  
  
### 値  
  
|名前|説明|  
|--------|--------|  
|`RemainCanceled`|非同期操作がクライアントからの要求された Canceled 状態に置かれている場合は、これで完了したターミナルまたはエラー状態に遷移に対して取り消された状態に収めることを示します。|  
|`TransitionFromCanceled`|非同期操作がクライアントからの要求された Canceled 状態に置かれている場合は、これによって取り消された状態からエラーまたはこのフラグを利用する呼び出しに従い、完了の終了状態への遷移状態があることを示します。|  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)
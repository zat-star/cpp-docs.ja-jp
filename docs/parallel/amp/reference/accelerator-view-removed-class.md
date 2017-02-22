---
title: "accelerator_view_removed クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator_view_removed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "amprt/Concurrency::accelerator_view_removed クラス"
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# accelerator_view_removed クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

基になる DirectX の呼び出しが Windows のタイムアウトの検出と回復機構が原因で失敗した場合にスローされる例外。  
  
## 構文  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[accelerator\_view\_removed::accelerator\_view\_removed コンストラクター](../Topic/accelerator_view_removed::accelerator_view_removed%20Constructor.md)|`accelerator_view_removed` クラスの新しいインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[accelerator\_view\_removed::get\_view\_removed\_reason メソッド](../Topic/accelerator_view_removed::get_view_removed_reason%20Method.md)|`accelerator_view` オブジェクトの削除の理由を示す HRESULT エラー コードを返します。|  
  
## 継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## 必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  
  
## 参照  
 [Concurrency 名前空間 \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
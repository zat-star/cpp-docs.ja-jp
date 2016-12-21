---
title: "packaged_task クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "future/std::packaged_task"
dev_langs: 
  - "C++"
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# packaged_task クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

呼び出しシグネチャが `Ty(ArgTypes...)`である呼び出しラッパーの *非同期プロバイダーに* ついて説明します。  この *関連付けられた非同期状態* が意図した結果の他に、呼び出し可能オブジェクトのコピーを保持します。  
  
## 構文  
  
```  
template<class>  
class packaged_task;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[packaged\_task::packaged\_task コンストラクター](../Topic/packaged_task::packaged_task%20Constructor.md)|`packaged_task` オブジェクトを構築します。|  
|[packaged\_task::~packaged\_task デストラクター](../Topic/packaged_task::~packaged_task%20Destructor.md)|`packaged_task` オブジェクトを破棄します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[packaged\_task::get\_future メソッド](../Topic/packaged_task::get_future%20Method.md)|同じ関連の非同期状態が存在 [今後](../standard-library/future-class.md) オブジェクトを返します。|  
|[packaged\_task::make\_ready\_at\_thread\_exit メソッド](../Topic/packaged_task::make_ready_at_thread_exit%20Method.md)|関連付けられた非同期状態に格納される呼び出し、アトミックに戻り値が呼び出し可能オブジェクトを格納します。|  
|[packaged\_task::reset メソッド](../Topic/packaged_task::reset%20Method.md)|関連付けられた非同期状態を置き換えます。|  
|[packaged\_task::swap メソッド](../Topic/packaged_task::swap%20Method.md)|指定されたオブジェクトの型と関連付けられた非同期状態を交換します。|  
|[packaged\_task::valid メソッド](../Topic/packaged_task::valid%20Method.md)|オブジェクトに関連付けられた非同期状態であるかどうかを指定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[packaged\_task::operator\= 演算子](../Topic/packaged_task::operator=%20Operator.md)|指定したオブジェクトに関連付けられた非同期状態を転送します。|  
|[packaged\_task::operator\(\) 演算子](../Topic/packaged_task::operator\(\)%20Operator.md)|関連付けられた非同期状態に格納されている呼び出し可能オブジェクトを、アトミックに保存して戻り値、*準備完了に*設定して状態を呼び出します。|  
|[packaged\_task::operator bool 演算子](../Topic/packaged_task::operator%20bool%20Operator.md)|オブジェクトに関連付けられた非同期状態であるかどうかを指定します。|  
  
## 必要条件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)
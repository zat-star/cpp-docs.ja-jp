---
title: "future クラス | Microsoft Docs"
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
  - "future/std::future"
dev_langs: 
  - "C++"
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# future クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*非同期オブジェクトに*ついて説明します。  
  
## 構文  
  
```  
template<class Ty>  
class future;  
```  
  
## 解説  
 各標準 *非同期プロバイダーは* 型がこのテンプレートのインスタンス化であるオブジェクトを返します。  `future` オブジェクトが関連付けられている非同期プロバイダーへのアクセスを提供します。  同じ非同期プロバイダーに関連付けられた複数の非同期オブジェクトが必要な場合は、[shared\_future](../standard-library/shared-future-class.md) オブジェクトへの `future` オブジェクトをコピーします。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[future::future コンストラクター](../Topic/future::future%20Constructor.md)|`future` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[future::get メソッド](../Topic/future::get%20Method.md)|関連付けられた非同期状態に格納される結果を取得します。|  
|[future::share メソッド](../Topic/future::share%20Method.md)|`shared_future`にオブジェクトを変換します。|  
|[future::valid メソッド](../Topic/future::valid%20Method.md)|オブジェクトが空でないかどうかを指定します。|  
|[future::wait メソッド](../Topic/future::wait%20Method.md)|関連付けられた非同期状態の準備が整うまで現在のスレッドをブロックします。|  
|[future::wait\_for メソッド](../Topic/future::wait_for%20Method.md)|関連付けられた非同期状態までブロックの準備ができていないか、指定した時間が経過する。|  
|[future::wait\_until メソッド](../Topic/future::wait_until%20Method.md)|関連付けられた非同期状態までブロックは準備が整ったまたは指定した時点まで。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[future::operator\= 演算子](../Topic/future::operator=%20Operator.md)|指定したオブジェクトに関連付けられた非同期状態を転送します。|  
  
## 必要条件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)
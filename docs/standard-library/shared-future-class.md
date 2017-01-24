---
title: "shared_future クラス | Microsoft Docs"
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
  - "future/std::shared_future"
dev_langs: 
  - "C++"
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# shared_future クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*非同期オブジェクトに*ついて説明します。  [今後](../standard-library/future-class.md) オブジェクトに対して、*非同期プロバイダーは*`shared_future` オブジェクトの任意の列に関連付けることができます。  
  
## 構文  
  
```  
template<class Ty>  
class shared_future;  
```  
  
## 解説  
 *空*である `shared_future` オブジェクトの `valid`、`operator=`とデストラクター以外のメソッドを呼び出さないでください。  
  
 `shared_future` オブジェクトは同期されません。  複数のスレッドが同じオブジェクトのメソッドを呼び出すと、予測できない結果になるデータの競合が発生します。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[shared\_future::shared\_future コンストラクター](../Topic/shared_future::shared_future%20Constructor.md)|`shared_future` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[shared\_future::get メソッド](../Topic/shared_future::get%20Method.md)|*関連付けられた非同期状態*に格納される結果を取得します。|  
|[shared\_future::valid メソッド](../Topic/shared_future::valid%20Method.md)|オブジェクトが空でないかどうかを指定します。|  
|[shared\_future::wait メソッド](../Topic/shared_future::wait%20Method.md)|関連付けられた非同期状態の準備が整うまで現在のスレッドをブロックします。|  
|[shared\_future::wait\_for メソッド](../Topic/shared_future::wait_for%20Method.md)|関連付けられた非同期状態までブロックの準備ができていないか、指定した時間が経過する。|  
|[shared\_future::wait\_until メソッド](../Topic/shared_future::wait_until%20Method.md)|関連付けられた非同期状態までブロックは準備が整ったまたは指定した時点まで。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[shared\_future::operator\= 演算子](../Topic/shared_future::operator=%20Operator.md)|新しい関連の非同期状態を割り当てます。|  
  
## 必要条件  
 **ヘッダー:** future  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)
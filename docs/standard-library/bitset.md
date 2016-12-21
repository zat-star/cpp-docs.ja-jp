---
title: "&lt;bitset&gt; | Microsoft Docs"
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
  - "std::<bitset>"
  - "std.<bitset>"
  - "<bitset>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<bitset> ヘッダー"
  - "bitset ヘッダー"
ms.assetid: af30a9b9-489e-46e3-9d29-5f3ea07ae6dc
caps.latest.revision: 19
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;bitset&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ビットの固定サイズ シーケンスを表して処理するための、テンプレート クラス ビットセットと 2 つのサポート テンプレート関数を定義します。  
  
## 構文  
  
```  
  
#include <bitset>  
  
```  
  
### 演算子  
  
|||  
|-|-|  
|[演算子 &](../Topic/operator&%20\(%3Cbitset%3E\).md)|次の 2 つのビットセット間でビットごとの AND を実行します。|  
|[演算子 \<\<](../Topic/operator%3C%3C%20\(%3Cbitset%3E\).md)|ビット シーケンスのテキスト表現を標準出力ストリームに挿入します。|  
|[演算子 \>\>](../Topic/operator%3E%3E%20\(%3Cbitset%3E\).md)|ビット シーケンスのテキスト表現を標準入力ストリームに挿入します。|  
|[operator^](../Topic/operator%5E%20\(%3Cbitset%3E\).md)|次の 2 つのビットセット間でビットごとの EXCLUSIVE\-OR を実行します。|  
|[演算子 &#124;](../Topic/operator%7C%20\(%3Cbitset%3E\).md)|次の 2 つのビットセット間でビットごとの OR を実行します。|  
  
### クラス  
  
|||  
|-|-|  
|[bitset クラス](../Topic/bitset%20Class.md)|このテンプレート クラスは、固定数のビットで構成されるシーケンスを格納するオブジェクト型を記述します。これらのビットによって、一連の項目または条件のフラグを保持するためのコンパクトな方法が提供されます。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
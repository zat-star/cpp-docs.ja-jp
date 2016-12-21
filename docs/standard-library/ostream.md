---
title: "&lt;ostream&gt; | Microsoft Docs"
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
  - "std.<ostream>"
  - "<ostream>"
  - "ostream/std::<ostream>"
  - "std::<ostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream ヘッダー"
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: 20
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレート クラス [basic\_ostream](../Topic/basic_ostream%20Class.md) を定義します。これは、入出力ストリームへの挿入を仲介します。  ヘッダーは、関連する複数のマニピュレーターを定義します   \(通常このヘッダーは、別の iostream ヘッダーに含まれています。  まれに、直接含めなければならないことがあります\)。  
  
## 構文  
  
```  
  
#include <ostream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[ostream](../Topic/ostream.md)|`char` に特殊化した `basic_ostream` と、`char` に特殊化した `char_traits` に基づいて型を作成します。|  
|[wostream](../Topic/wostream.md)|`wchar_t` に特殊化した `basic_ostream` と、`wchar_t` に特殊化した `char_traits` に基づいて型を作成します。|  
  
### マニピュレーター  
  
|||  
|-|-|  
|[endl](../Topic/endl.md)|行を終了し、バッファーをフラッシュします。|  
|[終点](../Topic/ends%20\(Standard%20C++%20Library\).md)|文字列を終了します。|  
|[flush](../Topic/flush%20\(Standard%20C++%20Library\).md)|バッファーをフラッシュします。|  
||左側の `basic_ostream` オブジェクト パラメーターの値と右側の `basic_ostream` オブジェクト パラメーターの値を交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[演算子 \<\<](../Topic/operator%3C%3C%20\(%3Costream%3E\).md)|さまざまな型をストリームに書き込みます。|  
  
### クラス  
  
|||  
|-|-|  
|[basic\_ostream](../Topic/basic_ostream%20Class.md)|このテンプレート クラスは、要素とエンコードされたオブジェクトをストリーム バッファーに挿入する操作を制御するオブジェクトを記述します。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)
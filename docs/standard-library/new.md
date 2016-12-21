---
title: "&lt;new&gt; | Microsoft Docs"
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
  - "std::<new>"
  - "<new>"
  - "std.<new>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "new ヘッダー"
ms.assetid: 218e2a15-34e8-4ef3-9122-1e90eccf8559
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;new&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログラムの制御下でストレージの割り当てと解放を制御するいくつかの型および関数を定義します。  また、ストレージ管理エラーに関するレポート用のコンポーネントを定義します。  
  
## 構文  
  
```  
  
#include <new>  
  
```  
  
## 解説  
 このヘッダーで宣言されている関数の一部は置換できます。  実装の際に既定のバージョンが提供されます。既定バージョンの動作については、このドキュメントで説明します。  ただし、プログラムで同じシグネチャを持つ関数を定義して、リンク時に既定のバージョンを置換することもできます。  置換バージョンは、このドキュメントで説明する要件を満たす必要があります。  
  
### オブジェクト  
  
|||  
|-|-|  
|[nothrow](../Topic/nothrow%20\(%3Cnew%3E\).md)|引数として使用するオブジェクトを `nothrow` バージョンの **new** および **delete** に提供します。|  
  
### Typedefs  
  
|||  
|-|-|  
|[new\_handler](../Topic/new_handler.md)|新しいハンドラーとして使用するのに適した関数を指す型。|  
  
### Functions  
  
|||  
|-|-|  
|[set\_new\_handler](../Topic/set_new_handler.md)|メモリ割り当ての試行に新たに失敗した場合に呼び出されるユーザー関数をインストールします。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md)|個々のオブジェクトに対するストレージの割り当てを解除する削除式によって呼び出される関数。|  
|[operator delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md)|オブジェクトの配列に対するストレージの割り当てを解除する削除式によって呼び出される関数。|  
|[new 演算子](../Topic/operator%20new%20\(%3Cnew%3E\).md)|個々のオブジェクトにストレージを割り当てる新しい式によって呼び出される関数。|  
|[new&#91;&#93; 演算子](../Topic/operator%20new\(%3Cnew%3E\).md)|オブジェクトの配列にストレージを割り当てる新しい式によって呼び出される関数。|  
  
### クラス  
  
|||  
|-|-|  
|[bad\_alloc クラス](../standard-library/bad-alloc-class.md)|このクラスは、割り当て要求が成功しなかったことを示すためにスローされる例外を記述します。|  
|[nothrow\_t クラス](../standard-library/nothrow-t-structure.md)|このクラスは、新しい演算子への関数のパラメーターとして使用され、この関数が割り当ての失敗を報告するには、例外をスローするのではなく null ポインターを返す必要があることを示します。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
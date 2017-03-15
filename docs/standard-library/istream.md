---
title: "&lt; istream &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istream/std::<istream>"
  - "std.<istream>"
  - "<istream>"
  - "std::<istream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream ヘッダー"
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt; istream &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

iostream の抽出を仲介するテンプレート クラス basic\_istream と、挿入と抽出の両方を仲介するテンプレート クラス basic\_iostream を定義します。 ヘッダーは、関連するマニピュレーターも定義します。 このヘッダー ファイルは通常、別の iostream ヘッダーに含まれているため、ほとんどの場合、直接含める必要はありません。  
  
## 構文  
  
```  
  
#include <istream>  
  
```  
  
### Typedefs  
  
|||  
|-|-|  
|[iostream](../Topic/iostream.md)|`char` に特殊化された型 `basic_iostream`。|  
|[istream](../Topic/istream.md)|`char` に特殊化された型 `basic_istream`。|  
|[wiostream](../Topic/wiostream.md)|**wchar** に特殊化された型 `basic_iostream`。|  
|[wistream](../Topic/wistream.md)|**wchar** に特殊化された型 `basic_istream`。|  
  
### マニピュレーター  
  
|||  
|-|-|  
|[ws](../Topic/ws.md)|ストリーム内の空白をスキップします。|  
|[swap](../Topic/%3Cistream%3E%20swap.md)|2 つのストリーム オブジェクトを交換します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator\>\>](../Topic/operator%3E%3E%20\(%3Cistream%3E\).md)|ストリームから文字と文字列を抽出します。|  
  
### クラス  
  
|||  
|-|-|  
|[basic\_iostream](../standard-library/basic-iostream-class.md)|入力と出力の両方を行うことができるストリーム クラス。|  
|[basic\_istream](../Topic/basic_istream%20Class.md)|このテンプレート クラスは、**Elem** 型の要素を含むストリーム バッファーからの要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。Elem 型は [char\_type](../Topic/basic_ios::char_type.md) とも呼ばれ、その特性は、[traits\_type](../Topic/basic_ios::traits_type.md) とも呼ばれるクラス **Tr** によって決定されます。|  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)
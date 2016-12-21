---
title: "コンパイラ エラー C2872 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2872"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2872"
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2872
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : あいまいなシンボルです。  
  
 参照しているシンボルを識別できません。  
  
 C2872 は、ヘッダー ファイルに [using ディレクティブ](../../misc/using-directive-cpp.md) が含まれ、その次のヘッダー ファイルが `#include` でインクルードされ、さらに `using` ディレクティブで指定された名前空間にも存在する型を含んでいる場合に発生することがあります。  `using` ディレクティブは、すべてのヘッダー ファイルを `#include` で指定した後に指定してください。  
  
 C2872 の詳細については、参照します [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;316317](http://support.microsoft.com/default.aspx?scid=kb;en-us;316317)。  
  
 次の例では警告 C2872 が生成されます。  
  
```  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```
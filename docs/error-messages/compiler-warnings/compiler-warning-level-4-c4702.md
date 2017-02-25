---
title: "コンパイラの警告 (レベル 4) C4702 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4702"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4702"
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 4) C4702
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

制御が渡らないコードです。  
  
 この警告は、"Visual Studio .NET 2003 : 制御が渡らないコード" に対して行われたコンパイラ準拠作業の結果です。  コンパイラ \(バック エンド\) は、制御が渡らないコードを検出した場合に、レベル 4 の警告である C4702 を生成します。  
  
 Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C\+\+ で有効なコードを作成するには、制御が渡らないコードを削除するか、すべてのソース コードがなんらかの実行フローで到達できるようにします。  
  
## 使用例  
 次の例では C4702 エラーが生成されます。  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## 使用例  
 **\/GX**、**\/EHc**、**\/EHsc**、または  **\/EHac** を指定してコンパイルし、extern C 関数を使用する場合、コードに制御が渡らなくなります。これは、extern C 関数はスローしないと見なされ、catch ブロックに到達できないからです。関数によるスローができるのでこの警告が有効ではないと思われる場合は、スローされる例外に応じて、**\/EHa** または **\/EHs** を指定してコンパイルします。  
  
 詳細については、「[\/EH \(例外処理モデル\)](../../build/reference/eh-exception-handling-model.md)」を参照してください。  
  
 次の例では C4702 エラーが生成されます。  
  
```  
// C4702b.cpp  
// compile with: /W4 /EHsc  
#include <iostream>  
  
using namespace std;  
extern "C" __declspec(dllexport) void Function2(){}  
  
int main() {  
   try {  
      Function2();  
   }  
   catch (...) {  
      cout << "Exp: Function2!" << endl;   // C4702  
   }  
}  
```
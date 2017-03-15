---
title: "コンパイラの警告 (レベル 1) C4005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4005"
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'識別子' : マクロが再定義されました。  
  
 マクロ識別子が 2 回定義されています。  コンパイラが 2 つ目のマクロ定義を使用しています。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  マクロをコマンド ラインとコード内の `#define` ディレクティブの両方で定義しています。  
  
2.  マクロがインクルード ファイルからインポートされています。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  いずれかの定義を削除します。  
  
2.  2 つ目の定義の前に [\#undef](../../preprocessor/hash-undef-directive-c-cpp.md) ディレクティブを使用します。  
  
 次の例では警告 C4005 が生成されます。  
  
```  
// C4005.cpp  
// compile with: /W1 /EHsc  
#include <iostream>  
using namespace std;  
  
#define TEST "test1"  
#define TEST "test2"   // C4005 delete or rename to resolve the warning  
  
int main() {  
   cout << TEST << endl;  
}  
```
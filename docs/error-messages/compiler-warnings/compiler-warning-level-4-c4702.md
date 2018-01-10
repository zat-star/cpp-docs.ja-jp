---
title: "コンパイラの警告 (レベル 4) C4702 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4702
dev_langs: C++
helpviewer_keywords: C4702
ms.assetid: d8198c1e-8762-42a6-9e6b-cb568b7a1686
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ef7420f3699363d33d195e2455ab9fddf88de40
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4702"></a>コンパイラの警告 (レベル 4) C4702
到達できないコード  
  
 この警告は、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果: 制御が渡らないコードです。 C4702 が生成されます (バック エンド)、コンパイラは、到達できないコードを検出すると、レベル 4 の警告です。  
  
 Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C では有効では、コードの場合は、到達できないコードを削除するか、すべてのソース コードが実行のいくつかのフローに到達できることを保証します。  
  
## <a name="example"></a>例  
 次の例では、C4702 が生成されます。  
  
```  
// C4702.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main() {  
   return 1;  
   printf_s("I won't print.\n");   // C4702 unreachable  
}  
```  
  
## <a name="example"></a>例  
 コンパイルするときに**/GX**、 **/EHc**、 **/EHsc**、または**/EHac**になり、extern C 関数を使用して、コードが到達できないため extern C関数をスローしないと見なされます、したがって、catch ブロックが到達可能ではありません。  この警告が無効である関数をスローすることができる場合、コンパイル時に**/EHa**または**/EHs**によってスローされる例外。  
  
 詳細については、次を参照してください。 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)詳細についてはします。  
  
 次の例では、C4702 が生成されます。  
  
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
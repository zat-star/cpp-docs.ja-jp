---
title: "コンパイラの警告 (レベル 1) C4005 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4005
dev_langs:
- C++
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 21023cf79a2ec25f94dc68cd3a55f722fa8316d8
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4005"></a>コンパイラの警告 (レベル 1) C4005
'identifier': 再定義はマクロ  
  
 マクロの識別子が 2 回定義されています。 コンパイラは、2 番目のマクロ定義を使用します。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  コマンドラインで、コードでは、マクロを定義する、`#define`ディレクティブです。  
  
2.  マクロはインクルード ファイルからインポートします。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  いずれかの定義を削除します。  
  
2.  使用して、 [#undef](../../preprocessor/hash-undef-directive-c-cpp.md)ディレクティブを 2 つ目の定義の前にします。  
  
 次の例では、C4005 が生成されます。  
  
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

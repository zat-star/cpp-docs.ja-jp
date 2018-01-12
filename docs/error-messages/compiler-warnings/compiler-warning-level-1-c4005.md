---
title: "コンパイラの警告 (レベル 1) C4005 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4005
dev_langs: C++
helpviewer_keywords: C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf0c5777cecf89bb0723b30c87dc4c856de0a016
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
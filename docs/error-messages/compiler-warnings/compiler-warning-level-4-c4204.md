---
title: "コンパイラの警告 (レベル 4) C4204 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4204
dev_langs:
- C++
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4ce45302200b0e4b9d664c6e2bdbd9b849f27292
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4204"></a>コンパイラの警告 (レベル 4) C4204
非標準の拡張機能が使用されています : 定数でない初期化子の集合です。  
  
 Microsoft の拡張機能 (/Ze)、定数ではない値を持つ集約型 (配列、構造体、共用体、およびクラス) を初期化することができます。  
  
## <a name="example"></a>例  
  
```  
// C4204.c  
// compile with: /W4  
int func1()  
{  
   return 0;  
}  
struct S1  
{  
   int i;  
};  
  
int main()  
{  
   struct S1 s1 = { func1() };   // C4204  
   return s1.i;  
}  
```  
  
 このような初期化は ANSI 互換の無効な ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。

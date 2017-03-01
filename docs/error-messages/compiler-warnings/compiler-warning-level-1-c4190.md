---
title: "コンパイラの警告 (レベル 1) C4190 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
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
translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf45c0737f52da93f93c1f95d313771f0e92a10e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4190"></a>コンパイラの警告 (レベル 1) C4190
'identifier1' を指定すると、C リンケージを持つ UDT C と互換性がない ' identifier2' を返す  
  
 関数または関数へのポインターは、UDT (ユーザー定義型、クラス、構造体、列挙型、または共用体である) を戻り値の型と、 `extern` "C"リンケージ。 これは、有効な場合。  
  
-   この関数のすべての呼び出しは、C++ から発生します。  
  
-   関数の定義は、C++ でです。  
  
## <a name="example"></a>例  
  
```cpp  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```

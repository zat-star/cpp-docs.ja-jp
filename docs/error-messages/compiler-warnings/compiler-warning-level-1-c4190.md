---
title: "コンパイラの警告 (レベル 1) C4190 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 127eb4327826412d605f2a4a008e411880998073
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4190"></a>コンパイラの警告 (レベル 1) C4190
'identifier1' を指定すると、C リンケージを持つ UDT 'identifier2' C と互換性がないを返す  
  
 関数または関数へのポインターは、戻り値の型として、UDT (ユーザー定義型、クラス、構造体、列挙型、または共用体である) を持つと`extern`"C"リンケージ。 これは有効な場合。  
  
-   この関数に対するすべての呼び出しは、C++ から発生します。  
  
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
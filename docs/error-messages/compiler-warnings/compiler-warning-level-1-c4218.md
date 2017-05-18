---
title: "コンパイラの警告 (レベル 1) C4218 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4218
dev_langs:
- C++
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6f657da21a7756973b9f9febe823003ebfd68fd1
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4218"></a>コンパイラの警告 (レベル 1) C4218
非標準の拡張機能が使用されています : 少なくとも、ストレージ クラスか型を指定しなければなりません。  
  
 既定 Microsoft の拡張機能 (/Ze)、型やストレージ クラスを指定することがなく変数を宣言することができます。 既定の型は `int` です。  
  
## <a name="example"></a>例  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 このような宣言は、ANSI 互換の無効な ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。

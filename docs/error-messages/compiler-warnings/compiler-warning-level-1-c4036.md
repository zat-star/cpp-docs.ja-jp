---
title: "コンパイラの警告 (レベル 1) C4036 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4036
dev_langs:
- C++
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 10
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 30ff24d9d8746d914ba4dd098e715d8b5ecb55c9
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4036"></a>コンパイラの警告 (レベル 1) C4036
実パラメーターとして渡される 'type' に型指定がありません  
  
 実パラメーターとして使用される構造体、共用体、列挙型、またはクラスの型名が指定されていません。 使用している場合[/Zg](../../build/reference/zg-generate-function-prototypes.md)関数プロトタイプを生成するには、コンパイラの問題をするこの警告と生成されたプロトタイプの仮パラメーターがコメント アウトします。  
  
 この警告を解決するには、型名を指定します。  
  
## <a name="example"></a>例  
 次の例では C4036 が生成されます。  
  
```  
// C4036.c  
// compile with: /Zg /W1  
// D9035 expected  
typedef struct { int i; } T;  
void f(T* t) {}   // C4036  
  
// OK  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```

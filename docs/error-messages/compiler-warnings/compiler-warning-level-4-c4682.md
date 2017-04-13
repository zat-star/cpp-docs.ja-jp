---
title: "コンパイラの警告 (レベル 4) C4682 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4682
dev_langs:
- C++
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 718382c17fd0b108322a29f99c3b3a2d2c813d6c
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4682"></a>コンパイラの警告 (レベル 4) C4682
'parameter': 方向性のあるパラメーター属性が指定されていません。[in] を既定とします  
  
 属性付きインターフェイス内のパラメーターにメソッドが、方向属性のいずれかの:[で](../../windows/in-cpp.md)または[アウト](../../windows/out-cpp.md)です。 パラメーターの既定値は in です。  
  
 既定では、この警告はオフに設定されています。 参照してください[コンパイラの警告無効になっている既定](../../preprocessor/compiler-warnings-that-are-off-by-default.md)詳細についてはします。  
  
 次の例では C4682 警告が生成されます。  
  
```  
// C4682.cpp  
// compile with: /W4  
#pragma warning(default : 4682)  
#include <windows.h>  
[module(name="MyModule")];  
  
[ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ]  
__interface IMyIface : IUnknown  
{  
   HRESULT f1(int i, int *pi); // C4682  
   // try the following line  
   // HRESULT f1([in] int i, [in] int *pi);  
};  
  
int main()  
{  
}  
```

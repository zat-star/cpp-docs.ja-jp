---
title: "コンパイラの警告 (レベル 1) C4674 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4674
dev_langs:
- C++
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
caps.latest.revision: 9
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ca99a22e6f91f44af58a1421d59151597017cddb
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4674"></a>コンパイラの警告 (レベル 1) C4674
'method' は宣言された 'static' であり、パラメーターを&1; つだけ持たなければなりません。  
  
変換演算子の署名が正しくありません。 メソッドは、ユーザー定義の変換とは見なされません。 オペレーターの定義の詳細については、次を参照してください。[ユーザー定義演算子 (C + +/CLI)](../../dotnet/user-defined-operators-cpp-cli.md)と[ユーザー定義の変換 (C + +/CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)します。  
  
## <a name="example"></a>例  
 次の例では C4674 が生成されます。  
  
```  
// C4674.cpp  
// compile with: /clr /WX /W1 /LD  
ref class G {  
   int op_Implicit(int i) {   // C4674  
      return 0;  
   }  
};  
```  


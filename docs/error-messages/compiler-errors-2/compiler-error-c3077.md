---
title: "コンパイラ エラー C3077 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3077
dev_langs:
- C++
helpviewer_keywords:
- C3077
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
caps.latest.revision: 6
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
ms.openlocfilehash: c7647e3700036e360858fd616df330e6db964835
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3077"></a>コンパイラ エラー C3077
'finalizer': ファイナライザーは、参照型のメンバーにのみなることができます  
  
 ネイティブ型または値型でファイナライザーを宣言することはできません。  
  
 詳細については、次を参照してください。[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C + +/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。  
  
## <a name="example"></a>例  
 次の例では警告 C3077 が生成されます。  
  
```  
// C3077.cpp  
// compile with: /clr /c  
value struct vs {  
   !vs(){}   // C3077  
};  
  
ref struct rs {  
protected:  
   !rs(){}   // OK  
};  
```

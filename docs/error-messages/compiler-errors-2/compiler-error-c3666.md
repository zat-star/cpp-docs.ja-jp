---
title: "コンパイラ エラー C3666 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3666
dev_langs:
- C++
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
caps.latest.revision: 6
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 68c327954c21fc6c39ed63e3e5211c7383f30971
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3666"></a>コンパイラ エラー C3666
'コンス トラクター': オーバーライド指定子 'キーワード' コンス トラクターでは許可されません  
  
 オーバーライド指定子は、コンス トラクターで使用されていたし、は許可されていません。 詳細については、次を参照してください。[オーバーライド指定子](../../windows/override-specifiers-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
 次の例では、c3666 エラーを生成します。  
  
```  
// C3666.cpp  
// compile with: /clr /c  
ref struct R {  
   R() new {}   // C3666  
   R(int i) {}   // OK  
};  
```

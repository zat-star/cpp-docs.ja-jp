---
title: "コンパイラ エラー C3133 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3133
dev_langs:
- C++
helpviewer_keywords:
- C3133
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
caps.latest.revision: 9
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
ms.openlocfilehash: 12a87a5a23fa4a613b45c2c11b0845ed4adc33e8
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3133"></a>コンパイラ エラー C3133
C++ varargs に属性を適用することはできません。  
  
 属性が正しく適用されませんでした。 属性は、可変個の引数を表す省略記号にない適用できます。  
  
 詳細については、次を参照してください。[ユーザー定義属性](../../windows/user-defined-attributes-cpp-component-extensions.md)します。  
  
## <a name="example"></a>例  
 次の例では、c3133 エラーを生成します。  
  
```  
// C3133.cpp  
// compile with: /clr /c  
ref struct MyAttr: System::Attribute {};   
void Func([MyAttr]...);   // C3133  
void Func2([MyAttr] int i);   // OK  
```

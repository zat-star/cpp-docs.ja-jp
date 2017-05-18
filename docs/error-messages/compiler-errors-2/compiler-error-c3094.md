---
title: "コンパイラ エラー C3094 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3094
dev_langs:
- C++
helpviewer_keywords:
- C3094
ms.assetid: 10da9b7c-e72d-4013-9925-c83e1bb142db
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fc0eea13e1b630d651c267df1b228afbadee56c5
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3094"></a>コンパイラ エラー C3094
'attribute': 匿名使用は許可されていません  
  
 属性のスコープを正しく指定しませんでした。  詳細については、次を参照してください。[ユーザー定義の属性](../../windows/user-defined-attributes-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では C3094 が生成されます。  
  
```  
// C3094.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
public ref class AAttribute : Attribute {};  
  
[A];   // C3094  
  
// OK  
[A]  
ref class x{};  
```

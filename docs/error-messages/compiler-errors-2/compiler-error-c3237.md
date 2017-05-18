---
title: "コンパイラ エラー C3237 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3237
dev_langs:
- C++
helpviewer_keywords:
- C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 0f4ae2e268f31b0c04f86d47318e597bb1beb412
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3237"></a>コンパイラ エラー C3237
'generic_class' : ジェネリック クラスをカスタム属性にすることはできません  
  
 ジェネリック クラスは、ユーザー定義の属性にすることはできません。  
  
## <a name="example"></a>例  
 次の例では C3237 が生成されます。  
  
```  
// C3237.cpp  
// compile with: /clr /c  
// C3237 expected  
using namespace System;  
  
generic <class T>  
// Delete the following line to resolve.  
[attribute(AttributeTargets::All, AllowMultiple=true)]  
public ref class GR {};  
```

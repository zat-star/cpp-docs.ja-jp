---
title: "コンパイラの警告 C4694 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4694
dev_langs:
- C++
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
caps.latest.revision: 3
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
ms.openlocfilehash: dd8b88c06a24b0f4cfa029a8558a0fc890bba57f
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4694"></a>コンパイラの警告 C4694
'class_1': シールされた抽象クラスには、基底クラス 'base_class' を含めることはできません  
  
 シールされた抽象クラスは参照型を継承できません。シールされた抽象クラスは、基底クラスの関数を実装することも、それ自体を基底クラスとして使用しすることもできません。  
  
 詳細については、次を参照してください。[抽象](../../windows/abstract-cpp-component-extensions.md)を[シール](../../windows/sealed-cpp-component-extensions.md)をと[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では C4694 が生成されます。  
  
```  
// C4694.cpp  
// compile with: /c /clr  
ref struct A {};  
ref struct B sealed abstract : A {};   // C4694  
```

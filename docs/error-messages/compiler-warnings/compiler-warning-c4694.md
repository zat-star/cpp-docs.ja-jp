---
title: "コンパイラの警告 C4694 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 04754b1215cf3c4ee44554a253ef6d00b0b67f2b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4694"></a>コンパイラの警告 C4694
'class_1': シールされた抽象クラスには、基底クラス 'base_class' を含めることはできません  
  
 シールされた抽象クラスは参照型を継承できません。シールされた抽象クラスは、基底クラスの関数を実装することも、それ自体を基底クラスとして使用しすることもできません。  
  
 詳細については、次を参照してください。[抽象](../../windows/abstract-cpp-component-extensions.md)、[シール](../../windows/sealed-cpp-component-extensions.md)、および[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では C4694 が生成されます。  
  
```  
// C4694.cpp  
// compile with: /c /clr  
ref struct A {};  
ref struct B sealed abstract : A {};   // C4694  
```

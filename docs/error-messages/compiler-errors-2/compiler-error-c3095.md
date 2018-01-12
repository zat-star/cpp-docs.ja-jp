---
title: "コンパイラ エラー C3095 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3095
dev_langs: C++
helpviewer_keywords: C3095
ms.assetid: cde725be-0936-40f6-9e57-e1d7d0710f83
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 265062e7ba739dbef8e917d44d46ebd9261a289e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3095"></a>コンパイラ エラー C3095
'attribute': 属性を繰り返して使用できません  
  
 複数回出現する属性がターゲットに適用されないように、いくつかの属性が宣言されます。  
  
 詳細については、「 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3095 が生成されます。  
  
```  
// C3095.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::All, AllowMultiple=false)]  
public ref class Attr : public Attribute {  
public:  
   Attr(int t) : m_t(t) {}  
   const int m_t;  
};  
  
[AttributeUsage(AttributeTargets::All, AllowMultiple=true)]  
public ref class Attr2 : public Attribute {  
public:  
   Attr2(int t) : m_t(t) {}  
   const int m_t;  
};  
  
[Attr(10)]   // C3095  
[Attr(11)]  
ref class A {};  
  
[Attr2(10)]   // OK  
[Attr2(11)]  
ref class B {};  
```
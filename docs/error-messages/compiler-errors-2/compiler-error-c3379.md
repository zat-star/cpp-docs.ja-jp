---
title: "コンパイラ エラー C3379 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3379
dev_langs:
- C++
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9fd5a8acf918a0f6b485cf9ba94ad759d58f7b2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3379"></a>コンパイラ エラー C3379
'class': 入れ子になったクラスは、その宣言の一部としてアセンブリ アクセス指定子を持つことはできません  
  
 クラスまたは構造体などのマネージ型に適用すると、[パブリック](../../cpp/public-cpp.md)と[プライベート](../../cpp/private-cpp.md)キーワードは、クラスがアセンブリ メタデータを通じて公開されるかどうかを示します。 `public`または`private`外側のクラスのアセンブリのアクセスを継承しますが、入れ子になったクラスには適用できません。  
  
 使用すると[/clr](../../build/reference/clr-common-language-runtime-compilation.md)、`ref`と`value`キーワードは、クラスが管理されていることを示します (を参照してください[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md))。  
  
 次の例では、C3379 が生成されます。  
  
```  
// C3379a.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class A {  
public:  
   static int i = 9;  
  
   public ref class BA {   // C3379  
   // try the following line instead  
   // ref class BA {  
   public:  
      static int ii = 8;  
   };  
};  
  
int main() {  
  
   A^ myA = gcnew A;  
   Console::WriteLine(myA->i);  
  
   A::BA^ myBA = gcnew A::BA;  
   Console::WriteLine(myBA->ii);  
}  
```  

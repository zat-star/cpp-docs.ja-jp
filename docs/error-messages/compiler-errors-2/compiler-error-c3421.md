---
title: "コンパイラ エラー C3421 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3421
dev_langs:
- C++
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 8f7a25ee2cb8b36c8e56edf4edb2bf152d6bfd9e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3421"></a>コンパイラ エラー C3421
'type': このクラスのファイナライザーは、アクセスできないか、または存在しないため、呼び出すことができません  
  
 ファイナライザーは暗黙的にプライベートであるため、それを囲む型の外部から呼び出すことはできません。  
  
 詳細については、次を参照してください。[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C + +/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)します。  
  
## <a name="example"></a>例  
 次の例では C3421 が生成されます。  
  
```  
// C3421.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B {   
   !B() {}  
  
public:  
   ~B() {}  
};  
  
int main() {  
   A a;  
   a.!A();   // C3421  
  
   B b;  
   b.!B();   // C3421  
}  
```

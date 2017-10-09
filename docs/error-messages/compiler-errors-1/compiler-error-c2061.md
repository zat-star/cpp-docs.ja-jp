---
title: "コンパイラ エラー C2061 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2061
dev_langs:
- C++
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 82518c78b49418c10cc0cd07ae59e58336af08f3
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2061"></a>コンパイラ エラー C2061
構文エラー: 識別子 'identifier'  
  
 コンパイラは、ことが想定されている識別子を検出します。 確認して`identifier`が宣言されているは、使用する前にします。  
  
 初期化子は、かっこで囲むことがあります。 この問題を避けるためには、宣言子をかっこで囲みますまたはやすく、`typedef`です。  
  
 コンパイラが、クラス テンプレート引数として式を検出したときに、このエラーを発生する可能性がありますも使用して[typename](../../cpp/typename.md)これは、型をコンパイラに指示します。  
  
 次の例では、C2061 が生成されます。  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061 は、インスタンス名を渡す場合に発生する可能性が[typeid](../../windows/typeid-cpp-component-extensions.md):  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```

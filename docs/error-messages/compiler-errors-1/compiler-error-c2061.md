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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e18810742efa94cdd130c1e11a2cdda0656c9921
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
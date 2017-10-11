---
title: "コンパイラ エラー C3367 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3367
dev_langs:
- C++
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d1d144399ca42ba321d8f3d11425bf2ff8e65891
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3367"></a>コンパイラ エラー C3367
'static_member_function': バインドされていないデリゲートを作成するために静的関数を使用することはできません  
  
バインドされていないデリゲートを呼び出す場合は、オブジェクトのインスタンスを渡す必要があります。 静的メンバー関数はクラス名によって呼び出されるので、バインドされていないデリゲートは、インスタンス メンバー関数でのみインスタンス化できます。  
  
バインドされていないデリゲートの詳細については、次を参照してください。[する方法: 定義および使用するデリゲート (C + + CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)です。  
  
## <a name="example"></a>例  
次の例では C3367 が生成されます。  
  
```cpp  
// C3367.cpp  
// compile with: /clr  
ref struct R {  
   void b() {}  
   static void f() {}  
};  
  
delegate void Del(R^);  
  
int main() {  
   Del ^ a = gcnew Del(&R::b);   // OK  
   Del ^ b = gcnew Del(&R::f);   // C3367  
}  
```

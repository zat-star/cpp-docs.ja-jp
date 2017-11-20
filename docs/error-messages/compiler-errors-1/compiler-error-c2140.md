---
title: "コンパイラ エラー C2140 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2140
dev_langs: C++
helpviewer_keywords: C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cee9861b991ae853443a49e158634c7578dcb913
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2140"></a>コンパイラ エラー C2140
'type': ジェネリック型パラメーターに依存する型がコンパイラの組み込み型の特徴である 'trait' への引数として許可されていません  
  
 無効な型指定子は、型の特徴に渡されました。  
  
 詳細については、次を参照してください。[型の特徴のコンパイラ サポート](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C2140 を生成します。  
  
```  
// C2140.cpp  
// compile with: /clr /c  
template <class T>  
  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class x {};  
  
generic <class T>  
ref class C {  
   void f() {  
      System::Console::WriteLine(__is_polymorphic(T));   // C2140  
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140  
  
      System::Console::WriteLine(__is_polymorphic(x));   // OK  
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK  
   }  
};  
```
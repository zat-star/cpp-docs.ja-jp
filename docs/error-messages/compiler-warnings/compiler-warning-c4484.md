---
title: "コンパイラの警告 C4484 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4484
dev_langs:
- C++
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa5f209dd3a77bcc4ec3c21d589fb8ba1ed3faf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4484"></a>コンパイラの警告 C4484
'override_function': 基本 ref クラス メソッド 'base_class_function' と一致しますが、'virtual'、'new' または 'override'; に設定されていません'new' (および 'virtual') と見なされます  
  
 コンパイルするときに**/clr**コンパイラが vtable の新しいスロットを取得する関数を意味、基本クラスの関数を暗黙的にオーバーライドされません。 解決するには、関数は、上書きするかどうかを明示的に指定します。  
  
 詳細については次を参照してください:  
  
-   [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [override](../../windows/override-cpp-component-extensions.md)  
  
-   [new (新しいスロット vtable の)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md)  
  
 C4484 は常に、エラーとして発行されます。 使用して、[警告](../../preprocessor/warning.md)を抑制する状況 C4484 プラグマ。  
  
## <a name="example"></a>例  
 次の例では、C4484 を生成します。  
  
```  
// C4484.cpp  
// compile with: /clr  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : A {  
   void Test() {}   // C4484  
};  
  
// OK  
ref struct C {  
   virtual void Test() {}  
   virtual void Test2() {}  
};  
  
ref struct D : C {  
   virtual void Test() new {}  
   virtual void Test2() override {}  
};  
```
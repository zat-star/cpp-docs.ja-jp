---
title: "オーバーライド (C++ コンポーネント拡張) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 88138001a9767bbe9752c1de0577910fca8bc914
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="override--c-component-extensions"></a>override (C++ コンポーネント拡張)
状況依存の `override` キーワードは、型のメンバーが基底クラスまたは基本インターフェイスのメンバーをオーバーライドすることを示します。  
  
## <a name="remarks"></a>コメント  
 `override`キーワードは、ネイティブ ターゲット (既定のコンパイラ オプション) にコンパイルするときに有効な Windows ランタイム ターゲット (**/ZW**コンパイラ オプション)、または共通言語ランタイム ターゲット (**/clr**コンパイラオプション)。  
  
 オーバーライド指定子の詳細については、次を参照してください。[オーバーライド指定子](../cpp/override-specifier.md)と[オーバーライド指定子とネイティブ コンパイル](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)です。  
  
 状況依存のキーワードの詳細については、次を参照してください。[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)です。  
  
## <a name="examples"></a>使用例  
 **例**  
  
 次のコード例に、`override` をネイティブ コンパイルでも使用できることを示します。  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **例**  
  
 次のコード例に、`override` を Windows ランタイム コンパイルで使用できることを示します。  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **必要条件**  
  
 コンパイラ オプション: **/ZW**  
  
 **例**  
  
 次のコード例に、`override` を共通言語ランタイム コンパイルで使用できることを示します。  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **必要条件**  
  
 コンパイラ オプション: **/clr**  
  
## <a name="see-also"></a>参照  
 [オーバーライド指定子](../cpp/override-specifier.md)   
 [オーバーライド指定子](../windows/override-specifiers-cpp-component-extensions.md)
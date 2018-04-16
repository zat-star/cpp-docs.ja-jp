---
title: "_ _identifier (c + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs:
- C++
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4d68d21fc9436bff0e39fa474b97ec54138e15b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="identifier-ccli"></a>__identifier (C++/CLI)
識別子としては、Visual C のキーワードの使用を有効にします。  
  
## <a name="all-platforms"></a>すべてのプラットフォーム  
**構文**  
  
```  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
**解説**  
  
使用、`__identifier`キーワードではない識別子のキーワードは許可されていますが、スタイルの問題としてお勧めします。  
  
## <a name="windows-runtime"></a>Windows ランタイム  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/ZW**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の例では、という名前のクラス`template`c# で作成され、DLL として配布します。 使用する Visual C プログラムで、`template`クラス、`__identifier`キーワードを非表示に、ファクトを`template`は標準の C++ キーワード。  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **解説**  
  
 `__identifier`キーワードが有効では、 **/clr**コンパイラ オプション。  
  
### <a name="requirements"></a>必要条件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次の例では、という名前のクラス`template`c# で作成され、DLL として配布します。 使用する Visual C プログラムで、`template`クラス、`__identifier`キーワードを非表示に、ファクトを`template`は標準の C++ キーワード。  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="see-also"></a>参照  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)   
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)
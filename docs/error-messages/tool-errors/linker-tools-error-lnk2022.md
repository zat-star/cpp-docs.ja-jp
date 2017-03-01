---
title: "リンカ ツール エラー LNK2022 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2022
dev_langs:
- C++
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 91fb85679fd6c66bc97974912a2de688f494d5e9
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2022"></a>リンカ ツール エラー LNK2022
メタデータの操作に失敗しました (HRESULT): error_message  
  
 リンカーでは、メタデータのマージ中にエラーが検出されました。 正常にリンクには、メタデータのエラーを解決する必要があります。  
  
 この問題を診断する方法の&1; つは、実行する**ildasm – トークン**である種類を検索するオブジェクト ファイルにトークンが表示されている`error_message`、し、相違点を探します。  メタデータ、LayoutType の属性が異なる場合でも同じ名前の&2; つのさまざまな種類が有効でありません。  
  
 LNK2022 (構造体などの型と同じ名前が競合している定義は、複数のコンパイル単位に存在する場合とでコンパイルするときに理由の&1; つ[/clr](../../build/reference/clr-common-language-runtime-compilation.md)します。  ここで、型はすべてのコンパイル単位の同一の定義を持っていることを確認します。  型名が表示されて`error_message`します。  
  
 LNK2022 のもう&1; つの考えられる原因は、リンカーがコンパイラに指定された以外に、別の場所にメタデータ ファイルを検出 (と[#using](../../preprocessor/hash-using-directive-cpp.md) )。 あったため、コンパイラに渡されたときに、メタデータ ファイル (.dll または .netmodule) が、リンカーに渡される場合は、同じ場所があることを確認します。  
  
 ATL アプリケーションの使用を作成するときに[_ATL_MIXED](http://msdn.microsoft.com/Library/11b59a83-7098-43e2-9f7b-408299930966)少なくとも&1; つで使用されている場合はすべてのコンパイル単位が必要です。  
  
## <a name="example"></a>例  
 次の例では、空の型を定義します。  
  
```  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## <a name="example"></a>例  
 このサンプルでは、異なる定義は同じ名前の型を含む&2; つのソース コード ファイルをリンクできませんを示します。  
  
 次の例では、LNK2022 を生成します。  
  
```  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```

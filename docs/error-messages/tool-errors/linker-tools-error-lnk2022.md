---
title: "リンカ ツール エラー LNK2022 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2022"
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# リンカ ツール エラー LNK2022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メタデータの操作に失敗しました。\(HRESULT\)\) : error\_message  
  
 メタデータのマージ中にエラーが見つかりました。  正常にリンクするには、メタデータのエラーを解決する必要があります。  
  
 この問題を診断するには、オブジェクト ファイルで **ildasm –tokens** を実行して、`error_message` にリストされているトークンを持つ型を検出し、それらの違いを調べる方法があります。メタデータには、LayoutType 属性だけが異なる場合でも、同じ名前で異なる型が 2 つあるのは無効です。  
  
 LNK2022 エラーが発生するのは、同じ名前でも定義が矛盾している構造体などの型が複数のコンパイル単位にあるときに、[\/clr](../../build/reference/clr-common-language-runtime-compilation.md) を指定してコンパイルした場合などです。この場合、型の定義がすべてのコンパイル単位で同じであることを確認します。型名の一覧は `error_message` にあります。  
  
 LNK2022 の原因として他に考えられるのは、\([\#using](../../preprocessor/hash-using-directive-cpp.md) を使用して\) コンパイラに指定された以外の場所で、リンカーがメタデータ ファイルを検出した場合です。  これが、コンパイラに渡したときのリンカーに渡された場合、メタデータ ファイルが同じ場所に \(.dll または .netmodule\) が付属していることを確認します。  
  
 ATL アプリケーションをビルドするときに、[\_ATL\_MIXED](../Topic/_ATL_MIXED.md) を少なくとも 1 つのコンパイル単位で使用する場合は、それをすべてのコンパイル単位で使用する必要があります。  
  
## 使用例  
 次の例は、空の型を定義します。  
  
```  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## 使用例  
 この例は、名前が同じで定義が異なる型を含む 2 つのソース コード ファイルをリンクできないことを示します。  
  
 次の例では LNK2022 エラーが生成されます。  
  
```  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```
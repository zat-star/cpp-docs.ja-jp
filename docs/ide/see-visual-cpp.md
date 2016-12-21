---
title: "&lt;see&gt; (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<see>"
  - "see"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<see> C++ XML タグ"
  - "see C++ XML タグ"
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;see&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<see\> タグを使用すると、テキスト内でリンクを指定できます。  示すテキストに [\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20C++\).md) を使用します。バッチ処理することを確認またはで表示する場合があります。  
  
## 構文  
  
```  
<see cref="member"/>  
```  
  
#### パラメーター  
 `member`  
 現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。  単一引用符で囲みます。  
  
 コンパイラは、指定されたコード要素が出力 XML 内の要素名に渡します。は、`member` を解決することを確認します。  コンパイラは `member`を検索警告が発行されます。  
  
## 解説  
 コンパイル時に [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定してドキュメント コメントをファイルに出力します。  
  
 \<see\>使用例については [\<summary\>](../ide/summary-visual-cpp.md) を参照してください。  
  
 Visual C\+\+ コンパイラでは、ドキュメント コメントで 1 回のパスの cref 参照の解決を試みます。  したがって、C\+\+ のルックアップ規則を使用して、シンボルがコンパイラによって参照がある未解決です。  詳細については、「[\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20C++\).md)」を参照してください。  
  
## 使用例  
 次の例では、コンパイラは参照の解決は、ジェネリック型への cref 参照のできるかこのようなに示します。  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## 参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
---
title: "&lt;exception&gt; (Visual C++) | Microsoft Docs"
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
  - "exception"
  - "<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<exception> C++ XML タグ"
  - "exception C++ XML タグ"
ms.assetid: 24451e79-9b89-4b77-98fb-702c6516b818
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;exception&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<exception\> タグを使用すると、スローできる例外を指定できます。  このタグは、メソッド定義に適用されます。  
  
## 構文  
  
```  
<exception cref="member">description</exception>  
```  
  
#### パラメーター  
 `member`  
 現在のコンパイル環境から利用可能な例外への参照。  名前のルックアップ規則を使用して、コンパイラは特定の例外があるチェックし、出力先 XML 内で標準要素名に `member` をに変換します。  コンパイラは `member`を検索警告が発行されます。  
  
 単一引用符で囲みます。  
  
 ジェネリック型への cref 参照の作成方法については、「[\<see\>](../ide/see-visual-cpp.md)」を参照してください。  
  
 `description`  
 説明。  
  
## 解説  
 コンパイル時に [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定してドキュメント コメントをファイルに出力します。  
  
 Visual C\+\+ コンパイラでは、ドキュメント コメントで 1 回のパスの cref 参照の解決を試みます。  したがって、C\+\+ のルックアップ規則を使用して、シンボルがコンパイラによって参照がある未解決です。  詳細については、「[\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20C++\).md)」を参照してください。  
  
## 使用例  
  
```  
// xml_exception_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_exception_tag.dll  
using namespace System;  
  
/// Text for class EClass.  
public ref class EClass : public Exception {  
   // class definition ...  
};  
  
/// <exception cref="System.Exception">Thrown when... .</exception>  
public ref class TestClass {  
   void Test() {  
      try {  
      }  
      catch(EClass^) {  
      }  
   }  
};  
```  
  
## 参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
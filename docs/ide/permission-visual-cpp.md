---
title: "&lt;permission&gt; (Visual C++) | Microsoft Docs"
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
  - "permission"
  - "<permission>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<permission> C++ XML タグ"
  - "permission C++ XML タグ"
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;permission&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<permission\> タグを使用すると、メンバーへのアクセスをドキュメントにできます。  <xref:System.Security.PermissionSet> はメンバーへのアクセスを指定できるようにします。  
  
## 構文  
  
```  
<permission cref="member">description</permission>  
```  
  
#### パラメーター  
 `member`  
 現在のコンパイル環境からの呼び出しに利用できる、メンバーまたはフィールドへの参照。  コンパイラは、指定されたコード要素が存在するかどうかを確認し、`member` を出力先 XML 内で標準要素名に変換します。  単一引用符で囲みます。  
  
 コンパイラは `member`を検索警告が発行されます。  
  
 ジェネリック型への cref 参照の作成方法については、「[\<see\>](../ide/see-visual-cpp.md)」を参照してください。  
  
 `description`  
 メンバーへのアクセスの説明。  
  
## 解説  
 コンパイル時に [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定してドキュメント コメントをファイルに出力します。  
  
 Visual C\+\+ コンパイラでは、ドキュメント コメントで 1 回のパスの cref 参照の解決を試みます。  したがって、C\+\+ のルックアップ規則を使用して、シンボルがコンパイラによって参照がある未解決です。  詳細については、「[\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20C++\).md)」を参照してください。  
  
## 使用例  
  
```  
// xml_permission_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_permission_tag.dll  
using namespace System;  
/// Text for class TestClass.  
public ref class TestClass {  
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>  
   void Test() {}  
};  
```  
  
## 参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
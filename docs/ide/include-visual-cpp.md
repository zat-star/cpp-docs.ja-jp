---
title: "&lt;include&gt; (Visual C++) | Microsoft Docs"
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
  - "include"
  - "<include>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<include> C++ XML タグ"
  - "include C++ XML タグ"
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;include&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<include\> タグを使用すると、ソース コード内の型およびメンバーの説明として、別のファイル内のコメントを参照できます。  これはソース コードのファイルにドキュメント コメントを直接記述しない方法です。  たとえば、チームが企業全体で使用される標準の「定型」というコメントを挿入するために \<include\> を使用できます。  
  
## 構文  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### パラメーター  
 `filename`  
 ドキュメントを含むファイルの名前。  ファイル名にパスを指定することもできます。  単一引用符で囲みます。  コンパイラは `filename`を検索警告が発行されます。  
  
 `tagpath`  
 目的のノード セットを選択する有効な XPath 式はファイルに含まれています。  
  
 `name`  
 タグの名前指定子。その後ろにコメントを指定します。`name` には `id` を指定します。  
  
 `id`  
 タグの ID。その後ろにコメントを指定します。  単一引用符で囲みます。  
  
## 解説  
 \<include\> タグは、XML の XPath 構文を使用します。  \<include\>を使用してカスタマイズ方法については、XPath ドキュメントを参照してください。  
  
 コンパイル時に [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定してドキュメント コメントをファイルに出力します。  
  
## 使用例  
 複数ファイルの例を次に示します。  \<include\>を使用する最初のファイルは次のドキュメント コメントが含まれています:  
  
```  
// xml_include_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_include_tag.dll  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />  
public ref class Test {  
   void TestMethod() {  
   }  
};  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />  
public ref class Test2 {  
   void Test() {  
   }  
};  
```  
  
 2 番目のファイル xml\_include\_tag.doc には、次のドキュメント コメントが記述されています。  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## プログラムの出力  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>t2</name>  
    </assembly>  
    <members>  
        <member name="T:Test">  
            <summary>  
The summary for this type.  
</summary>  
        </member>  
        <member name="T:Test2">  
            <summary>  
The summary for this other type.  
</summary>  
        </member>  
    </members>  
</doc>  
```  
  
## 参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
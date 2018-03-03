---
title: "&lt;含める&gt;(Visual C) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- include
- <include>
dev_langs:
- C++
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9a6b07ce540d67a44e46a24fb943dac93bb95a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ltincludegt-visual-c"></a>&lt;含める&gt;(Visual C)
\<include> タグを使用して、ソース コード内の型とメンバーを記述する別のファイル内のコメントを参照することができます。 これは文書化のコメントをソース コード ファイル内に直接配置する方法の代替です。  たとえば、使用することができます\<含める > は、チームや会社で使用する標準的な「定型」コメントを挿入しますします。  
  
## <a name="syntax"></a>構文  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### <a name="parameters"></a>パラメーター  
 `filename`  
 ドキュメントを含むファイルの名前。 ファイル名をパスで修飾することができます。  名前は、一重引用符または二重引用符で囲みます。  コンパイラは、`filename` が見つからない場合に警告を発行します。  
  
 `tagpath`  
 ファイルに含まれている必要なノード セットを選択する有効な XPath 式です。  
  
 `name`  
 コメントの前に配置するタグの名前指定子。`name` には `id` が指定されます。  
  
 `id`  
 コメントの前に配置するタグの ID。  名前は、一重引用符または二重引用符で囲みます。  
  
## <a name="remarks"></a>コメント  
 \<include> タグは XML XPath 構文を使用します。 使用してカスタマイズする方法については、XPath に関するドキュメントを参照してください\<含める >。  
  
 コンパイル時に [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定して、ドキュメント コメントをファイルに出力します。  
  
## <a name="example"></a>例  
 これは、複数ファイルの例です。 最初のファイルを使用して\<含める >、次のドキュメントのコメントが含まれています。  
  
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
  
 2 番目のファイル xml_include_tag.doc には、次のドキュメントのコメントが含まれています。  
  
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
  
## <a name="program-output"></a>プログラムの出力  
  
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
  
## <a name="see-also"></a>参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
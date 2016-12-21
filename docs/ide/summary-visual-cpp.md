---
title: "&lt;summary&gt; (Visual C++) | Microsoft Docs"
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
  - "<summary>"
  - "summary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<summary> C++ XML タグ"
  - "summary C++ XML タグ"
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;summary&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<summary\> タグは、型または型のメンバーの説明に使用します。  型の説明に補足情報を追加するには、[\<remarks\>](../ide/remarks-visual-cpp.md) タグを使用します。  
  
## 構文  
  
```  
<summary>description</summary>  
```  
  
#### パラメーター  
 `description`  
 オブジェクトの要約。  
  
## 解説  
 \<summary\> のタグのテキストは、IntelliSense の型に関する唯一の情報源で、[&#91;オブジェクト ブラウザー&#93;](http://msdn.microsoft.com/ja-jp/f89acfc5-1152-413d-9f56-3dc16e3f0470)、コード コメント Web レポートで表示されます。  
  
 コンパイル時に [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定してドキュメント コメントをファイルに出力します。  
  
## 使用例  
  
```  
// xml_summary_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_summary_tag.dll  
  
/// Text for class MyClass.  
public ref class MyClass {  
public:  
   /// <summary>MyMethod is a method in the MyClass class.  
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>  
   /// <seealso cref="MyClass::MyMethod2"/>  
   /// </summary>  
   void MyMethod(int Int1) {}  
  
   /// text  
   void MyMethod2() {}  
};  
```  
  
## 参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
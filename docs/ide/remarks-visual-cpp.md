---
title: "&lt;remarks&gt; (Visual C++) | Microsoft Docs"
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
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "<remarks> C++ XML タグ"
  - "remarks C++ XML タグ"
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &lt;remarks&gt; (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\<remarks\> タグを使用して、型の情報を追加し、[\<summary\>](../ide/summary-visual-cpp.md) で指定された情報を補足します。  この情報は [&#91;オブジェクト ブラウザー&#93;](http://msdn.microsoft.com/ja-jp/f89acfc5-1152-413d-9f56-3dc16e3f0470)、コード コメント Web レポートで表示されます。  
  
## 構文  
  
```  
<remarks>description</remarks>  
```  
  
#### パラメーター  
 `description`  
 メンバーの説明。  
  
## 解説  
 コンパイル時に [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) を指定してドキュメント コメントをファイルに出力します。  
  
## 使用例  
  
```  
// xml_remarks_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_remarks_tag.dll  
  
using namespace System;  
  
/// <summary>  
/// You may have some primary information about this class.  
/// </summary>  
/// <remarks>  
/// You may have some additional information about this class.  
/// </remarks>  
public ref class MyClass {};  
```  
  
## 参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)
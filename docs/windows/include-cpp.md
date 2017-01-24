---
title: "include (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.include"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "include attribute"
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# include (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

生成された .idl ファイルに含める一つ以上のヘッダー ファイルを指定します。  
  
## 構文  
  
```  
  
      [ include(  
   header_file  
) ];  
```  
  
#### パラメーター  
 *header\_file*  
 生成された .idl ファイルのインクルードするファイルの名前。  
  
## 解説  
 **必要**  C\+\+ 属性は生成された .idl ファイルで `#include` のステートメントを `import "docobj.idl"` のステートメントの下に配置します。  
  
 **必要**  C\+\+ 属性に [必要](http://msdn.microsoft.com/library/windows/desktop/aa367052) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 次のコード例ではを  **必要**  を使用する方法を示しています。  この例ではinclude.h はファイルの \#include ステートメントが含まれています。  
  
```  
// cpp_attr_ref_include.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[include(cpp_attr_ref_include.h)];  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
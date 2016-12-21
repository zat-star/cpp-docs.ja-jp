---
title: "includelib (C++) | Microsoft Docs"
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
  - "vc-attr.includelib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "includelib attribute"
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# includelib (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

生成された .idl ファイルに含める .idl ファイルまたは .h ファイルを指定します。  
  
## 構文  
  
```  
  
      [ includelib(  
   name.idl  
) ];  
```  
  
#### パラメーター  
 *name.idl*  
 生成された .idl ファイルの一部としてインクルードする .idl ファイルの名前。  
  
## 解説  
 `includelib` C\+\+ 属性により `importlib` のステートメントの後に生成された .idl ファイルに含める.idl ファイルまたは .h ファイルが発生します。  
  
## 使用例  
 次のコードは.cpp ファイルに表示されます :  
  
```  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意|  
|**複数回の適用**|○|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [include](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
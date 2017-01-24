---
title: "importidl | Microsoft Docs"
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
  - "vc-attr.importidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "importidl attribute"
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# importidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

生成された .idl ファイルに指定の .idl ファイルに挿入します。  
  
## 構文  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### パラメーター  
 `idl_file`  
 独自のアプリケーション用に生成される .idl ファイルとマージする .idl ファイルの名前を指定します。  
  
## 解説  
 **importidl** C\+\+ 属性はプログラムで生成された .idl ファイルにライブラリ ブロックの外部セクション `idl_file`\(\) とプログラムで生成された .idl ファイルのライブラリのセクションにライブラリのセクション \(\) `idl_file` します。  
  
 生成された .idl ファイルを使用して渡します。コード化された .idl ファイルを使用する場合は**importidl** を操作することもできます。  
  
## 使用例  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [import](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
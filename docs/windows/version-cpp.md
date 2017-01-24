---
title: "version (C++) | Microsoft Docs"
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
  - "vc-attr.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version attribute"
  - "version information, version attribute"
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# version (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラスの複数のバージョンでの特定のバージョンを指定します。  
  
## 構文  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### パラメーター  
 *バージョン*  
 コクラスのバージョン番号。  指定しない場合1.0 は .idl ファイル内に配置されます。  
  
## 解説  
 **バージョン**  C\+\+ 属性に [バージョン](http://msdn.microsoft.com/library/windows/desktop/aa367306) の MIDL の属性と同じ機能を持ちますが生成された .idl ファイルに渡されます。  
  
## 使用例  
 **バージョン**  の使用例については [bindable](../windows/bindable.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|**コクラス**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
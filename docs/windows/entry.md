---
title: "entry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.entry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "entry attribute"
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# entry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL のエントリ ポイントを指定してモジュール内のエクスポート関数または定数を指定します。  
  
## 構文  
  
```  
  
      [ entry(  
   id  
) ]  
```  
  
#### パラメーター  
 `id`  
 エントリ ポイントの ID。  
  
## 解説  
 **エントリ**  C\+\+ 属性に [エントリ](http://msdn.microsoft.com/library/windows/desktop/aa366815) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 **エントリ**  の例では[idl\_module](../windows/idl-module.md) の例を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|`idl_module` 属性|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
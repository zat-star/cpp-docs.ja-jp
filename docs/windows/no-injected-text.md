---
title: "no_injected_text | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.no_injected_text"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_injected_text attribute"
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# no_injected_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンパイラで属性を使用した結果としてコードを挿入できません。  
  
## 構文  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### パラメーター  
 `boolean`\(省略可能\)  
 挿入されたコードを使用しない場合は **true** 挿入したコードが実行 **False**。  **true** が既定値です。  
  
## 解説  
 **no\_injected\_text** C\+\+ 属性の最も一般的な用途は.mrg ファイルに **no\_injected\_text** の属性を挿入 [\/Fx](../build/reference/fx-merge-injected-code.md) コンパイラ オプションを使用します。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
---
title: "library_block | Microsoft Docs"
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
  - "vc-attr.library_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "library_block attribute"
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# library_block
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IDL ライブラリ ブロック内の構造を配置します。  
  
## 構文  
  
```  
  
[library_block]  
  
```  
  
## 解説  
 ライブラリ ブロック内の構造を配置した場合参照されるかどうかをタイプ ライブラリに渡されることをに関係なく確認します。  既定では[コクラス](../windows/coclass.md)[ディスパッチインターフェイス](../windows/dispinterface.md) と [idl\_module](../windows/idl-module.md) の属性で修飾されている構造体だけライブラリ ブロックに配置されます。  
  
## 使用例  
 次のコードではカスタム インターフェイスはライブラリ ブロック内に配置されます。  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト。](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
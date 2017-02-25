---
title: "helpstringdll | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpstringdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpstringdll attribute [C++]"
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# helpstringdll
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL の名前を文書内の文字列の参照 \(ローカリゼーション\) を実行するように指定します。  
  
## 構文  
  
```  
  
      [ helpstringdll(  
   "string"  
) ]  
```  
  
#### パラメーター  
 `string`  
 ドキュメントの文字列参照を使用する DLL。  
  
## 解説  
 **helpstringdll** C\+\+ 属性に [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) の MIDL の属性と同じ機能があります。  
  
## 使用例  
  
```  
// cpp_attr_ref_helpstringdll.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib", helpstringdll="xx.dll")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI   
{  
   HRESULT xxx();  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `interface` のインターフェイス メソッド|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
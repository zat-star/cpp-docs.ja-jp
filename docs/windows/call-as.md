---
title: "call_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.call_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call_as attribute"
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# call_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リモート関数が呼び出されるとローカル関数が呼び出されるようにリモート関数にマップする方法 [ローカル](../windows/local-cpp.md) の関数を有効にします。  
  
## 構文  
  
```  
  
      [ call_as(  
   function  
) ]  
```  
  
#### パラメーター  
 *機能性*  
 リモート関数が呼び出されたときに呼び出しの対象とするローカル関数。  
  
## 解説  
 **call\_as\(A\)** C\+\+ 属性に [call\_as\(A\)](http://msdn.microsoft.com/library/windows/desktop/aa366748) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 リモート処理可能関数 \(\)**Remf1** リモート **f1** に関数 \(\) をマップする方法に **call\_as\(A\)** を使用する方法を次のコード例に示します :  
  
```  
// cpp_attr_ref_call_as.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMInterface {  
   [local] HRESULT f1 ( int i );  
   [call_as(f1)] HRESULT Remf1 ( int i );   
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス メソッド|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [local](../windows/local-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
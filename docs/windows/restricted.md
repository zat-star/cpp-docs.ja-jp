---
title: "restricted | Microsoft Docs"
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
  - "vc-attr.restricted"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "restricted attribute"
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# restricted
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

モジュールインターフェイスまたはディスパッチ インターフェイスのメンバーを任意に呼び出すことができないことを指定します。  
  
## 構文  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### パラメーター  
 `interfaces`  
 COM オブジェクトからランダムに呼び出すことができる一つ以上のインターフェイス。  このパラメーターはクラスに適用された場合のみ有効です。  
  
## 解説  
 **restricted** C\+\+ 属性に [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) の MIDL の属性と同じ機能があります。  
  
## 使用例  
 次のコードは **restricted** 属性の使用方法を示します :  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|インターフェイス メソッド`interface` **クラス** `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|\( **クラス**  または `struct` に適用される場合\) **コクラス**|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
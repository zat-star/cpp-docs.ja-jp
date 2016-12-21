---
title: "registration_script | Microsoft Docs"
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
  - "vc-attr.registration_script"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registration_script attribute"
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# registration_script
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したカスタム登録スクリプトを実行します。  
  
## 構文  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### パラメーター  
 *script*  
 カスタム登録スクリプト \(.rgs\) ファイルへの完全パス。  **None** の値は`script = "none"` などコクラスに登録の要件がないことを示します。  
  
## 解説  
 **registration\_script** C\+\+ 属性は  **スクリプト**  で指定されたカスタム登録スクリプトを実行します。  この属性を指定しない場合標準 .rgs ファイル \(コンポーネントを登録するための情報を含む\) を使用します。  .rgs ファイルの詳細については[ATL レジストリ コンポーネント \(レジストラー\)](../atl/atl-registry-component-registrar.md) を参照してください。  
  
 この属性は [コクラス](../windows/coclass.md)[ProgID](../Topic/progid.md)または [vi\_progid](../windows/vi-progid.md) の属性 \(そのうちの 1 つを意味する属性を適用することを同じ要素に必要です。  
  
## 使用例  
 次のコードではコンポーネントが cpp\_attr\_ref\_registration\_script.rgs というレジストリ スクリプトがあることを指定します。  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|次の一つ以上 :  **コクラス ProgID**または **vi\_progid**。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
---
title: "requires_category | Microsoft Docs"
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
  - "vc-attr.requires_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "requires_category attribute"
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# requires_category
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ターゲット クラスの必須コンポーネントのカテゴリを指定します。  
  
## 構文  
  
```  
  
     [ requires_category(   
  requires_category  
) ]  
```  
  
#### パラメーター  
 *requires\_category*  
 必要なカテゴリ ID。  
  
## 解説  
 **requires\_category** C\+\+ 属性はクラスに必要なコンポーネント カテゴリを指定します。  詳細については[REQUIRED\_CATEGORY](../Topic/REQUIRED_CATEGORY.md) を参照してください。  
  
 この属性は [コクラス](../windows/coclass.md)[ProgID](../Topic/progid.md)または [vi\_progid](../windows/vi-progid.md) の属性 \(そのうちの 1 つを意味する属性を適用することを同じ要素に必要です。  
  
## 使用例  
 次のコードはオブジェクトの実装をコントロールのカテゴリ必要です。  
  
```  
// cpp_attr_ref_requires_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLibrary")];  
  
[ coclass, requires_category("CATID_Control"),  
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]  
class CMyClass {};  
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
 [implements\_category](../Topic/implements_category.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
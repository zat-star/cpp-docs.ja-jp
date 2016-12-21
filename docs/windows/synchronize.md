---
title: "synchronize | Microsoft Docs"
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
  - "vc-attr.synchronize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "synchronize attribute"
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# synchronize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ターゲット メソッドへのアクセスを同期します。  
  
## 構文  
  
```  
  
[synchronize]  
  
```  
  
## 解説  
 ターゲット オブジェクトのメソッドを同期する  **同期**  C\+\+ 属性の実装をサポートします。  同期は複数のオブジェクトをターゲット メソッドのアクセスを制御することにより共通リソース \(クラスのメソッドなど\) を使用できるようになります。  
  
 この属性によって挿入されるコードは対象メソッドの先頭に `Lock` の適切なメソッド \(スレッド モデルによって決まります\) が呼び出されます。  メソッドが終了すると`Unlock` は自動的に呼び出されます。  これらの関数の詳細については[CComAutoThreadModule:: ロック](../Topic/CComAutoThreadModule::Lock.md) を参照してください。  
  
 この属性は [コクラス](../windows/coclass.md)[ProgID](../Topic/progid.md)または [vi\_progid](../windows/vi-progid.md) の属性 \(そのうちの 1 つを意味する属性を適用することを同じ要素に必要です。  の一つの属性が使用されそのほかの 2 つが自動的に適用されます。  たとえば**ProgID** が適用されている場合**vi\_progid** と  **コクラス**  も適用されます。  
  
## 使用例  
 次のコードは `CMyClass` のオブジェクトの `UpdateBalance` のメソッドの同期を提供します。  
  
```  
// cpp_attr_ref_synchronize.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="SYNC")];  
  
[coclass,  
 threading(both),  
 vi_progid("MyProject.MyClass"),  
 progid("MyProject.MyClass.1"),  
 uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]  
class CMyClass {  
   float m_nBalance;  
  
   [synchronize]  
   void UpdateBalance(float nAdjust) {  
      m_nBalance += nAdjust;  
   }  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|クラスメソッドメソッド|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|次の一つ以上 :  **コクラス ProgID**または **vi\_progid**。|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
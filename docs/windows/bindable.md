---
title: "bindable | Microsoft Docs"
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
  - "vc-attr.bindable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bindable attribute"
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bindable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロパティがデータ連結をサポートすることを示します。  
  
## 構文  
  
```  
  
[bindable]  
  
```  
  
## 解説  
 **bindable** C\+\+ 属性に [bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738) の MIDL の属性と同じ機能があります。  [propget](../windows/propget.md)[propput](../windows/propput.md)または [propputref](../windows/propputref.md) の属性で定義されるプロパティで使用したり手動でバインドできるメソッドを定義できます。  
  
 次の例では **bindable**MFC の使用方法を示します :  
  
-   [コントロールのサンプル : MFC ベースの ActiveX コントロール](http://msdn.microsoft.com/ja-jp/a44adf86-0ba0-4504-bedb-512b6cba2e63)  
  
-   [CIRC サンプル : ActiveX コントロール](http://msdn.microsoft.com/ja-jp/9ba34d04-280e-49f4-90ae-41a6be44c95b)  
  
-   [TESTHELP サンプル : ツール ヒントとヘルプを持つ ActiveX コントロール](http://msdn.microsoft.com/ja-jp/d822861d-c6f0-4d0a-ad11-970eebb1e8cd)  
  
## 使用例  
 次のコードはプロパティの **bindable** の使用方法を示します :  
  
```  
// cpp_attr_ref_bindable.cpp  
// compile with: /LD  
#include <windows.h>  
[  
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"),  
   dispinterface,  
   helpstring("property demo Interface")  
]  
__interface IPropDemo : IDispatch {  
  
   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);  
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);  
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);  
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);     
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();  
};  
  
[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];  
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
 [defaultbind](../windows/defaultbind.md)   
 [displaybind](../windows/displaybind.md)   
 [immediatebind](../windows/immediatebind.md)   
 [requestedit](../windows/requestedit.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)
---
title: "コンパイラ エラー C3707 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3707"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3707"
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3707
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : ディスパッチ インターフェイスは dispid を必要とします。  
  
 `dispinterface` メソッドを使用する場合は、そのメソッドに `dispid` を割り当てる必要があります。  このエラーを解決するには、`dispinterface` メソッドに `dispid` を割り当てます。たとえば、以下のサンプルでは、メソッドの `id` 属性のコメント化を解除しています。  詳細については、「[dispinterface](../../windows/dispinterface.md)」および「[id](../../windows/id.md)」を参照してください。  
  
 次の例では警告 C3707 が生成されます。  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```
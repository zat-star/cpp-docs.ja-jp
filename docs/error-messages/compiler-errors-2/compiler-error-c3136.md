---
title: "コンパイラ エラー C3136 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3136"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3136"
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3136
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : COM インターフェイスは他の COM インターフェイスからのみ継承できます、'interface' は COM インターフェイスではありません。  
  
 [インターフェイス属性](../../windows/interface-attributes.md)が適用されたインターフェイスは、COM インターフェイス以外のインターフェイスから継承されます。  最終的に、COM インターフェイスは `IUnknown` から継承されます。  先頭にインターフェイス属性が付くインターフェイスは、すべて COM インターフェイスです。  
  
 次のコードは C3136 を生成します。  
  
```  
// C3136.cpp  
#include "unknwn.h"  
  
__interface A   // C3136  
// try the following line instead  
// _interface A : IUnknown  
{  
   int a();  
};  
  
[object]  
__interface B : A  
{  
   int aa();  
};  
```
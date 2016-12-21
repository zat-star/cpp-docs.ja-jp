---
title: "コンパイラの警告 (レベル 1) C4581 | Microsoft Docs"
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
  - "C4581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4581"
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

使用できない動作: 属性を処理するために、'"string1"' を 'string2' で置き換えました  
  
 このエラーは、Visual C\+\+ 属性のパラメーター チェックを行う Visual C\+\+ 2005 で行ったコンパイラ準拠作業の結果として生成されることがあります。  
  
 以前のバージョンでは、引用符で囲まれている属性値も囲まれていない属性値も受け入れられていました。  値が列挙体の場合は、引用符で囲まないでください。  
  
## 使用例  
 次の例では C4581 エラーが生成されます。  
  
```  
// C4581.cpp  
// compile with: /c /W1  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {};  
  
[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581  
// try the following line instead  
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]  
class CSample : public IMyI {};  
```
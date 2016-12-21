---
title: "コンパイラの警告 (レベル 1) C4917 | Microsoft Docs"
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
  - "C4917"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4917"
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4917
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declarator' : GUID はクラス、インターフェイスまたは名前空間のみに関連付けることができます。  
  
 [class](../../cpp/class-cpp.md)、[interface](../Topic/__interface.md)、または [namespace](../Topic/namespace%20Declaration.md) 以外のユーザー定義の構造体には、GUID を関連付けることができません。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では、C4917 警告が生成されます。  
  
```  
// C4917.cpp  
// compile with: /W1  
#pragma warning(default : 4917)  
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S  
{  
} s;   // C4917, don't put uuid on a struct  
  
int main()  
{  
}  
```
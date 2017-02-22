---
title: "致命的なエラー C1191 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1191"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1191"
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 致命的なエラー C1191
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'dll' はグローバル スコープでのみインポートできます。  
  
 \/clr プログラミングを使用するプログラムに mscorlib.dll をインポートするための命令は、名前空間や関数には使用できません。グローバル スコープで使用する必要があります。  
  
 次の例では警告 C1191 が生成されます。  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 解決方法 :  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```
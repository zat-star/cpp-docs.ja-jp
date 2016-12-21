---
title: "2.6.3 barrier Directive | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.3 barrier Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**バリア**  のディレクティブはチームでスレッドを同期します。  検出されていない場合チームの各スレッドが他にこのポイントに到達するまで待機します。   **バリア**  のディレクティブの構文は次のとおりです :  
  
```  
#pragma omp barrier new-line  
```  
  
 チームでスレッドがバリアにヒットした後チームの各スレッドはそのディレクティブの後のステートメントを並列実行します。   **バリア**  のディレクティブの構文の一部として C. 言語のステートメントがないためプログラム内の配置にも制限があることに注意してください。  正式な文法については [付録 C](../Topic/C.%20OpenMP%20C%20and%20C++%20Grammar.md) を参照してください。  例ではこれらの制限を示します。  
  
```  
/* ERROR - The barrier directive cannot be the immediate  
*          substatement of an if statement  
*/  
if (x!=0)  
   #pragma omp barrier  
...  
  
/* OK - The barrier directive is enclosed in a  
*      compound statement.  
*/  
if (x!=0) {  
   #pragma omp barrier  
}  
```
---
title: "コンパイラ エラー C2708 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2708"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2708"
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2708
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 実引数のバイト数が前回の呼び出しまたは参照時と異なっています。  
  
 [\_\_stdcall](../../cpp/stdcall.md) 関数の前にはプロトタイプを置く必要があります。  コンパイラでは、\_stdcall 関数の前にプロトタイプがない場合、関数の最初の呼び出しがプロトタイプとして解釈されます。これに一致しない呼び出しが検出されたときに、このエラーが生成されます。  
  
 このエラーを解決するには、関数にプロトタイプを追加してください。
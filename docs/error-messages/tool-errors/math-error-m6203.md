---
title: "数値演算エラー M6203 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6203"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6203"
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 数値演算エラー M6203
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : \_OVERFLOW エラー  
  
 指定された関数の結果が大きすぎて表現できません。  
  
 このエラーが発生すると、関数 `_matherr` が呼び出され、関数名、引数、エラー タイプが渡されます。  関数 `_matherr` を書き直すことによって、実行時浮動小数点数値演算エラーの処理をカスタマイズできる場合もあります。
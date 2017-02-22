---
title: "数値演算エラー M6202 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6202"
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 数値演算エラー M6202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : \_SING エラー  
  
 指定された関数の引数の値が不適切です。  渡された値はこの関数では定義されていません。  
  
 このエラーが発生すると、関数 `_matherr` が呼び出され、関数名、引数、エラー タイプが渡されます。  関数 `_matherr` を書き直すことによって、実行時浮動小数点数値演算エラーの処理をカスタマイズできる場合もあります。
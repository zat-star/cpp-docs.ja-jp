---
title: "メイクファイルの特殊文字 | Microsoft Docs"
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
helpviewer_keywords: 
  - "マクロ, 特殊文字"
  - "メイクファイル, 特殊文字"
  - "NMAKE プログラム, 特殊文字"
  - "特殊文字, NMAKE マクロで"
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# メイクファイルの特殊文字
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE の特殊文字をリテラル文字として使用するには、その文字の前にカレット \(^\) を付けます。  NMAKE は、ほかの文字に先行するカレットは無視します。  特殊文字は次のとおりです。  
  
 `:  ;  #  (  )  $  ^  \  {  }  !  @  —`  
  
 二重引用符で囲まれた文字列内のカレット \(^\) は、リテラルのカレット文字として扱われます。  行末にカレットを置くと、文字列またはマクロではリテラルの改行文字が挿入されます。  
  
 マクロでは、改行文字が後続する円記号 \(\\\) は空白で置換されます。  
  
 コマンドでは、パーセント記号 \(%\) はファイル指定子です。  コマンドで % をリテラルで表すには、2 つのパーセント記号 \(%%\) を指定します。  コマンドではない場合は 1 つの % がリテラルとして解釈されますが、%% は常に 1 つの % として解釈されます。  したがって、%% をリテラルで表すには、3 つのパーセント記号 \(%%%\) または 4 つのパーセント記号 \(%%%%\) を指定します。  
  
 コマンドでドル記号 \($\) をリテラル文字として使用するには、2 つのドル記号 \($$\) を指定します。  この方法は、^$ が有効なほかの状況でも使用できます。  
  
## 参照  
 [メイクファイルの内容](../build/contents-of-a-makefile.md)
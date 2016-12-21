---
title: "ターゲット | Microsoft Docs"
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
  - "ターゲット, 指定 (NMAKE で)"
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ターゲット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

依存関係行では、有効なファイル名、ディレクトリ名、または[疑似ターゲット](../build/pseudotargets.md)を使用して 1 つ以上のターゲットを指定します。  複数のターゲットは、空白またはタブで区切ります。  ターゲットの表記では、大文字と小文字が区別されません。  ファイル名には、パスを指定できます。  ターゲット名に使用できるのは 256 文字までです。  コロンの前のターゲットが 1 文字である場合は、間に空白を入れて区切ります。空白で区切らないと、NMAKE は文字とコロンの組み合わせをドライブ指定子として解釈します。  
  
## さらに詳しくは次のトピックをクリックしてください  
 [疑似ターゲット](../build/pseudotargets.md)  
  
 [複数のターゲット](../build/multiple-targets.md)  
  
 [依存関係の追加](../build/cumulative-dependencies.md)  
  
 [複数の記述ブロックのターゲット](../build/targets-in-multiple-description-blocks.md)  
  
 [依存関係の副作用](../build/dependency-side-effects.md)  
  
## 参照  
 [記述ブロック](../build/description-blocks.md)
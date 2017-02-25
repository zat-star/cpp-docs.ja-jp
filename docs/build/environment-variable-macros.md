---
title: "環境変数マクロ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "環境変数, マクロ (NMAKE の)"
  - "マクロ, 環境変数"
  - "NMAKE プログラム, 環境変数マクロ"
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 環境変数マクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE は、セッションの開始前に存在する環境変数のマクロ定義を継承します。  変数がオペレーティング システムの環境で設定された場合、その変数は NMAKE マクロとして利用できます。  継承された名前は、大文字に変換されます。  継承は、プリプロセスの前に行われます。  \/E オプションを使用すると、環境変数から継承されたマクロが、メイクファイルで同じ名前を持つマクロよりも優先されます。  
  
 環境変数マクロはセッションで再定義できます。再定義すると、対応する環境変数が変更されます。  環境変数は、SET コマンドで変更することもできます。  ただし、SET コマンドを使用してセッションで環境変数を変更しても、対応するマクロは変更されません。  
  
 たとえば、次のようになります。  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 この例では、`PATH` を変更することで、対応する環境変数 `PATH` が変更されます。この変更では、パスに `\nonesuch` が追加されます。  
  
 メイクファイルでは構文的に正しくない文字列として環境変数が定義されている場合、マクロは作成されず、警告も生成されません。  変数の値にドル記号 \($\) が含まれている場合、NMAKE はそのドル記号がマクロ呼び出しの開始であると解釈します。  そのマクロを使用すると、予測不可能な動作が発生することがあります。  
  
## 参照  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)
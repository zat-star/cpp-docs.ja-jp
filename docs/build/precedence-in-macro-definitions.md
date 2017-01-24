---
title: "マクロ定義の優先順位 | Microsoft Docs"
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
  - "マクロ, 優先順位"
  - "NMAKE プログラム, 優先順位 (マクロ定義の)"
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# マクロ定義の優先順位
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マクロに複数の定義がある場合、NMAKE は優先順位の最も高い定義を使用します。  優先順位の高いものから順番に示すと、次のようになります。  
  
1.  コマンド ラインで定義されているマクロ  
  
2.  メイクファイルまたはインクルード ファイルで定義されているマクロ  
  
3.  継承された環境変数マクロ  
  
4.  Tools.ini で定義されているマクロ  
  
5.  [CC](../build/command-macros-and-options-macros.md) や [AS](../build/command-macros-and-options-macros.md) などの組み込みマクロ  
  
 \/E を使用すると、環境変数から継承されたマクロが、同じ名前のメイクファイル マクロよりも優先されます。  コマンド ラインのマクロよりも優先させるには、**\!UNDEF** を使用します。  
  
## 参照  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)
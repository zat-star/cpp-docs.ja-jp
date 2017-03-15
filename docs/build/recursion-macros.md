---
title: "再帰マクロ | Microsoft Docs"
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
  - "マクロ, 再帰"
  - "NMAKE プログラム, 再帰マクロ"
  - "再帰マクロ"
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 再帰マクロ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

再帰マクロを使用すると、NMAKE を再帰的に呼び出すことができます。  再帰的なセッションでは、コマンド ライン マクロと環境変数マクロ、および Tools.ini の情報が継承されます。  メイクファイルで定義された推論規則、または **.SUFFIXES** と **.PRECIOUS** の指定は継承されません。  マクロを再帰的な NMAKE セッションに渡すには、再帰呼び出しの前に SET で環境変数を設定するか、再帰呼び出しのコマンドでマクロを定義するか、または Tools.ini でマクロを定義します。  
  
|マクロ|定義|  
|---------|--------|  
|**MAKE**|NMAKE を呼び出すために最初に使用されたコマンド。<br /><br /> $\(MAKE\) マクロは nmake.exe への完全パスを提供します。|  
|**MAKEDIR**|NMAKE が呼び出されたときの現在のディレクトリ。|  
|**MAKEFLAGS**|現在有効なオプション。  `/$(MAKEFLAGS)` のように使用します。\/F が含まれていないことに注意してください。|  
  
## 参照  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)
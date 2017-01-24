---
title: "インライン アセンブリでの C++ 関数の呼び出し | Microsoft Docs"
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
  - "__asm キーワード [C++], 呼び出し (関数を)"
  - "関数呼び出し, C++ 関数"
  - "関数呼び出し, インライン アセンブラー内"
  - "関数 [C++], インライン アセンブラー内での呼び出し"
  - "インライン アセンブラー, 呼び出し (関数を)"
  - "Visual C++, 関数"
ms.assetid: 1f0d1eb3-54cf-45d5-838d-958188616b38
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブリでの C++ 関数の呼び出し
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 `__asm` ブロックは過ぎられないグローバルな C\+\+ の関数を呼び出すことができます。  オーバーロードされた C\+\+ のグローバル関数または C.C\+\+ メンバー関数を呼び出すとコンパイラはエラーを発行します。  
  
 この関数を **extern 「 C 」 15** のリンケージで宣言して呼び出すことができます。  これは **extern 「 C 」 15** のリンケージを持つためすべての標準ヘッダー ファイルがライブラリ関数を定義するC\+\+. ではプログラム内の `__asm` ブロックが C ライブラリ関数を呼び出すことができます。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)
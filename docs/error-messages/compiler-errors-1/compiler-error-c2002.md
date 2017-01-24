---
title: "コンパイラ エラー C2002 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2002"
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ワイド文字定数の使用方法が正しくありません。  
  
 マルチバイト文字定数が無効です。  
  
### 次のような原因をチェックして問題を解決するには  
  
1.  ワイド文字定数に含まれるバイト数が多すぎます。  
  
2.  標準ヘッダー STDDEF.h がインクルードされていません。  
  
3.  ワイド文字は、通常のリテラル文字列に連結できません。  
  
4.  ワイド文字定数の前には文字 L を付ける必要があります。  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Microsoft C\+\+ の場合、プリプロセッサ ディレクティブのテキスト引数は ASCII であることが必要です。  たとえば、ディレクティブ `#pragma message(L"string")` は無効です。
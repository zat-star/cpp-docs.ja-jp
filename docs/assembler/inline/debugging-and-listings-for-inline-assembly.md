---
title: "インライン アセンブリのデバッグと一覧表示 | Microsoft Docs"
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
  - "__asm キーワード [C++], デバッグ"
  - "バグ, __asm ブロック"
  - "デバッグ [C++], インライン アセンブラー コード"
  - "インライン アセンブラー, デバッグ"
  - "インライン アセンブラー, listings"
  - "ソース レベル デバッガー"
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブリのデバッグと一覧表示
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 インライン アセンブラー コードを含むプログラムはソース レベルのデバッガーで [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) オプションでコンパイル デバッグできます。  
  
 デバッガーではブレークポイントの C や C\+\+ およびアセンブリ言語の両方を設定できます。  混在アセンブリとソースのモードを有効にするとアセンブリ コードの提供元および逆アセンブルしたフォームの両方を表示できます。  
  
 複数のアセンブリ命令を配置することに注意してください。1 行のソース言語のステートメントはデバッグに悪影響を及ぼすことがあります。  ソース行モードでは単一行を受け取らない同一の各ステートメントにブレークポイントを設定するためにデバッガーを使用できます。  同じ基本原則が `__asm` に一つの論理行に配置する C\+\+. マクロとして定義されたブロックを適用します。  
  
 [\/FAs](../../build/reference/fa-fa-listing-file.md) のコンパイラ オプションとソースの混在アセンブリ一覧を作成する場合リストはそれぞれのアセンブリ言語のソース行およびアセンブリの形式も含まれています。  マクロが一覧に配置されませんがコンパイル時に配置されます。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [\_\_asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)
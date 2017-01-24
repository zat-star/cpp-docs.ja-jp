---
title: "リソース コンパイラ エラー RC2144 | Microsoft Docs"
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
  - "RC2144"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2144"
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソース コンパイラ エラー RC2144
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

主言語 ID が数字ではありません。  
  
 主言語 ID は 16 進数の言語 ID にする必要があります。  有効な言語 ID の一覧については、「*ランタイム ライブラリ リファレンス*」の「[言語および国\/地域識別文字列](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)」を参照してください。  
  
 このエラーは、ツールを使用して、.RC ファイルにリソースを追加してから削除した場合にも発生することがあります。  この問題を解決するには、.RC ファイルをテキスト エディターで開き、使用されていないすべてのリソースを手動でクリーンアップします。
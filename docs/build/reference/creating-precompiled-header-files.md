---
title: "プリコンパイル済みヘッダー ファイルの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch ファイル, 作成"
  - "cl.exe コンパイラ, プリコンパイル (コードを)"
  - "PCH ファイル, 作成"
  - "プリコンパイル済みヘッダー ファイル, 作成"
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# プリコンパイル済みヘッダー ファイルの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft C コンパイラおよび C\+\+ コンパイラには、インライン コードなど、C コードまたは C\+\+ コードをプリコンパイルするためのオプションが用意されています。  このパフォーマンス機能を使用すると、安定したコード本体をコンパイルし、コンパイル済みのコードをファイルに格納し、以降のコンパイルでプリコンパイル済みコードと開発中のコードを組み合わせることができます。  安定したコードは再度コンパイルする必要がないため、以降のコンパイルが高速化されます。  
  
 ここでは、プリコンパイル済みヘッダーに関する次の問題について説明します。  
  
-   [ソース コードをプリコンパイルする時期](../../build/reference/when-to-precompile-source-code.md)  
  
-   [コードをプリコンパイルする 2 つの方法](../../build/reference/two-choices-for-precompiling-code.md)  
  
-   [プリコンパイル済みヘッダーの一貫性規則](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [プロジェクトでのプリコンパイル済みヘッダーの使用](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 プリコンパイル済みヘッダーに関連するコンパイラ オプションのリファレンス情報については、「[\/Y \(プリコンパイル済みヘッダー\)](../../build/reference/y-precompiled-headers.md)」を参照してください。  
  
## 参照  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)
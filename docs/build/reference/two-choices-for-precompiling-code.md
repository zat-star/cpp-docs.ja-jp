---
title: "コードをプリコンパイルする 2 つの方法 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
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
  - ".pch ファイル"
  - ".pch ファイル, プリコンパイル オプション"
  - "自動プリコンパイル"
  - "コード, プリコンパイル"
  - "コンパイル (ソース コードを), プリコンパイル"
  - "PCH ファイル"
  - "PCH ファイル, プリコンパイル オプション"
  - "プリコンパイル済みヘッダー ファイル"
  - "プリコンパイル済みヘッダー ファイル, プリコンパイル オプション"
  - "プリコンパイル (コードを)"
ms.assetid: f50ac76f-e2a2-462d-bda5-0e2ab7cccdeb
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コードをプリコンパイルする 2 つの方法
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ を使用すると、あらゆる C または C\+\+ のコードをプリコンパイルできます。つまり、ヘッダー ファイル以外のコードもプリコンパイルできます。  
  
 プリコンパイルは、いくぶん計画が必要ですが、単純なヘッダー ファイル以外のソース コードをプリコンパイルする場合は、コンパイルの速度がかなり高速化されます。  
  
 ソース ファイルに複数の共通ヘッダー ファイルが異なる順序でインクルードされている場合、またはプリコンパイルにソース コードを含める場合は、コードをプリコンパイルします。  
  
 プリコンパイル済みヘッダーのオプションは、[\/Yc \(プリコンパイル済みヘッダー ファイルの作成\)](../../build/reference/yc-create-precompiled-header-file.md) および [\/Yu \(プリコンパイル済みヘッダー ファイルの使用\)](../../build/reference/yu-use-precompiled-header-file.md) です。  プリコンパイル済みヘッダーを作成するには **\/Yc** を使用します。  **\/Yc** オプションを `hdrstop` プラグマ \(省略可能\) と併用すると、ヘッダー ファイルとソース コードの両方をプリコンパイルできます。  **\/Yu** オプションは、現在のコンパイルで既存のプリコンパイル済みヘッダーを使用する場合に使用します。  **\/Fp** を **\/Yc** オプションと **\/Yu** オプションと共に使用して、プリコンパイル済みヘッダーに別の名前を付けることができます。  
  
 **\/Yu** および **\/Yc** のコンパイラ オプションのリファレンス トピックでは、開発環境でこの機能を使用する方法について説明します。  
  
## 詳細情報  
  
-   [ソース コードをプリコンパイルする時期](../../build/reference/when-to-precompile-source-code.md)  
  
-   [プリコンパイル済みヘッダーの一貫性規則](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [プロジェクトでのプリコンパイル済みヘッダーの使用](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 プリコンパイル済みヘッダーを使用するその他の例については、MFC \(Microsoft Foundation Class\) ライブラリに同梱のサンプル プログラムをビルドするときに使用するメイクファイルを参照してください。  
  
## 参照  
 [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)
---
title: "ソース コードをプリコンパイルする時期 | Microsoft Docs"
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
  - "プリコンパイル済みヘッダー ファイル, タイミング (プリコンパイルの)"
  - "ソース コード, プリコンパイル"
ms.assetid: eb8ba193-fd87-40d3-9545-c75deabe37cb
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ソース コードをプリコンパイルする時期
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリコンパイル済みコードを開発サイクル中に使用すると、コンパイル時間を削減できます。特に、次の場合に有用です。  
  
-   常に変更の少ない大型のコード本体を使用する。  
  
-   プログラムが複数のモジュールから構成され、すべてのモジュールが標準のインクルード ファイルのセット、および同じコンパイル オプションを使用する。  この場合、すべてのインクルード ファイルを 1 つのプリコンパイル済みヘッダーにプリコンパイルできます。  
  
 最初のコンパイル、つまり、プリコンパイル済みヘッダー ファイルを作成するコンパイルでは、以降のコンパイルよりも時間がかかります。  以降のコンパイルでは、プリコンパイル済みコードをインクルードすると、さらに高速化されます。  
  
 C および C\+\+ のどちらのプログラムもプリコンパイル可能です。  C\+\+ プログラミングでは、通常、クラス インターフェイス情報を別個にヘッダー ファイルに挿入します。  これらのヘッダー ファイルは、後でそのクラスを使用するプログラムにインクルードできます。  これらのヘッダーをプリコンパイルすると、プログラムのコンパイル時間を短縮できます。  
  
> [!NOTE]
>  1 つのソース ファイルに対しては 1 つのプリコンパイル済みヘッダー \(.pch\) ファイルしか使用できませんが、同じプロジェクトで複数の .pch ファイルを使用することはできます。  
  
## 参照  
 [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)
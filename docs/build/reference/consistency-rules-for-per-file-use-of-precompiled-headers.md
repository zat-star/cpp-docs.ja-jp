---
title: "PCH ファイルの使用時の一貫性規則 | Microsoft Docs"
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
  - ".pch ファイル, 一貫性規則"
  - "PCH ファイル, 一貫性規則"
  - "プリコンパイル済みヘッダー ファイル, 一貫性規則"
ms.assetid: afd49365-48bc-41f4-b700-fe8297b944a1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# PCH ファイルの使用時の一貫性規則
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/Yu](../../build/reference/yu-use-precompiled-header-file.md) コンパイラ オプションを使用すると、使用するプリコンパイル済みヘッダー \(PCH\) ファイルを指定できます。  
  
 PCH を使うと、特に指定しない限り、コンパイラ オプションやプラグマなどのコンパイル環境が PCH 生成時の状態と同じだと見なされて、コードがコンパイルされます。  矛盾する箇所が検出されると、警告が出力されます。矛盾箇所の内容が示される場合もあります。  ただし、この警告は単に矛盾を示しているだけなので、必ずしも PCH に問題があるとは限りません。  PCH に対する一貫性の要件については、以下のセクションで説明します。  
  
## コンパイラ オプションの一貫性  
 次のコンパイラ オプションでは、PCH を使用する場合に矛盾が生じる場合があります。  
  
-   \/D \(プリプロセッサ\) オプションでマクロを作成した場合は、PCH のコンパイル時と同じマクロを今回のコンパイルにも使う必要があります。  定義した定数の状態はチェックされませんが、定数を変更すると予測できない結果を生じることがあります。  
  
-   \/E オプションや \/EP オプションでは、PCH を使うことはできません。  
  
-   PCH の作成には、\/FR \(ブラウザー情報の生成\) または \/Fr \(ローカル変数の除外\) を使用する必要があります。この PCH を使う以降のコンパイルでは、これらのオプションを使うことはできません。  
  
## C 7.0 互換 \(\/Z7\)  
 PCH の作成時にこのオプションを有効にしておくと、この PCH を使う以降のコンパイル時にデバッグ情報を使用できます。  
  
 PCH の作成時に \/Z7 オプションを有効にしていない場合は、以降のコンパイルで PCH と \/Z7 オプションを併用すると、矛盾に対して警告が発行されます。  このとき、デバッグ情報は現在の .obj ファイルに格納されるため、デバッガーでは PCH で定義されているローカル シンボルを使用できません。  
  
## インクルード パスの一貫性  
 PCH 自体には、PCH の生成時に有効であったインクルード パスに関する情報は含まれていません。  .pch ファイルを使用すると、現在のコンパイルで指定されたインクルード パスが必ず使用されます。  
  
## ソース ファイルの一貫性  
 .PCH ファイルを使ってソース コードをコンパイルする \(\/Yu オプション\) と、プリコンパイル対象のソース コード内のプリプロセッサ ディレクティブ \(プラグマを含む\) がすべて無視されます。  したがって、これらのプリプロセッサ ディレクティブで指定するコンパイルは、.PCH ファイルの作成 \(\/Yc オプション\) 時と同じ内容にする必要があります。  
  
## プラグマの一貫性  
 PCH の作成時に処理されたプラグマは、通常、その PCH でコンパイルされるファイルにも反映されます。  ただし、comment プラグマと message プラグマは、PCH を使ったコンパイルには反映されません。  
  
 以下のプラグマは PCH の一部として保持され、PCH を使った以降のコンパイルに反映されます。  
  
||||  
|-|-|-|  
|alloc\_text|include\_alias|pack|  
|auto\_inline|init\_seg|pointers\_to\_members|  
|check\_stack|inline\_depth|setlocale|  
|code\_seg|inline\_recursion|vtordisp|  
|data\_seg|intrinsic|警告|  
|function|optimize||  
  
## 参照  
 [プリコンパイル済みヘッダーの一貫性規則](../../build/reference/precompiled-header-consistency-rules.md)   
 [\/Yu \(プリコンパイル済みヘッダー ファイルの使用\)](../../build/reference/yu-use-precompiled-header-file.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)
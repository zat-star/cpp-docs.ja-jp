---
title: "ブラウザー情報ファイルのビルド : 概要 | Microsoft Docs"
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
  - ".bsc ファイル, .bsc ファイルの概要"
  - "ブラウザー情報ファイル (.bsc)"
  - "ブラウザー情報ファイル (.bsc), 作成"
  - "bsc ファイル, bsc ファイルの概要"
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ブラウザー情報ファイルのビルド : 概要
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

シンボルの参照用としてブラウザー データベースを作成するために、コンパイラではプロジェクトのソース ファイルごとに .sbr ファイルが作成され、BSCMAKE.EXE ではそれらの .sbr ファイルが 1 つの .bsc ファイルに連結されます。  
  
 .sbr ファイルと .bsc ファイルの生成には時間がかかるため、Visual C\+\+ ではそれらの機能が既定でオフになっています。  現在の情報を参照する必要がある場合は、参照オプションをオンにし、プロジェクトを再度ビルドする必要があります。  
  
 [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) または [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md) を使用すると、コンパイラで .sbr ファイルを作成できます。  .bsc ファイルを作成するには、コマンド ラインで [BSCMAKE](../../build/reference/bscmake-command-line.md) を呼び出します。  コマンド ラインで BSCMAKE を使用すると、ブラウザー情報ファイルをさらに細かく制御できます。  詳細については、「[BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)」を参照してください。  
  
> [!TIP]
>  .sbr ファイルの生成はオンにして、.bsc ファイルの生成はオフのままという設定もできます。  このように設定するとビルドが高速化されますが、.bsc ファイルの生成をオンにしてプロジェクトをビルドしても、新しい .bsc ファイルをすぐに作成できます。  
  
 .bsc ファイルのサイズを縮小すると、.bsc ファイルのビルドに必要な時間、メモリ、およびディスク容量を削減できます。  
  
 開発環境でブラウザー ファイルをビルドする方法については、「[&#91;全般&#93; プロパティ ページ \(プロジェクト\)](../Topic/General%20Property%20Page%20\(Project\).md)」を参照してください。  
  
### サイズの小さい .bsc ファイルを作成するには  
  
1.  [BSCMAKE コマンド ライン オプション](../Topic/BSCMAKE%20Options.md)を使用して、ブラウザー情報ファイルから情報を除外します。  
  
2.  コンパイル時またはアセンブル時に、.sbr ファイルのローカル シンボルを 1 つ以上省略します。  
  
3.  現段階のデバッグに必要な情報がオブジェクト ファイルに格納されていない場合は、ブラウザー情報ファイルをリビルドするときに BSCMAKE コマンドでその .sbr ファイルを省略します。  
  
### 複数プロジェクトのブラウザー データベースを 1 つのブラウザー情報ファイル \(.bsc\) に結合するには  
  
1.  プロジェクト レベルで .bsc ファイルをビルドしないようにするか、\/n スイッチを使用して .sbr ファイルが切り捨てられないようにします。  
  
2.  すべてのプロジェクトがビルドされた後に、すべての .sbr ファイルを入力内容として BSCMAKE を実行します。  ワイルドカードを使用できます。  たとえば、.sbr ファイルの格納されているプロジェクト ディレクトリ C:\\X、C:\\Y、および C:\\Z があり、すべてのファイルを 1 つの .bsc ファイルに結合する必要がある場合は、BSCMAKE C:\\X\\\*.sbr C:\\Y\\\*.sbr C:\\Z\\\*.sbr \/o c:\\whatever\_directory\\combined.bsc を使用して .bsc ファイルをビルドします。  
  
## 参照  
 [C と C\+\+ のビルド ツール](../Topic/C-C++%20Build%20Tools.md)   
 [BSCMAKE リファレンス](../../build/reference/bscmake-reference.md)
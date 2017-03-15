---
title: "Visual C++ ActiveX コントロールの再配布 | Microsoft Docs"
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
  - "コントロール [C++], 配布"
  - "コントロール [C++], 再配布"
ms.assetid: eefbb7e4-d28c-4c35-98bf-d9540cfaae83
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ ActiveX コントロールの再配布
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 6.0 には、後で再配布する、アプリケーションで使用できる ActiveX コントロールが用意されています。  これらのコントロールは、Visual C\+\+ には含まれていません。  Visual C\+\+ 6.0 の使用許諾契約に従って、Visual C\+\+ で開発されたアプリケーションと共にこれらのコントロールを再配布できます。  
  
> [!NOTE]
>  Visual C\+\+ 6.0 は Microsoft サポート対象から除外されました。  
  
 再配布できる Visual C\+\+ 6.0 の ActiveX コントロールの一覧については、Visual C\+\+ 6.0 製品 CD のディスク 1 の Common\\Redist\\Redist.txt を参照してください。  
  
 アプリケーションを配布する場合は、Regsvr32.exe を使用して、ActiveX コントロールの .ocx をインストールして登録する必要があります。  また、現在のバージョンのシステム ファイルがターゲット コンピューターにインストールされていることを確認する必要があります。必要なシステム ファイルを次に示します。アスタリスク \(\*\) が付いているファイルは、登録する必要があるファイルです。  
  
-   Asycfilt.dll  
  
-   Comcat.dll \*  
  
-   Oleaut32.dll \*  
  
-   Olepro32.dll \*  
  
-   Stdole2.tlb  
  
 これらの DLL がターゲット システムで使用できない場合は、対応するオペレーティング システムで定められた更新機構を使用して DLL を更新する必要があります。  Windows オペレーティング システムの最新の Service Pack は、[http:\/\/windowsupdate.microsoft.com](http://windowsupdate.microsoft.com) からダウンロードできます。  
  
 アプリケーションで、データベースに接続する ActiveX コントロールを使用する場合は、Microsoft Data Access Components \(MDAC\) をターゲット システムにインストールしておく必要があります。  詳細については、「[データベース サポート ファイルの再頒布](../ide/redistributing-database-support-files.md)」を参照してください。  
  
 データベースに接続する ActiveX コントロールを使用するときは、ターゲット コンピューターにデータ ソース名をレプリケートする必要があります。  レプリケーションは、`ConfigDSN` などの関数を使用してプログラムで行うことができます。  
  
 一部の再頒布可能な ActiveX コントロールは、追加の依存関係を持っています。  Visual C\+\+ 6.0 製品 CD の Os\\System フォルダーに入っている各 .ocx ファイルに対しても .dep ファイルが作成されます。  再配布する .ocx ファイルごとに、対応する .dep ファイルの 1 つ以上の USES エントリを探します。  ファイルが一覧に表示されている場合は、ターゲット コンピューターにそのファイルが存在することを確認してください。  .ocx ファイルを直接サポートするすべての DLL を登録する必要があります。  Regsvr32.exe の実行が正常に終了するには、コントロールが静的に読み込むすべての DLL をターゲット コンピューターに用意しておく必要があります。さらに、依存関係として一覧に表示された DLL に対する .dep ファイルが Visual C\+\+ 6.0 CD の Os\\System フォルダー内にある場合は、その .dep ファイル内の USES エントリを調べる必要もあります。  
  
## 参照  
 [Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)
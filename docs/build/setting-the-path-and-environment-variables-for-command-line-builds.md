---
title: "コマンド ライン ビルドのパスと環境変数の設定 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
f1_keywords: 
  - "include"
  - "Lib"
  - "Path"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ [C++], 環境変数"
  - "コンパイル (ソース コードを) [C++], コマンド ラインから"
  - "環境変数 [C++]"
  - "環境変数 [C++], CL コンパイラ"
  - "INCLUDE 予約語"
  - "LIB 環境変数"
  - "LINK ツール [C++], 環境変数"
  - "LINK ツール [C++], パス"
  - "PATH 予約語"
  - "VCVARS32.bat ファイル"
ms.assetid: 99389528-deb5-43b9-b99a-03c8773ebaf4
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# コマンド ライン ビルドのパスと環境変数の設定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] コマンド ライン ビルド ツールには、インストールに合わせてカスタマイズしたいくつかの環境変数が必要です。  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] をインストールすると、必要な環境変数を設定するコマンド ファイルが作成され、これらの環境変数が既に設定されているコマンド プロンプト ウィンドウを起動するショートカットが作成されます。  コマンド ライン ツールを使用する場合は、これらのショートカットのいずれかを実行するか、標準のコマンド プロンプト ウィンドウを開いて vcvarsall.bat コマンド ファイルを実行できます。  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] コマンド ライン ツールでは、PATH、TMP、INCLUDE、LIB、および LIBPATH 環境変数が使用されます。また、ツール固有の環境変数が使用される場合もあります。  これらの環境変数の値はインストールに固有であり、製品の更新やアップグレードによって変更される場合があるため、自分で設定するのではなく、vcvarsall.bat または \[開発者コマンド プロンプト\] のショートカットを使用することをお勧めします。  コンパイラとリンカーで使用される固有の環境変数の詳細については、「[環境変数 CL](../build/reference/cl-environment-variables.md)」および「[環境変数 LINK](../build/reference/link-environment-variables.md)」を参照してください。  
  
> [!NOTE]
>  コマンド ライン ツールまたはツール オプションには、管理者のアクセス許可を必要とするものがあります。  これらを使用するには、\(開くコマンド プロンプト ウィンドウのショートカット メニューで\) **\[管理者として実行\]** オプションを使用してコマンド プロンプト ウィンドウを開くことをお勧めします。  
  
## コマンド プロンプトのショートカットの使用  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] のすべてのエディションに含まれている \[開発者コマンド プロンプト\] のショートカットによって、コマンド プロンプト ウィンドウが開き、32 ビット x86 ネイティブ ツールセットを使用して x86 プロセッサを対象とするように環境が設定されます。  x64 および ARM プラットフォームを対象とする 32 ビット クロス コンパイラのコマンド プロンプトも使用できます。  システムおよびインストールされている [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] のエディションによっては、x64 プロセッサを対象とする 64 ビット x64 ネイティブ ツールセットのコマンド プロンプト ショートカットや、x86 プロセッサを対象とする 64 ビット クロス コンパイラのコマンド プロンプト ショートカットも使用できます。  コマンド ライン ツールセットの以下のバージョンは、Visual Studio のすべてのエディションで使用できます。  
  
 x86 on x86  
 このツールセットは、x86 マシン用の出力ファイルの作成に使用します。  x86 マシン上ではネイティブの 32 ビット プロセスとして、64 ビットの Windows オペレーティング システムでは WOW64 により 32 ビット プロセスとして実行されます。  
  
 [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] on x86 \([!INCLUDE[vcprx64](../Token/vcprx64_md.md)] クロス コンパイラ\)  
 このツールセットは、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] 用の出力ファイルの作成に使用します。  x86 マシン上ではネイティブの 32 ビット プロセスとして、64 ビットの Windows オペレーティング システムでは WOW64 により 32 ビット プロセスとして実行されます。  
  
 ARM on x86 \(ARM クロス コンパイラ\)  
 このツールセットは、ARM マシン用の出力ファイルの作成に使用します。  x86 マシン上ではネイティブの 32 ビット プロセスとして、64 ビットの Windows オペレーティング システムでは WOW64 により 32 ビット プロセスとして実行されます。  
  
 コマンド ライン ツールセットの以下のバージョンは、64 ビット プラットフォームで使用できます。  
  
 x86 on [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]  
 このツールセットは、x86 マシン用の出力ファイルの作成に使用します。  64 ビット Windows オペレーティング システム上でネイティブのプロセスとして実行されます。  
  
 [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] on[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]  
 このツールセットは、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] マシン用の出力ファイルの作成に使用します。  64 ビット Windows オペレーティング システム上でネイティブのプロセスとして実行されます。  
  
 ARM on x64 \(ARM クロス コンパイラ\)  
 このツールセットは、ARM マシン用の出力ファイルの作成に使用します。  64 ビット Windows オペレーティング システム上でネイティブの 64 ビット プロセスとして実行されます。  
  
#### \[開発者コマンド プロンプト\] ウィンドウを開くには  
  
1.  表示される Windows 8 の \[スタート\] 画面で、「Visual Studio ツール」と入力します。  入力に従って検索結果が変化します。**\[Visual Studio ツール\]** が表示されたら、それを選択します。  
  
     これ以前のバージョンの Windows では、**\[スタート\]** をクリックし、検索ボックスに「Visual Studio ツール」と入力します。  検索結果に **\[Visual Studio ツール\]** が表示されたら、それを選択します。  
  
2.  **\[Visual Studio ツール\]** フォルダーで、使用しているバージョンの [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] の **\[開発者コマンド プロンプト\]** を開きます。  \(管理者として実行するには、\[開発者コマンド プロンプト\] のショートカット メニューを開き、**\[管理者として実行\]** を選択します\)。  
  
 開発者コマンド プロンプトによって、32 ビット ネイティブ ツールセットを使用して x86 プロセッサを対象とするように環境が設定されます。  **\[x64 Cross Tools コマンド プロンプト\]** を選択すると、32 ビット ネイティブ ツールセットを使用して x64 プロセッサを対象とします。  **\[ARM Cross Tools コマンド プロンプト\]** を選択すると、32 ビット ネイティブ ツールセットを使用して ARM プロセッサを対象とします。  **\[x64 Native Tools コマンド プロンプト\]** を選択すると、64 ビット ネイティブ ツールセットを使用して x64 プロセッサを対象とします。  
  
## コマンド プロンプト ウィンドウでの vcvarsall.bat の使用  
 標準のコマンド プロンプト ウィンドウで vcvarsall.bat を実行することで、環境変数を設定し、ネイティブの 32 ビットまたは 64 ビット コンパイル用、または x86、x64、または ARM プロセッサへのクロス コンパイル用にコマンド ラインを構成できます。  引数を指定せずに vcvarsall.bat を実行すると、x86 を対象として 32 ビット ネイティブ コンパイラを使用するための環境変数が構成されます。  ただし、このバッチ ファイルを使用して任意のコンパイラを構成できます。  ビルド コンピューターのアーキテクチャにインストールされていない、または使用できないコンパイラ構成を指定した場合は、メッセージが表示されます。  サポートされている引数を次の表に示します。  
  
|vcvarsall.bat 引数|コンパイラ|ビルドコンピューターのアーキテクチャ|ビルド出力のアーキテクチャ|  
|----------------------|-----------|------------------------|-------------------|  
|x86|x86 32 ビット ネイティブ|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|x86|  
|x86\_amd64|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] on x86 クロス|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|x86\_arm|ARM on x86 クロス|x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|ARM|  
|amd64|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] 64 ビット ネイティブ|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|amd64\_x86|x86 on [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] クロス|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|x86|  
|amd64\_arm|ARM on [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] クロス|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|ARM|  
  
 次の手順では、32 ビット ネイティブ ツールセットを使用して x86 プラットフォームを対象とするようにコマンド プロンプトを構成する方法を示します。  
  
#### vcvarsall.bat を実行するには  
  
1.  コマンド プロンプトで、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] のインストール ディレクトリに移動します。  \(場所は、システムおよび [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] のインストールによって異なりますが、通常は C:\\Program Files \(x86\)\\Microsoft Visual Studio *version*\\VC\\ です\)。たとえば、次のように入力します。  
  
     cd "\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\VC"  
  
2.  このコマンド プロンプト ウィンドウを 32 ビット x86 コマンド ライン ビルド用に構成するには、コマンド プロンプトで次のように入力します。  
  
     `vcvarsall x86`  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] には、コマンド ライン環境を設定するための vcvars32.bat もあります。  vcvars32.bat ファイルは、32 ビット x86 コマンド ライン ビルドを有効にするための適切な環境変数の設定に制限されています。  これは、`vcvarsall x86` コマンドと同等です。  
  
 コマンド ライン ビルド用に [DEVENV](../Topic/Devenv%20Command%20Line%20Switches.md) を使用している場合、vcvarsall.bat または vcvars32.bat によって設定された環境は、**\/useenv** オプションも指定しない限り、ビルドに影響しません。  
  
> [!CAUTION]
>  vcvarsall.bat ファイルは、コンピューターによって異なる場合があります。  vcvarsall.bat ファイルが見つからない場合や破損している場合でも、別のコンピューターのファイルを使用して置き換えないでください。  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] セットアップ プログラムを再実行してファイルを置き換えてください。  
>   
>  vcvarsall.bat ファイルは、バージョンによっても異なります。  以前のバージョンの [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] と最新バージョンの [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] の両方がコンピューターにインストールされている場合は、同じコマンド プロンプト ウィンドウから異なるバージョンの vcvarsall.bat または vcvars32.bat を実行しないでください。  
  
## 参照  
 [コマンド ラインでのビルド](../Topic/Building%20on%20the%20Command%20Line.md)   
 [リンク](../Topic/Linking.md)   
 [リンカー オプション](../build/reference/linker-options.md)   
 [C\/C\+\+ プログラムのコンパイル](../build/reference/compiling-a-c-cpp-program.md)   
 [コンパイラ オプション](../build/reference/compiler-options.md)
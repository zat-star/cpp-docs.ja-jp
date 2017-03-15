---
title: "方法: 64 ビットの Visual C++ ツールセットをコマンド ラインから有効にする | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "64 ビット コンパイラ [C++], コマンド ラインの使用"
  - "64 ビット コンパイラ [C++], ツールセットを有効化 (コマンド ラインで)"
  - "コマンド ライン [C++], 64 ビット コンパイラ"
  - "IPF"
  - "IPF, コマンド ライン コンパイラ"
  - "Itanium [C++]"
  - "Itanium [C++], コマンド ライン コンパイラ"
  - "x64 [C++]"
  - "x64 [C++], コマンド ライン コンパイラ"
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
caps.latest.revision: 30
caps.handback.revision: 30
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 方法: 64 ビットの Visual C++ ツールセットをコマンド ラインから有効にする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ には、32 ビット、64 ビット、または ARM ベースの Windows オペレーティング システム上で実行できるアプリを作成するためのコンパイラが用意されています。  
  
> [!NOTE]
>  各エディションの Visual C\+\+ に付属している特定のツールの詳細については、「[Visual Studio エディションでの Visual C\+\+ ツールおよびテンプレート](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)」を参照してください。  
>   
>  Visual Studio IDE で 64 ビット アプリケーションを作成する方法については、「[方法 : Visual C\+\+ プロジェクトを 64 ビット プラットフォーム用に設定する](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)」を参照してください。  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] には、x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]、および ARM を対象とする 32 ビット、x86 ホスト、ネイティブ、および ARM の各コンパイラが用意されています。  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] が 64 ビット Windows オペレーティング システムにインストールされている場合、32 ビット、x86 ホスト ネイティブ、およびクロス コンパイラに加え、64 ビット、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)] ホスト ネイティブ、およびクロス コンパイラが、各対象 \(x86、[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]、および ARM\) に対してインストールされます。  それぞれの対象の 32 ビットと 64 ビットのコンパイラでは、同一のコードが生成されますが、64 ビット コンパイラは、プリコンパイル済みヘッダーのシンボルと、プログラム全体の最適化 \([\/GL](../build/reference/gl-whole-program-optimization.md)、[\/LTCG](../build/reference/ltcg-link-time-code-generation.md)\) オプションに対応するため、より多くのメモリをサポートしています。  32 ビット コンパイラを使用していてメモリ制限の問題に直面した場合は、64 ビット コンパイラを試してください。  
  
 Visual Studio が 64 ビット Windows オペレーティング システムにインストールされている場合、64 ビット [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] ネイティブ コンパイラおよび x86 クロス コンパイラ用の追加のコマンド プロンプト ショートカットを使用できます。  Windows 8 でこれらのコマンド プロンプトにアクセスするには、**\[スタート\]** 画面で **\[すべてのアプリ\]** を開きます。  インストールされたバージョンの **\[[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\]** の下で、**\[Visual Studio ツール\]** を開き、ネイティブツールまたはクロスツールのいずれかのコマンド プロンプトを選択します。  これ以前のバージョンの Windows では、**\[スタート\]** をクリックし、**\[すべてのプログラム\]**、**\[[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]\]**、**\[Visual Studio ツール\]** の順にクリックしてコマンド プロンプトを選択します。  
  
## Vcvarsall.bat  
 どのコンパイラも、コマンド ラインから使用できます。これには、vcvarsall.bat コマンド ファイルを実行し、パスと環境変数を構成してコンパイラ ツールセットを有効にします。  x86 または ARM プラットフォームを対象とする 64 ビット ツールセットを有効にするコマンド プロンプト ショートカットがないため、コマンド プロンプト ウィンドウで vcvarsall.bat を使用して 64 ビット ツールセットを代わりに使用します。  詳細については、「[コマンド ライン ビルドのパスと環境変数の設定](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)」を参照してください。  
  
 次の手順では、コマンド プロンプトを設定して x86、x64、ARM プラットフォームを対象とした 64 ビット ネイティブ ツールセットを使用する方法を示しています。  
  
#### vcvarsall.bat を実行して 64 ビット ツールセットを使用するには  
  
1.  コマンド プロンプトで、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] インストール ディレクトリに変更します  \(システムおよび [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] のインストールによって異なりますが、一般的な場所は C:\\Program Files \(x86\)\\Microsoft Visual Studio *version*\\VC\\ です\)。たとえば、次のように入力します。  
  
     cd "\\Program Files \(x86\)\\Microsoft Visual Studio 12.0\\VC"  
  
2.  x64 プラットフォームを対象とする 64 ビット コマンドライン ビルドのコマンド プロンプト ウィンドウを設定するには、コマンド プロンプトで次のように入力します。  
  
     `vcvarsall amd64`  
  
3.  x86 プラットフォームを対象とする 64 ビット コマンドライン ビルドのコマンド プロンプト ウィンドウを設定するには、コマンド プロンプトで次のように入力します。  
  
     `vcvarsall amd64_x86`  
  
4.  ARM プラットフォームを対象とする 64 ビット コマンドライン ビルドのコマンド プロンプト ウィンドウを設定するには、コマンド プロンプトで次のように入力します。  
  
     `vcvarsall amd64_arm`  
  
## 参照  
 [64 ビット用プログラムの構成](../build/configuring-programs-for-64-bit-visual-cpp.md)
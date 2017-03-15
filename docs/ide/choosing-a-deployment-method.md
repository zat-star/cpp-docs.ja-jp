---
title: "配置方法の選択 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーションの配置 [C++], メソッド"
  - "配置 (アプリケーションを) [C++], メソッド"
  - "DLL [C++], 再配布"
  - "動的リンク [C++]"
  - "ライブラリ [C++], アプリケーションの配置の問題"
  - "マニフェスト [C++]"
  - "再配布 (DLL を)"
  - "side-by-side アセンブリ [C++]"
  - "静的なリンク [C++]"
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
caps.latest.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# 配置方法の選択
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] アプリケーションを単体で使用できない場合、また、コピー コマンドを使用して配置できない場合は、Windows インストーラーを使用して配置することをお勧めします。  Windows インストーラーでは、インストール、修復、およびアンインストールのほか、アプリケーション ファイル、依存関係、およびレジストリ エントリの分割不可能な更新もサポートされています。  
  
> [!NOTE]
>  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ネイティブ アプリケーションの [ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md) 配置は Visual Studio でも可能ですが、追加の手順が必要になります。  詳細については、「[Visual C\+\+ アプリケーションの ClickOnce 配置](../ide/clickonce-deployment-for-visual-cpp-applications.md)」を参照してください。  
  
## Visual C\+\+ ライブラリの共有 DLL  
 Visual Studio インストーラーでは、Visual C\+\+ ライブラリが %windir%\\system32\\ ディレクトリにインストールされるため、このライブラリに依存する Visual C\+\+ アプリケーションを開発する場合、そのアプリケーションは意図したとおりに実行されます。  ただし、Visual Studio がない可能性があるコンピューターにアプリケーションを配置する場合は、ライブラリがアプリケーションと共にそのコンピューターにインストールされているかどうかを確認することをお勧めします。  
  
## Visual C\+\+ ライブラリの再配布  
 ご利用の配置に、再頒布用にライセンスされた任意のバージョンの Visual C\+\+ ライブラリを再頒布できます。  配置する方法は 3 つあります。  
  
-   再頒布可能パッケージを使用した集中配置。Visual C\+\+ ライブラリが共有 DLL として %windir%\\system32\\ にインストールされます \(このフォルダーにインストールするには管理者権限が必要です\)。アプリケーションをターゲット コンピューターにインストールする前に、再頒布可能パッケージを実行するスクリプトまたはセットアップ プログラムを作成できます。  再頒布可能パッケージは、x86 プラットフォーム、x64 プラットフォーム、および ARM プラットフォーム \(VCRedist\_x86.exe、VCRedist\_x64.exe、または VCRedist\_arm.exe\) で使用できます。  Visual Studio では、これらのパッケージは %ProgramFiles\(x86\)%\\Microsoft Visual Studio `version`\\VC\\Redist\\`locale ID`\\ に含まれています。  [Microsoft ダウンロード センター](http://go.microsoft.com/fwlink/?LinkId=132793)からダウンロードすることもできます \(ダウンロード センターで、アプリケーションに対応する "[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 再頒布可能パッケージ *Visual Studio version and update*" を検索します。  たとえば、Visual Studio 2012 更新プログラム 4 を使用してアプリケーションをビルドした場合は、"Visual C\+\+ 再頒布可能パッケージ 2012 更新プログラム 4" を検索します\)。再頒布パッケージを使用する方法については、「[チュートリアル: Visual C\+\+ 再頒布可能パッケージを使用した Visual C\+\+ アプリケーションの配置](../Topic/Walkthrough:%20Deploying%20a%20Visual%20C++%20Application%20By%20Using%20the%20Visual%20C++%20Redistributable%20Package.md)」を参照してください。  
  
-   マージ モジュールを使用した集中配置。各マージ モジュールによって特定の Visual C\+\+ ライブラリが共有 DLL として %windir%\\system32\\ にインストールされます \(このフォルダーにインストールするには管理者権限が必要です\)。マージ モジュールは、アプリケーションの .msi インストーラー ファイルの一部になります。  Visual C\+\+ の再頒布可能なマージ モジュールは、Visual Studio の \\Program Files \(x86\)\\Common Files\\Merge Modules\\ に含まれています。  詳細については、「[マージ モジュールを使用した再配布](../ide/redistributing-components-by-using-merge-modules.md)」を参照してください。  
  
-   ローカル配置。Visual Studio インストール \(通常は \\Program Files \(x86\)\\Microsoft Visual Studio `version`\\VC\\Redist\\`platform`\\`library`\\\) から特定の Visual C\+\+ DLL をコピーし、インストール先のコンピューターで、アプリケーションの実行可能ファイルと同じフォルダーにインストールします。  この配置方法を使用すると、管理者権限を持たないユーザーによるインストール、またはネットワーク共有から実行できるアプリケーションに対するインストールが可能です。  
  
 再頒布可能なマージ モジュールが使用されている配置で、管理者権限を持たないユーザーがインストールを実行すると、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLL はインストールされず、アプリケーションは実行されません。  また、ユーザー単位でのインストールを許可するマージ モジュールでビルドされたアプリケーション インストーラーでは、システムのすべてのユーザーに影響を及ぼす共有の場所にライブラリがインストールされます。  ローカル配置を使用すると、必要な [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] DLL を特定のユーザーのアプリケーションのディレクトリに、他のユーザーに影響を与えることはなくインストールできます。管理者権限も不要ですが、  これによりサービス性に問題が発生する可能性があるため、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] の再頒布可能 DLL のローカル配置はお勧めしません。  
  
 Visual C\+\+ ライブラリの配置が不適切だと、そのライブラリに依存するアプリケーションの実行時に実行時エラーが発生する可能性があります。  オペレーティング システムがアプリケーションを読み込むときの検索順序については、「[LoadLibraryEx function \(LoadLibraryEx 関数\)](http://go.microsoft.com/fwlink/?LinkId=132792)」を参照してください。  
  
## 動的リンクを静的リンクに優先させる  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリを再配布する場合、静的リンクは使用しないことをお勧めします。  アプリケーションのパフォーマンスが静的リンクによって大きく向上することはほぼありませんが、サービスのコストは、ほとんどの場合、高くなります。  たとえば、セキュリティの強化によって更新されるライブラリに静的にリンクしているアプリケーションについて考えます。このアプリケーションは、再コンパイルして再配置しなければ、セキュリティ強化のメリットを得ることはできません。  代わりに、アプリケーションをライブラリに動的にリンクさせて、配置される場所でライブラリを更新できるようにすることをお勧めします。  
  
## 参照  
 [デスクトップ アプリケーションの配置](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)   
 [Not in Build: Choosing a Deployment Strategy](http://msdn.microsoft.com/ja-jp/ecd632d8-063c-4028-b785-81bba045107b)   
 [Windows Installer Deployment Overview](http://msdn.microsoft.com/ja-jp/3ce4610a-b54f-404e-b650-42f4a55dfc3b)   
 [ClickOnce のセキュリティと配置](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [配置例](../ide/deployment-examples.md)
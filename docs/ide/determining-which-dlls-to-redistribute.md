---
title: "再配布する DLL の決定 | Microsoft Docs"
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
  - "アプリケーションの配置 [C++], DLL の再配布"
  - "依存関係 [C++], アプリケーションの配置"
  - "配置 (アプリケーションを) [C++], DLL の再配布"
  - "DLL [C++], 再配布"
  - "再配布 (DLL を)"
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# 再配布する DLL の決定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio によって提供される DLL を使用するアプリケーションをビルドする場合、アプリケーションを実行するユーザーもそれらの DLL を自分のコンピューター上に持っている必要があります。  多くのユーザーは Visual Studio をインストールしていないと考えられるので、それらの DLL をユーザーに提供する必要があります。  Visual Studio では、これらの DLL を、アプリケーションのインストーラーに含めることができる再頒布可能ライブラリとして利用できるようにしています。  
  
 再頒布可能 DLL は、Visual Studio のインストールに含まれています。  既定では、Program Files \(x86\)\\Microsoft Visual Studio version\\VC\\Redist フォルダーにインストールされます。  インストーラーに含めやすくするために、DLL はスタンドアロンの再頒布可能パッケージとして、Microsoft ダウンロード センターからも入手できます。  これらのパッケージは実行可能ファイルであり、再頒布可能ファイルをユーザーのコンピューターにインストールします。  再頒布可能パッケージのバージョンは、アプリケーションの作成に使用した Visual Studio ツールセットのバージョンと一致する必要があります。  一致する再頒布可能パッケージを見つけるには、[Microsoft ダウンロード センター](http://go.microsoft.com/fwlink/p/?LinkId=158431)で "Visual C\+\+ 再頒布可能パッケージ" を検索します。  
  
 アプリケーションと共に再配布する必要がある DLL を判断するには、アプリケーションが依存する DLL の完全な一覧を収集します。  その一覧を収集する方法の 1 つは、「[Visual C\+\+ アプリケーションの依存関係の理解](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)」で説明されているように、Dependency Walker \(depends.exe\) を実行することです。  
  
 依存関係の一覧がある場合は、Microsoft Visual Studio インストール ディレクトリにある Redist.txt ファイル内の一覧、または Visual Studio のマイクロソフト ソフトウェア ライセンス条項の「頒布可能コード」セクションで言及されている再頒布可能 DLL の "REDIST list" と比較してください。  Visual Studio 2013 での一覧は、オンラインで「[Microsoft Visual Studio 2013 および Microsoft Visual Studio 2013 SDK 用頒布可能コード](http://go.microsoft.com/fwlink/p/?LinkId=313603)」から利用できます。  Visual Studio に含まれているすべてのファイルを再配布することはできません。再配布を許可されているのは、Redist.txt またはオンラインの "REDIST list" で指定されているファイルだけです。 アプリケーションのデバッグ バージョンと、各種の Visual C\+\+ デバッグ DLL は、再配布できません。  詳細については、「[配置方法の選択](../ide/choosing-a-deployment-method.md)」を参照してください。  
  
 次の表に、アプリケーションが依存する可能性がある一部の Visual C\+\+ DLL を示します。  
  
|Visual C\+\+ ライブラリ|説明|対象|  
|------------------------|--------|--------|  
|msvcr*version*.dll|ネイティブ コード用の C ランタイム ライブラリ \(CRT\)|[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)を使用するアプリケーション。|  
|msvcp*version*.dll|ネイティブ コード用の標準 C\+\+ ライブラリ|[標準 C\+\+ ライブラリ](../standard-library/cpp-standard-library-reference.md)を使用するアプリケーション|  
|mfc*version*.dll|MFC \(Microsoft Foundation Class\) ライブラリ|[MFC ライブラリ](../mfc/mfc-desktop-applications.md) を使用するアプリケーション。|  
|mfc*version*u.dll|Unicode をサポートする MFC ライブラリ|[MFC ライブラリ](../mfc/mfc-desktop-applications.md)を使用し、Unicode のサポートを必要とするアプリケーション。|  
|mfcmifc80.dll|MFC マネージ インターフェイス ライブラリ|[MFC ライブラリ](../mfc/mfc-desktop-applications.md)と [Windows フォーム コントロール](../Topic/Windows%20Forms%20Controls.md)を使用するアプリケーション。|  
|mfcm*version*.dll|MFC マネージ ライブラリ|[MFC ライブラリ](../mfc/mfc-desktop-applications.md)と [Windows フォーム コントロール](../Topic/Windows%20Forms%20Controls.md)を使用するアプリケーション。|  
|mfcm*version*u.dll|Unicode をサポートする MFC マネージ ライブラリ|[MFC ライブラリ](../mfc/mfc-desktop-applications.md)と [Windows フォーム コントロール](../Topic/Windows%20Forms%20Controls.md)を使用し、Unicode のサポートを必要とするアプリケーション。|  
  
> [!NOTE]
>  Active Template Library を別の DLL として再配布する必要がなくなりました。  その機能はヘッダーとスタティック ライブラリに移動されました。  
  
 アプリケーションと共にこのような DLL を再配布する方法の詳細については、「[Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)」を参照してください。  例については、「[配置例](../ide/deployment-examples.md)」を参照してください。  
  
 システム Dll はオペレーティング システムの一部であるため、通常は再配布する必要はありません。  ただし、Microsoft オペレーティング システムの複数のバージョンでアプリケーションを実行する場合など、これが該当しない可能性もあります。  この場合、使用許諾契約書を必ずお読みください。  また、Windows Update や Service Pack を通じて、または Microsoft が提供する再頒布可能パッケージを使用して、システム DLL のアップグレードを試みてください。  使用可能なパッケージは、[Microsoft サポート](http://support.microsoft.com/) Web サイトまたは [Microsoft ダウンロード センター](http://go.microsoft.com/fwlink/p/?LinkId=158431)で検索できます。  
  
## 参照  
 [配置方法の選択](../ide/choosing-a-deployment-method.md)   
 [デスクトップ アプリケーションの配置](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)
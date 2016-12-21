---
title: "[高度な機能] (MFC アプリケーション ウィザード) | Microsoft Docs"
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
  - "vc.appwiz.mfc.exe.advanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC アプリケーション ウィザード、高度な機能"
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [高度な機能] (MFC アプリケーション ウィザード)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、ヘルプや印刷サポートなど、アプリケーションの追加機能のためのオプションを示します。  各セクションで、これらの高度な機能の追加サポートを指定します。  
  
 **\[コンテキスト ヘルプ \(HTML\)\]**  
 F1 キー、\[ヘルプ\] メニュー、またはダイアログ ボックスの **\[ヘルプ\]** ボタンから開くことができる状況依存のヘルプ用のヘルプ ファイルが生成されます。  ヘルプ サポートにはヘルプ コンパイラが必要です。  ヘルプ コンパイラがない場合は、セットアップを再実行することによってインストールできます。  
  
 詳細については、「[HTML ヘルプ : プログラムの状況依存のヘルプ](../../mfc/html-help-context-sensitive-help-for-your-programs.md)」と「[ヘルプ ファイル \(HTML ヘルプ\)](../../ide/help-files-html-help.md)」を参照してください。  
  
 **\[印刷と印刷プレビュー\]**  
 MFC ライブラリから [CView クラス](../Topic/CView%20Class.md)内のメンバー関数を呼び出すことによって、印刷、印刷設定、および印刷プレビューのコマンドを処理するコードが生成されます。  これらの関数に対するコマンドも、ウィザードによってアプリケーションのメニューに追加されます。  印刷サポートが使用できるのは、ウィザードの [\[アプリケーションの種類\] \(MFC アプリケーション ウィザード\)](../Topic/Application%20Type,%20MFC%20Application%20Wizard.md) ページで **\[ドキュメント ビュー アーキテクチャ サポート\]** が指定されたアプリケーションだけです。  既定では、ドキュメント\/ビュー アプリケーションには印刷サポートが含まれます。  
  
 **\[オートメーション\]**  
 アプリケーションが別のアプリケーションに実装されているオブジェクトを操作したり、アプリケーションをオートメーション クライアントに公開したりできるように指定します。  
  
 **\[ActiveX コントロール\]**  
 ActiveX コントロールをサポートします \(既定値\)。  このオプションを選択せず、後で ActiveX コントロールをプロジェクトに追加することが必要になった場合は、アプリケーションのメンバー関数 [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md) に [CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md) の呼び出しを追加する必要があります。  
  
 **\[MAPI \(メッセージ API\)\]**  
 アプリケーションでメール メッセージの作成、操作、転送、および格納ができるように指定します。  
  
 **\[Windows ソケット\]**  
 TCP\/IP ネットワークで通信するアプリケーションを作成するために使用できる Windows ソケットをサポートします。  
  
 **\[アクティブなユーザー補助サポート\]**  
 [IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466) のサポートを [CWnd](../Topic/CWnd%20Class.md) の派生クラスに追加します。これにより、ユーザー インターフェイスをカスタマイズすることができ、ユーザー補助クライアントの操作性が向上します。  
  
 **\[コモン コントロール マニフェスト\]**  
 既定で有効になります。  Microsoft Windows XP 以降のオペレーティング システムに同梱されているコモン コントロール DLL を使用するためのアプリケーション マニフェストを生成します。  
  
 既存のアプリケーションで使用されている以前のバージョンのコモン コントロールが、Version 6 のコモン コントロール DLL によって自動的に更新されることはありません。  Version 6 のコモン コントロール DLL を使用するには、アプリケーションが DLL を読み込むことができるようにするためのアプリケーション マニフェストを作成する必要があります。  Version 6 のコモン コントロール DLL は、Windows XP のテーマもサポートしています。  
  
 また、アプリケーション マニフェストによって、アプリケーションに必要なその他の DLL やその他のバージョンも指定できます。  アプリケーション マニフェストの詳細については、[Isolated Applications and Side\-by\-Side Assemblies](http://msdn.microsoft.com/library/dd408052) の「[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]」を参照してください。  
  
 **再起動マネージャーのサポート**  
 [Windows 再起動マネージャー](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx)のサポートを追加します。  [新しい再起動マネージャーを使用する操作方法](http://msdn.microsoft.com/vstudio/ee886407)に関するページでは、MFC から再起動マネージャーを使用する方法について説明します。  
  
 **\[高度なフレーム ペイン\]**  
 |オプション|説明|  
|-----------|--------|  
|**\[ドッキング可能なエクスプローラー ペイン\]**|メイン フレーム ウィンドウの左側に、Visual Studio の**ソリューション エクスプローラー**のようなドッキング ペインを作成します。|  
|**\[ドッキング可能な出力ペイン\]**|メイン フレーム ウィンドウの下に、Visual Studio の**出力**ペインのようなドッキング ペインを作成します。|  
|**\[ドッキング可能なプロパティ ペイン\]**|メイン フレーム ウィンドウの右側に、Visual Studio の**プロパティ** ペインのようなドッキング ペインを作成します。|  
|**\[ナビゲーション ウィンドウ\]**|メイン フレーム ウィンドウの左側に、Outlook のナビゲーション バーのようなドッキング ペインを作成します。|  
|**\[キャプション バー\]**|メイン フレーム ウィンドウの上に、Office 形式のキャプション バーを作成します。|  
  
 **\[\[最近使ったファイル\] のファイル数\]**  
 最近使ったファイルの一覧に表示するファイル数を指定します。  既定値は 4 です。  
  
## 参照  
 [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)
---
title: "MFC ActiveX コントロール : ActiveX コントロールの配布 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetWindowsDirectory"
  - "GetSystemDirectory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配布 (MFC ActiveX コントロールを)"
  - "GetProcAddress メソッド, 登録 (ActiveX コントロールを)"
  - "GetSystemDirectory メソッド"
  - "GetWindowsDirectory メソッド"
  - "インストール (ActiveX コントロールを)"
  - "LoadLibrary メソッド, 登録 (ActiveX コントロールを)"
  - "MFC ActiveX コントロール, ANSI または Unicode のバージョン"
  - "MFC ActiveX コントロール, 配布"
  - "MFC ActiveX コントロール, インストール"
  - "MFC ActiveX コントロール, 登録"
  - "MFC40.DLL"
  - "MFC40U.DLL"
  - "MSVCRT40.dll"
  - "OLEPRO32.DLL"
  - "再頒布可能なファイル, MFC ActiveX コントロール"
  - "登録 (ActiveX コントロールを)"
  - "登録 (コントロールを)"
  - "レジストリ, 登録 (コントロールを)"
  - "RegSvr32.exe"
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC ActiveX コントロール : ActiveX コントロールの配布
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、問題を ActiveX コントロールの再配布に複数説明します。:  
  
-   [ANSI 形式または Unicode バージョンのコントロール](#_core_ansi_or_unicode_control_versions)  
  
-   [ActiveX コントロールと再頒布可能な DLL のインストール](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [コントロールの登録](#_core_registering_controls)  
  
    > [!NOTE]
    >  ActiveX コントロールの再配布の詳細については、「[コントロールの再頒布](../Topic/Redistributing%20Controls.md)」を参照してください。  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI 形式または Unicode バージョンのコントロール  
 かどうかコントロールの Unicode または ANSI バージョン、またはその両方を提供するかを決定する必要があります。  この決定は ANSI 文字型と Unicode 文字セットでよく移植性の要因に基づいています。  
  
 すべての Win32 オペレーティング システムで動作する ANSI のコントロール、さまざまな Win32 オペレーティング システム間の最大移植性を有効にします。  Unicode のコントロールは、Windows NT のみ \(バージョン 3.51 以降\) で、Windows 95 または Windows 98 で実行されます。  移植性が最大の注意点、ANSI のコントロールを提供します。  コントロールが Windows NT でのみ機能し、Unicode コントロールを提供できます。  この二つを提供し、アプリケーションがユーザーのオペレーティング システムでは、最も適切なバージョンをインストールすることもできます。  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> ActiveX コントロールと再頒布可能な DLL のインストール  
 、ActiveX コントロールを与えるセットアップ プログラムは、Windows ディレクトリの特別なサブディレクトリを作成し、コントロールの .OCX ファイルをインストールする必要があります。  
  
> [!NOTE]
>  Windows ディレクトリの名前を取得するには、セットアップ プログラムで Windows **GetWindowsDirectory** API を使用します。  企業や製品の名前からサブディレクトリの名前を派生したい場合があります。  
  
 セットアップ プログラムは、Windows のシステム ディレクトリに必要で再頒布可能な DLL ファイルをインストールする必要があります。  DLL のいずれかはユーザーのコンピューターに存在する場合、セットアップ プログラムは、インストールされているバージョンとバージョンを比較します。  バージョン番号が既にインストールされているファイルを上回った場合のみファイルを再インストールします。  
  
 ActiveX コントロールが OLE コンテナー アプリケーションでのみ使用でき、OLE コントロールで DLL の完全なセットを配布する必要はありません。  含まれているアプリケーション \(またはオペレーティング システム自体は\) 標準 OLE DLL がインストールされていると判断できます。  
  
##  <a name="_core_registering_controls"></a> コントロールの登録  
 コントロールが使用する前に適切なエントリは Windows 登録情報データベースでそれに対して作成する必要があります。  ActiveX コントロール コンテナーは、レジスタの新しいコントロールには、ユーザーがメニュー項目が用意されていますが、この機能はすべてのコンテナーで使用できないことがあります。  したがって、インストールすると、セットアップ プログラムにコントロールを登録する必要があります。  
  
 必要に応じて、代わりにコントロールを直接使用するセットアップ プログラムを作成できます。  
  
 コントロール DLL を読み込むために **LoadLibrary** Windows API を使用します。  次に、「」DllRegisterServer 関数のアドレスの取得使用 **GetProcAddress** 。  最後に、`DllRegisterServer` 関数を呼び出します。  次のコード サンプルは `hLib` がコントロール ライブラリ ハンドルを格納し、`lpDllEntryPoint`ストア「」DllRegisterServer 関数のアドレスを 1 とおりのメソッド。  
  
 [!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/CPP/mfc-activex-controls-distributing-activex-controls_1.cpp)]  
  
 コントロールを登録する利点は直接インストール時を減らす別のプロセス \(つまり、REGSVR32\) 呼び出し、読み込む必要がないことです。  また、登録はインプロセスであるため、セットアップ プログラムは、外部プロセスがあります。エラー、予想外の状況に処理できます。  
  
> [!NOTE]
>  セットアップ プログラムは、ActiveX コントロールをインストールする前に、**OleInitialize**を呼び出す必要があります。  セットアップ プログラムが終了すると、**OleUnitialize**を呼び出します。  これは、OLE システム DLL が ActiveX コントロールを登録するために適切な状態であることを確認します。  
  
 MFCx0.DLL を登録します。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)
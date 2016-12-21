---
title: "CWinApp のその他のサービス | Microsoft Docs"
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
  - "LoadStdProfileSettings"
  - "EnableShellOpen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アプリケーション オブジェクト [C++], サービス"
  - "CWinApp クラス, ファイル マネージャーでのドラッグ アンド ドロップ"
  - "CWinApp クラス, 初期化 (GDI+ を)"
  - "CWinApp クラス, 最近使ったドキュメント"
  - "CWinApp クラス, サービス"
  - "CWinApp クラス, シェル登録"
  - "ドラッグ アンド ドロップ [C++], ファイル"
  - "DragAcceptFiles メソッド"
  - "EnableShellOpen メソッド"
  - "ファイル [C++], ドラッグ アンド ドロップ"
  - "ファイル [C++], 最近使った"
  - "GDI+, 初期化 (MFC の)"
  - "GDI+, 非表示 (バックグラウンド スレッドを) [MFC]"
  - "LoadStdProfileSettings メソッド"
  - "MFC [C++], ファイルの操作"
  - "MFC [C++], 最近使ったファイルの一覧"
  - "MFC [C++], シェル登録"
  - "MRU 一覧"
  - "登録 (ファイルの種類を)"
  - "RegisterShellFileTypes メソッド"
  - "登録 [C++], シェル"
  - "レジストリ [C++], 最近使ったファイル"
  - "サービス, 提供 (CWinApp が)"
  - "シェル, 登録 (ファイルの種類を)"
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
caps.latest.revision: 10
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinApp のその他のサービス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

メッセージ ループを実行してアプリケーションを初期化し、その後にクリーンアップする機会を提供するだけでなく [CWinApp](../mfc/reference/cwinapp-class.md) は他のさまざまなサービスを提供します。  
  
##  <a name="_core_shell_registration"></a> シェル登録  
 既定では、MFC アプリケーション ウィザードのアプリケーション ファイル エクスプローラーまたはファイル マネージャーで、ダブルクリックして作成したユーザーがデータ ファイルを開くことができます。  アプリケーションが MDI アプリケーションの場合、アプリケーションで作成されるファイルの拡張を指定すると、MFC アプリケーション ウィザードは [RegisterShellFileTypes](../Topic/CWinApp::RegisterShellFileTypes.md) の呼び出しを追加し、生成したこと `InitInstance` への [CWinApp](../mfc/reference/cwinapp-class.md) の [EnableShellOpen](../Topic/CWinApp::EnableShellOpen.md) のメンバー関数をオーバーライドします。  
  
 `RegisterShellFileTypes` は ファイル エクスプローラーまたはファイル マネージャーでアプリケーションのドキュメントの種類を登録します。  関数は、Windows が管理する登録データベースにエントリを追加します。  エントリは各ドキュメントの種類を登録し、ファイルの種類と拡張子を関連付け、アプリケーションが起動するコマンド ラインを指定し、その種類のドキュメントを開くダイナミック データ エクスチェンジ \(DDE\) のコマンドを指定します。  
  
 `EnableShellOpen` は アプリケーションがファイル エクスプローラーまたはファイル マネージャーから DDE コマンドを受け取るようにユーザーが選択するファイルを表示して、プロセスを終了します。  
  
 この `CWinApp` の自動登録サポートはアプリケーションの .reg ファイルを出荷するか、特別なインストール作業を行う必要がなくなります。  
  
 \([InitInstance](../Topic/CWinApp::InitInstance.md) 関数の [GdiplusStartup](_gdiplus_FUNC_GdiplusStartup_token_input_output_) を呼び出して\) アプリケーションの GDI\+ を初期化したい場合は、GDI\+ のバックグラウンド スレッドを抑制する必要があります。  
  
 **TRUE**へ [GdiplusStartupInput](_gdiplus_STRUC_GdiplusStartupInput) 構造体の **SuppressBackgroundThread** のメンバーを設定することで、これを行うことができます。  GDI\+ のバックグラウンド スレッドを抑制する場合は、**NotificationUnhook** の **NotificationHook** と呼び出しはアプリケーションのメッセージ ループの追加と削除前に \([GdiplusStartupOutput](_gdiplus_STRUC_GdiplusStartupOutput)を参照してください\) は行う必要があります。  したがって、**GdiplusStartup** を呼び出して適切な場所とフック通知関数は次に示すように仮想関数 [CWinApp::Run](../Topic/CWinApp::Run.md)メソッドをオーバーライドして、Overload:  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/CPP/special-cwinapp-services_1.cpp)]  
  
 背景 GDI\+ のスレッドを抑制する、DDE コマンドはアプリケーションのメイン ウィンドウが作成される前に途中に挿入できます。  シェルによって発行された DDE コマンドはエラー メッセージに、途中で、中止できます。  
  
##  <a name="_core_file_manager_drag_and_drop"></a> ファイル マネージャーのドラッグ アンド ドロップ  
 ファイル マネージャーまたはファイル エクスプローラーのファイル ビュー ウィンドウからアプリケーション ウィンドウにドラッグできます。  たとえば、一つ以上のファイルは、アプリケーションがファイル名を取得し、それらのファイルの MDI 子ウィンドウを開くことができる MDI アプリケーションのメイン ウィンドウにドラッグできるようにする場合があります。  
  
 アプリケーション ファイルのドラッグ アンド ドロップを有効にするには、MFC アプリケーション ウィザードは `InitInstance`にメイン フレーム ウィンドウの [CWnd](../Topic/CWnd%20Class.md) の [DragAcceptFiles](../Topic/CWnd::DragAcceptFiles.md) メンバー関数の呼び出しを記述します。  ドラッグ アンド ドロップ機能を実装したくない場合は、その呼び出しを削除します。  
  
> [!NOTE]
>  また、ドキュメントに汎用 OLE ドラッグ アンド ドロップ機能をドラッグ データ間または内部実装できます。  詳細については、[ドラッグ アンド ドロップ \(OLE\)](../mfc/drag-and-drop-ole.md)記事を参照してください。  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> 最近使用されたドキュメントを追跡できます。  
 ユーザーがファイルを開いたり閉じたりするため、アプリケーション オブジェクトは 4 回使用されたファイルが最後に記録します。  これらのファイルの名前はファイル メニューに追加され、変更されたときに更新されます。  フレームワークは、レジストリまたはプロジェクトと同じ名前の .ini ファイルにアプリケーションが起動するときにこれらのファイル名を保存し、ファイルから読み込みます。  MFC アプリケーション ウィザードで作成する `InitInstance` のオーバーライドはレジストリまたは .ini ファイルから情報を読み込む使用したファイル名を含む [CWinApp](../mfc/reference/cwinapp-class.md) のメンバー関数 [LoadStdProfileSettings](../Topic/CWinApp::LoadStdProfileSettings.md)の呼び出しを最後に含まれています。  
  
 これらのエントリは、次の形式で格納されます。:  
  
-   Windows NT、Windows 2000 では、後で、レジストリ キー値に格納されます。  
  
-   Windows 3.x で、値は WIN.INI ファイルに格納されます。  
  
-   Windows 95 では、値は WIN.INI のキャッシュされたバージョンに格納されます。  
  
## 参照  
 [CWinApp : アプリケーション クラス](../Topic/CWinApp:%20The%20Application%20Class.md)
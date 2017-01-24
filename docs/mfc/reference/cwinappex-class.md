---
title: "CWinAppEx クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinAppEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinAppEx クラス"
ms.assetid: a3d3e053-3e22-463f-9444-c73abb1bb9d7
caps.latest.revision: 37
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinAppEx クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CWinAppEx` は、アプリケーション状態の処理、状態のレジストリへの保存、状態のレジストリからの読み込み、アプリケーション マネージャーの初期化、および同じアプリケーション マネージャーへのリンクの提供を行います。  
  
## 構文  
  
```  
class CWinAppEx : public CWinApp  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CWinAppEx::CWinAppEx](../Topic/CWinAppEx::CWinAppEx.md)|`CWinAppEx` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinAppEx::CleanState](../Topic/CWinAppEx::CleanState.md)|アプリケーションに関する情報を Windows レジストリから削除します。|  
|[CWinAppEx::EnableLoadWindowPlacement](../Topic/CWinAppEx::EnableLoadWindowPlacement.md)|アプリケーションがレジストリからメイン フレーム ウィンドウの初期のサイズと位置を読み込むかどうかを指定します。|  
|[CWinAppEx::EnableTearOffMenus](../Topic/CWinAppEx::EnableTearOffMenus.md)|アプリケーションでティアオフ メニューを有効にします。|  
|[CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md)|ユーザーがアプリケーションでカスタム メニュー コマンドを作成できるようにします。|  
|[CWinAppEx::ExitInstance](../Topic/CWinAppEx::ExitInstance.md)|アプリケーションのこのインスタンスを終了するに `Run` のメンバー関数内部から、フレームワークによって呼び出されます。  \([CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md) をオーバーライドします\)。|  
|[CWinAppEx::GetBinary](../Topic/CWinAppEx::GetBinary.md)|指定されたレジストリ値に関連付けられているバイナリ データを読み込みます。|  
|[CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md)|グローバル [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) オブジェクトへのポインターを返します。|  
|[CWinAppEx::GetDataVersion](../Topic/CWinAppEx::GetDataVersion.md)||  
|[CWinAppEx::GetDataVersionMajor](../Topic/CWinAppEx::GetDataVersionMajor.md)|Windows レジストリに保存されている、アプリケーションのメジャー バージョンを返します。|  
|[CWinAppEx::GetDataVersionMinor](../Topic/CWinAppEx::GetDataVersionMinor.md)|Windows レジストリに保存されている、アプリケーションのマイナー バージョンを返します。|  
|[CWinAppEx::GetInt](../Topic/CWinAppEx::GetInt.md)|指定された値に関連付けられている数値データをレジストリから読み込みます。|  
|[CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md)|グローバル [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md) オブジェクトへのポインターを返します。|  
|[CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md)|グローバル [CMouseManager](../../mfc/reference/cmousemanager-class.md) オブジェクトへのポインターを返します。|  
|[CWinAppEx::GetObject](../Topic/CWinAppEx::GetObject.md)|指定された値に関連付けられている `CObject` 派生データをレジストリから読み込みます。|  
|[CWinAppEx::GetRegSectionPath](../Topic/CWinAppEx::GetRegSectionPath.md)|レジストリ キーのパスである文字列を返します。  このパスでは、指定された相対パスがアプリケーション パスと連結されています。|  
|[CWinAppEx::GetRegistryBase](../Topic/CWinAppEx::GetRegistryBase.md)|アプリケーションのレジストリ パスを返します。|  
|[CWinAppEx::GetSectionBinary](../Topic/CWinAppEx::GetSectionBinary.md)|指定されたキーと値に関連付けられているバイナリ データをレジストリから読み込みます。|  
|[CWinAppEx::GetSectionInt](../Topic/CWinAppEx::GetSectionInt.md)|指定されたキーと値に関連付けられている数値データをレジストリから読み込みます。|  
|[CWinAppEx::GetSectionObject](../Topic/CWinAppEx::GetSectionObject.md)|指定されたキーと値に関連付けられている `CObject` データをレジストリから読み込みます。|  
|[CWinAppEx::GetSectionString](../Topic/CWinAppEx::GetSectionString.md)|指定されたキーと値に関連付けられている文字列データをレジストリから読み込みます。|  
|[CWinAppEx::GetShellManager](../Topic/CWinAppEx::GetShellManager.md)|グローバル [CShellManager](../../mfc/reference/cshellmanager-class.md) オブジェクトへのポインターを返します。|  
|[CWinAppEx::GetString](../Topic/CWinAppEx::GetString.md)|指定された値に関連付けられている文字列データをレジストリから読み込みます。|  
|[CWinAppEx::GetTooltipManager](../Topic/CWinAppEx::GetTooltipManager.md)|グローバル [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) オブジェクトへのポインターを返します。|  
|[CWinAppEx::GetUserToolsManager](../Topic/CWinAppEx::GetUserToolsManager.md)|グローバル [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md) オブジェクトへのポインターを返します。|  
|[CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)|`CContextMenuManager` オブジェクトを初期化します。|  
|[CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)|`CKeyboardManager` オブジェクトを初期化します。|  
|[CWinAppEx::InitMouseManager](../Topic/CWinAppEx::InitMouseManager.md)|`CMouseManager` オブジェクトを初期化します。|  
|[CWinAppEx::InitShellManager](../Topic/CWinAppEx::InitShellManager.md)|`CShellManager` クラスを初期化します。|  
|[CWinAppEx::InitTooltipManager](../Topic/CWinAppEx::InitTooltipManager.md)|`CTooltipManager` クラスを初期化します。|  
|[CWinAppEx::IsResourceSmartUpdate](../Topic/CWinAppEx::IsResourceSmartUpdate.md)||  
|[CWinAppEx::IsStateExists](../Topic/CWinAppEx::IsStateExists.md)|指定したキーがレジストリに存在するかどうかを示します。|  
|[CWinAppEx::LoadState](../Topic/CWinAppEx::LoadState.md)|レジストリからアプリケーションの状態を読み込みます。|  
|[CWinAppEx::OnAppContextHelp](../Topic/CWinAppEx::OnAppContextHelp.md)|ユーザーが **\[カスタマイズ\]** ダイアログ ボックスのコンテキスト ヘルプを要求したときに、フレームワークによって呼び出されます。|  
|[CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md)|ユーザーがアプリケーションのどこかをダブルクリックしたときにユーザー定義コマンドを呼び出します。|  
|[CWinAppEx::OnWorkspaceIdle](../Topic/CWinAppEx::OnWorkspaceIdle.md)||  
|[CWinAppEx::SaveState](../Topic/CWinAppEx::SaveState.md)|アプリケーション フレームワークの状態を Windows レジストリに書き込みます。|  
|[CWinAppEx::SetRegistryBase](../Topic/CWinAppEx::SetRegistryBase.md)|既定のレジストリ キーのパスを設定します。  このキーは、それ以降のすべてのレジストリ呼び出しのルートとして使用されます。|  
|[CWinAppEx::ShowPopupMenu](../Topic/CWinAppEx::ShowPopupMenu.md)|ポップアップ メニューを表示します。|  
|[CWinAppEx::WriteBinary](../Topic/CWinAppEx::WriteBinary.md)|バイナリ データを指定されたレジストリ値に書き込みます。|  
|[CWinAppEx::WriteInt](../Topic/CWinAppEx::WriteInt.md)|数値データを指定されたレジストリ値に書き込みます。|  
|[CWinAppEx::WriteObject](../Topic/CWinAppEx::WriteObject.md)|[CObject クラス](../Topic/CObject%20Class.md) から派生したデータを指定されたレジストリ値に書き込みます。|  
|[CWinAppEx::WriteSectionBinary](../Topic/CWinAppEx::WriteSectionBinary.md)|バイナリ データを指定されたレジストリ キーの値に書き込みます。|  
|[CWinAppEx::WriteSectionInt](../Topic/CWinAppEx::WriteSectionInt.md)|数値データを指定されたレジストリ キーの値に書き込みます。|  
|[CWinAppEx::WriteSectionObject](../Topic/CWinAppEx::WriteSectionObject.md)|`CObject` クラスから派生したデータを指定されたレジストリ キーの値に書き込みます。|  
|[CWinAppEx::WriteSectionString](../Topic/CWinAppEx::WriteSectionString.md)|文字列データを指定されたレジストリ キーの値に書き込みます。|  
|[CWinAppEx::WriteString](../Topic/CWinAppEx::WriteString.md)|文字列データを指定されたレジストリ値に書き込みます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinAppEx::LoadCustomState](../Topic/CWinAppEx::LoadCustomState.md)|アプリケーション状態が読み込まれたときに、フレームワークによって呼び出されます。|  
|[CWinAppEx::LoadWindowPlacement](../Topic/CWinAppEx::LoadWindowPlacement.md)|アプリケーションのサイズと位置をレジストリから読み込むときに、フレームワークによって呼び出されます。  読み込まれるデータには、アプリケーションが最後に閉じられたときのメイン フレームのサイズと位置が含まれています。|  
|[CWinAppEx::OnClosingMainFrame](../Topic/CWinAppEx::OnClosingMainFrame.md)|メイン フレーム ウィンドウで `WM_CLOSE` を処理するときに、フレームワークによって呼び出されます。|  
|[CWinAppEx::PreLoadState](../Topic/CWinAppEx::PreLoadState.md)|アプリケーションの状態を読み込む直前に、フレームワークによって呼び出されます。|  
|[CWinAppEx::PreSaveState](../Topic/CWinAppEx::PreSaveState.md)|アプリケーションの状態を保存する直前に、フレームワークによって呼び出されます。|  
|[CWinAppEx::ReloadWindowPlacement](../Topic/CWinAppEx::ReloadWindowPlacement.md)|指定されたウィンドウのサイズと位置をレジストリから再読み込みします。|  
|[CWinAppEx::SaveCustomState](../Topic/CWinAppEx::SaveCustomState.md)|アプリケーションの状態をレジストリに保存した後に、フレームワークによって呼び出されます。|  
|[CWinAppEx::StoreWindowPlacement](../Topic/CWinAppEx::StoreWindowPlacement.md)|メイン フレームのサイズと位置をレジストリに書き込むために、フレームワークによって呼び出されます。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CWinAppEx::m\_bForceImageReset](../Topic/CWinAppEx::m_bForceImageReset.md)|ツール バーを含むフレーム ウィンドウをフレームワークが読み込むときにすべてのツール バー イメージをリセットするかどうかを指定します。|  
  
## 解説  
 MFC フレームワークによって提供される `CWinAppEx` のクラスによって機能の多くには異なります。  `CWinAppEx` クラスは、次のどちらかの方法でアプリケーションに組み込みます。  
  
-   メイン スレッドで `CWinAppEx` クラスを構築します。  
  
-   メイン アプリケーション クラスを `CWinAppEx` から派生させます。  
  
 `CWinAppEx` をアプリケーションに組み込むと、任意のアプリケーション マネージャーを初期化できます。  アプリケーション マネージャーを使用する前には、該当する初期化メソッドを呼び出してマネージャーを初期化する必要があります。  目的のマネージャーのポインターを取得するには、関連付けられている get メソッドを呼び出します。  `CWinAppEx` クラスで管理しているアプリケーション マネージャーは、[CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)、[CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)、[CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)、[CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)、および [CMenuTearOffManager クラス](../../mfc/reference/cmenutearoffmanager-class.md)です。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 [CWinAppEx](../../mfc/reference/cwinappex-class.md)  
  
## 必要条件  
 **ヘッダー :** afxwinappex.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CWinApp クラス](../../mfc/reference/cwinapp-class.md)   
 [CMouseManager クラス](../../mfc/reference/cmousemanager-class.md)   
 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)   
 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)   
 [CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)
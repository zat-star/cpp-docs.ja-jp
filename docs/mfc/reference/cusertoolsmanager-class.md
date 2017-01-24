---
title: "CUserToolsManager クラス | Microsoft Docs"
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
  - "CUserToolsManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserToolsManager クラス"
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUserToolsManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーション内の [CUserTool クラス](../Topic/CUserTool%20Class.md) オブジェクトのコレクションを保持します。  ユーザー ツールは、外部アプリケーションを実行するメニュー項目です。  `CUserToolsManager` オブジェクトは、ユーザーまたは開発者がアプリケーションに新しいユーザー ツールを追加できるようにします。  ユーザー ツールに関連するコマンドの実行をサポートし、Windows レジストリにユーザー ツールに関する情報を保存します。  
  
## 構文  
  
```  
class CUserToolsManager : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CUserToolsManager::CUserToolsManager](../Topic/CUserToolsManager::CUserToolsManager.md)|`CUserToolsManager` を構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md)|新しいユーザー ツールを作成します。|  
|[CUserToolsManager::FindTool](../Topic/CUserToolsManager::FindTool.md)|指定したコマンド ID に関連付けられた `CMFCUserTool` オブジェクトへのポインターを返します。|  
|[CUserToolsManager::GetArgumentsMenuID](../Topic/CUserToolsManager::GetArgumentsMenuID.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[ツール\]** タブの **\[引数\]** メニューに関連付けられているリソース ID を返します。|  
|[CUserToolsManager::GetDefExt](../Topic/CUserToolsManager::GetDefExt.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[ツール\]** タブの **\[コマンド\]** フィールドで使用される、**\[ファイルを開く\]** ダイアログ ボックス \([CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md)\) の既定の拡張子を返します。|  
|[CUserToolsManager::GetFilter](../Topic/CUserToolsManager::GetFilter.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[ツール\]** タブの **\[コマンド\]** フィールドで使用される、**\[ファイルを開く\]** ダイアログ ボックス \([CFileDialog クラス](../Topic/CFileDialog%20Class.md)\) のファイル フィルターを返します。|  
|[CUserToolsManager::GetInitialDirMenuID](../Topic/CUserToolsManager::GetInitialDirMenuID.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[ツール\]** タブの **\[初期ディレクトリ\]** メニューに関連付けられているリソース ID を返します。|  
|[CUserToolsManager::GetMaxTools](../Topic/CUserToolsManager::GetMaxTools.md)|アプリケーションで割り当てることができるユーザー ツールの最大数を返します。|  
|[CUserToolsManager::GetToolsEntryCmd](../Topic/CUserToolsManager::GetToolsEntryCmd.md)|ユーザー ツールのメニュー項目プレースホルダーのコマンド ID を返します。|  
|[CUserToolsManager::GetUserTools](../Topic/CUserToolsManager::GetUserTools.md)|ユーザー ツールの一覧への参照を返します。|  
|[CUserToolsManager::InvokeTool](../Topic/CUserToolsManager::InvokeTool.md)|指定されたコマンド ID を持つユーザー ツールと関連付けるアプリケーションを実行します。|  
|[CUserToolsManager::IsUserToolCmd](../Topic/CUserToolsManager::IsUserToolCmd.md)|コマンド ID がユーザー ツールに関連付けられているかどうかを判定します。|  
|[CUserToolsManager::LoadState](../Topic/CUserToolsManager::LoadState.md)|Windows レジストリからユーザー ツールに関する情報を読み込みます。|  
|[CUserToolsManager::MoveToolDown](../Topic/CUserToolsManager::MoveToolDown.md)|指定したユーザー ツールをユーザー ツールの一覧内で下へ移動します。|  
|[CUserToolsManager::MoveToolUp](../Topic/CUserToolsManager::MoveToolUp.md)|指定したユーザー ツールをユーザー ツールの一覧内で上へ移動します。|  
|[CUserToolsManager::RemoveTool](../Topic/CUserToolsManager::RemoveTool.md)|指定されたユーザー ツールをアプリケーションから削除します。|  
|[CUserToolsManager::SaveState](../Topic/CUserToolsManager::SaveState.md)|ユーザー ツールに関する情報を Windows レジストリに格納します。|  
|[CUserToolsManager::SetDefExt](../Topic/CUserToolsManager::SetDefExt.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[ツール\]** タブの **\[コマンド\]** フィールドで使用される、**\[ファイルを開く\]** ダイアログ ボックス \([CFileDialog クラス](../Topic/CFileDialog%20Class.md)\) の既定の拡張子を指定します。|  
|[CUserToolsManager::SetFilter](../Topic/CUserToolsManager::SetFilter.md)|**\[カスタマイズ\]** ダイアログ ボックスの **\[ツール\]** タブの **\[コマンド\]** フィールドで使用される、**\[ファイルを開く\]** ダイアログ ボックス \([CFileDialog クラス](../Topic/CFileDialog%20Class.md)\) のファイル フィルターを指定します。|  
  
## 解説  
 ユーザー ツールをアプリケーションに組み込むには、次の操作を行う必要があります。  
  
 1.  ユーザー ツール メニュー エントリに使用するメニュー項目と関連コマンド ID を確保します。  
  
 2.  ユーザーがアプリケーションで定義できる各ユーザー ツールで使用する連番のコマンド ID を確保します。  
  
 3.  [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md) メソッドを呼び出し、メニュー コマンド ID、最初のユーザー ツール コマンド ID、および最後のユーザー ツール コマンド ID をパラメーターとして指定します。  
  
 1 つのアプリケーションで使用できるグローバル `CUserToolsManager` オブジェクトは 1 つです。  
  
 ユーザー ツールの例については、VisualStudioDemo サンプル プロジェクトを参照してください。  
  
## 使用例  
 次の例は、`CUserToolsManager` オブジェクトへの参照の取得方法と新しいユーザー ツールの作成方法を示しています。  このコード スニペットは [Visual Studio のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/reference/codesnippet/CPP/cusertoolsmanager-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxusertoolsmanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [CUserTool クラス](../Topic/CUserTool%20Class.md)
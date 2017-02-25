---
title: "CContextMenuManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CContextMenuManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CContextMenuManager クラス"
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CContextMenuManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CContextMenuManager` オブジェクトはショートカット メニュー \(コンテキスト メニューとも呼ばれる\) を管理します。  
  
## 構文  
  
```  
class CContextMenuManager : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CContextMenuManager::CContextMenuManager](../Topic/CContextMenuManager::CContextMenuManager.md)|`CContextMenuManager` オブジェクトを構築します。|  
|`CContextMenuManager::~CContextMenuManager`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CContextMenuManager::AddMenu](../Topic/CContextMenuManager::AddMenu.md)|新しいショートカット メニューを追加します。|  
|[CContextMenuManager::GetMenuById](../Topic/CContextMenuManager::GetMenuById.md)|指定されたリソース ID に関連付けられたメニューを識別するハンドルを返します。|  
|[CContextMenuManager::GetMenuByName](../Topic/CContextMenuManager::GetMenuByName.md)|指定されたメニュー名に一致するメニューを識別するハンドルを返します。|  
|[CContextMenuManager::GetMenuNames](../Topic/CContextMenuManager::GetMenuNames.md)|メニュー名のリストを返します。|  
|[CContextMenuManager::LoadState](../Topic/CContextMenuManager::LoadState.md)|Windows レジストリに格納されているショートカット メニューを読み込みます。|  
|[CContextMenuManager::ResetState](../Topic/CContextMenuManager::ResetState.md)|コンテキスト メニュー マネージャーからショートカット メニューを消去します。|  
|[CContextMenuManager::SaveState](../Topic/CContextMenuManager::SaveState.md)|ショートカット メニューを Windows レジストリに保存します。|  
|[CContextMenuManager::SetDontCloseActiveMenu](../Topic/CContextMenuManager::SetDontCloseActiveMenu.md)|新しいショートカット メニューを表示するときに、`CContextMenuManager` がアクティブなショートカット メニューを閉じるかどうかを制御します。|  
|[CContextMenuManager::ShowPopupMenu](../Topic/CContextMenuManager::ShowPopupMenu.md)|指定されたショートカット メニューを表示します。|  
|[CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md)|指定されたショートカット メニューを表示します。  選択されたメニュー コマンドのインデックスを返します。|  
  
## 解説  
 `CContextMenuManager` は、ショートカット メニューを管理し、それらのメニューの外観の一貫性を確保します。  
  
 `CContextMenuManager` オブジェクトは手動で作成しないでください。  アプリケーションのフレームワークにより `CContextMenuManager` オブジェクトが作成されます。  ただし、アプリケーションの初期化時に [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md) を呼び出す必要があります。  コンテキスト マネージャーを初期化したら、[CWinAppEx::GetContextMenuManager](../Topic/CWinAppEx::GetContextMenuManager.md) を使用して、アプリケーションのコンテキスト マネージャーへのポインターを取得します。  
  
 ショートカット メニューは、実行時に `AddMenu` を呼び出して作成できます。  最初にユーザー入力を受け取らずにメニューを表示する場合は、`ShowPopupMenu` を呼び出します。  メニューを作成してユーザー入力を待機する場合は、`TrackPopupMenu` を使用します。  `TrackPopupMenu` は、選択されたコマンドのインデックスを返します。ユーザーが何も選択しないで終了した場合は 0 を返します。  
  
 `CContextMenuManager` は、その状態を Windows レジストリに保存して読み込むこともできます。  
  
## 使用例  
 メニューを `CContextMenuManager` オブジェクトに追加する方法と、`CContextMenuManager` オブジェクトが新しいポップアップ メニューを表示するときにアクティブなポップアップ メニューを閉じない方法を次の例に示します。  このコード スニペットは [カスタムはページのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/CPP/ccontextmenumanager-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxcontextmenumanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitContextMenuManager](../Topic/CWinAppEx::InitContextMenuManager.md)
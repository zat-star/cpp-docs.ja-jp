---
title: "CKeyboardManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CKeyboardManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyboardManager クラス"
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CKeyboardManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メイン フレーム ウィンドウおよび子フレーム ウィンドウのショートカット キーのテーブルを管理します。  
  
## 構文  
  
```  
class CKeyboardManager : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CKeyboardManager::CKeyboardManager](../Topic/CKeyboardManager::CKeyboardManager.md)|`CKeyboardManager` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CKeyboardManager::CleanUp](../Topic/CKeyboardManager::CleanUp.md)|ショートカット キー テーブルを消去します。|  
|[CKeyboardManager::FindDefaultAccelerator](../Topic/CKeyboardManager::FindDefaultAccelerator.md)|指定されたコマンドおよびウィンドウの既定のショートカット キーを取得します。|  
|[CKeyboardManager::IsKeyHandled](../Topic/CKeyboardManager::IsKeyHandled.md)|キーがアクセラレータ テーブルで処理されるかどうかを確認します。|  
|[CKeyboardManager::IsKeyPrintable](../Topic/CKeyboardManager::IsKeyPrintable.md)|文字が印刷可能かどうかを示します。|  
|[CKeyboardManager::IsShowAllAccelerators](../Topic/CKeyboardManager::IsShowAllAccelerators.md)|メニューにコマンドのすべてのショートカット キーが表示されるか、または既定のショートカット キーのみが表示されるかを示します。|  
|[CKeyboardManager::LoadState](../Topic/CKeyboardManager::LoadState.md)|Windows レジストリからショートカット キーのテーブルを読み込みます。|  
|[CKeyboardManager::ResetAll](../Topic/CKeyboardManager::ResetAll.md)|アプリケーション リソースからショートカット キーの一覧を再読み込みします。|  
|[CKeyboardManager::SaveState](../Topic/CKeyboardManager::SaveState.md)|ショートカット キーの一覧を Windows レジストリに保存します。|  
|[CKeyboardManager::ShowAllAccelerators](../Topic/CKeyboardManager::ShowAllAccelerators.md)|フレームワークがすべてのコマンドのすべてのショートカット キーを表示するか、または各コマンドの 1 つのショートカット キーのみを表示するかを示します。  このメソッドは、関連付けられたショートカット キーが 1 つしかないコマンドには影響を与えません。|  
|[CKeyboardManager::TranslateCharToUpper](../Topic/CKeyboardManager::TranslateCharToUpper.md)|文字を大文字レジスタに変換します。|  
|[CKeyboardManager::UpdateAccelTable](../Topic/CKeyboardManager::UpdateAccelTable.md)|ショートカット キー テーブルを新しいショートカット キー テーブルで更新します。|  
  
## 解説  
 このクラスのメンバーを使用すると、ショートカット キー テーブルを Windows レジストリに保存して読み込んだり、テンプレートを使用してショートカット キー テーブルを更新したり、フレーム ウィンドウでコマンドの既定のショートカット キーを見つけることができます。  加えて、`CKeyboardManager` オブジェクトを使用すると、ショートカット キーがユーザーに表示される方法を制御できます。  
  
 `CKeyboardManager` オブジェクトは手動で作成しないでください。  アプリケーションのフレームワークによって自動的に作成されます。  ただし、アプリケーションの初期化中には [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md) を呼び出す必要があります。  アプリケーションのキーボード マネージャーへのポインターを取得するには、[CWinAppEx::GetKeyboardManager](../Topic/CWinAppEx::GetKeyboardManager.md) を呼び出します。  
  
## 使用例  
 `CKeyboardManager` オブジェクトへのポインターを `CWinAppEx` クラスから取得する方法と、メニュー コマンドに関連付けられたすべてのショートカット キーを表示する方法を次の例に示します。  このコード スニペットは [カスタムはページのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/CPP/ckeyboardmanager-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxkeyboardmanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md)   
 [キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)
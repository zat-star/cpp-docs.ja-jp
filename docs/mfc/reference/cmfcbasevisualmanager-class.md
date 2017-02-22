---
title: "CMFCBaseVisualManager クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCBaseVisualManager"
  - "CMFCBaseVisualManager.~CMFCBaseVisualManager"
  - "~CMFCBaseVisualManager"
  - "CMFCBaseVisualManager::~CMFCBaseVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~CMFCBaseVisualManager デストラクター"
  - "CMFCBaseVisualManager クラス"
  - "CMFCBaseVisualManager クラス, デストラクター"
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMFCBaseVisualManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

派生ビジュアル マネージャーと Windows テーマ API の間のレイヤー。  
  
 `CMFCBaseVisualManager` は、使用可能であれば UxTheme.dll を読み込み、Windows テーマ API メソッドへのアクセスを管理します。  
  
 このクラスは内部でのみ使用します。  
  
## 構文  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](../Topic/CMFCBaseVisualManager::CMFCBaseVisualManager.md)|`CMFCBaseVisualManager` オブジェクトを構築し、初期化します。|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|デストラクターです。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::DrawCheckBox](../Topic/CMFCBaseVisualManager::DrawCheckBox.md)|現在の Windows テーマを使用してチェック ボックス コントロールを描画します。|  
|[CMFCBaseVisualManager::DrawComboBorder](../Topic/CMFCBaseVisualManager::DrawComboBorder.md)|現在の Windows テーマを使用してコンボ ボックスの境界線を描画します。|  
|[CMFCBaseVisualManager::DrawComboDropButton](../Topic/CMFCBaseVisualManager::DrawComboDropButton.md)|現在の Windows テーマを使用してコンボ ボックスのドロップダウン ボタンを描画します。|  
|[CMFCBaseVisualManager::DrawPushButton](../Topic/CMFCBaseVisualManager::DrawPushButton.md)|現在の Windows テーマを使用してプッシュ ボタンを描画します。|  
|[CMFCBaseVisualManager::DrawRadioButton](../Topic/CMFCBaseVisualManager::DrawRadioButton.md)|現在の Windows テーマを使用してオプション ボタン コントロールを描画します。|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](../Topic/CMFCBaseVisualManager::DrawStatusBarProgress.md)|現在の Windows テーマを使用して、ステータス バー コントロール \([CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)\) 上にプログレス バーを描画します。|  
|[CMFCBaseVisualManager::FillReBarPane](../Topic/CMFCBaseVisualManager::FillReBarPane.md)|現在の Windows のテーマを使用して rebar コントロールの背景を塗りつぶします。|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](../Topic/CMFCBaseVisualManager::GetStandardWindowsTheme.md)|現在の Windows テーマを取得します。|  
  
### プロテクト メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::CleanUpThemes](../Topic/CMFCBaseVisualManager::CleanUpThemes.md)|`UpdateSystemColors` で取得したすべてのハンドルの `CloseThemeData` を呼び出します。|  
|[CMFCBaseVisualManager::UpdateSystemColors](../Topic/CMFCBaseVisualManager::UpdateSystemColors.md)|`OpenThemeData` を呼び出して、さまざまなコントロール \(ウィンドウ、ツール バー、ボタンなど\) を描画するためのハンドルを取得します。|  
  
## 解説  
 このクラスのオブジェクトを直接インスタンス化する必要はありません。  
  
 このクラスはすべてのビジュアル マネージャーの基本クラスであるため、[CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md) を呼び出して、現在のビジュアル マネージャーへのポインターを取得し、そのポインターを使用して `CMFCBaseVisualManager` のメソッドにアクセスできます。  ただし、現在の Windows テーマを使用してコントロールを表示する必要がある場合は、`CMFCVisualManagerWindows` インターフェイスを使用することをお勧めします。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## 必要条件  
 **ヘッダー :** afxvisualmanager.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)
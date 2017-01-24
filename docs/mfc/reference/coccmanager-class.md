---
title: "COccManager クラス | Microsoft Docs"
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
  - "COccManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール コンテナー [C++], コントロール サイト"
  - "CNoTrackObject クラス"
  - "COccManager クラス"
  - "カスタム コントロール [MFC], サイト"
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COccManager クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`COleControlContainer` オブジェクトと `COleControlSite` オブジェクトによって実装されるさまざまなカスタム コントロール サイトを管理します。  
  
## 構文  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COccManager::CreateContainer](../Topic/COccManager::CreateContainer.md)|**COleContainer** のオブジェクトを作成します。|  
|[COccManager::CreateDlgControls](../Topic/COccManager::CreateDlgControls.md)|`COleContainer` に関連付けられたオブジェクトによってホストされる ActiveX コントロールを作成します。|  
|[COccManager::CreateSite](../Topic/COccManager::CreateSite.md)|`COleClientSite` オブジェクトを作成します。|  
|[COccManager::GetDefBtnCode](../Topic/COccManager::GetDefBtnCode.md)|既定のボタンのコードを取得します。|  
|[COccManager::IsDialogMessage](../Topic/COccManager::IsDialogMessage.md)|メッセージ ダイアログのターゲットを決定します。|  
|[COccManager::IsLabelControl](../Topic/COccManager::IsLabelControl.md)|指定したコントロールにラベル コントロールであるかどうかを判定します。|  
|[COccManager::IsMatchingMnemonic](../Topic/COccManager::IsMatchingMnemonic.md)|現在のニーモニックが特定のコントロールのニーモニックと一致するかどうかを判定します。|  
|[COccManager::OnEvent](../Topic/COccManager::OnEvent.md)|指定されたイベントを処理します。|  
|[COccManager::PostCreateDialog](../Topic/COccManager::PostCreateDialog.md)|ダイアログの作成時に割り当てられたリソースを解放します。|  
|[COccManager::PreCreateDialog](../Topic/COccManager::PreCreateDialog.md)|ActiveX コントロールのダイアログ テンプレートを処理します。|  
|[COccManager::SetDefaultButton](../Topic/COccManager::SetDefaultButton.md)|指定したコントロールの既定の状態を切り替えます。|  
|[COccManager::SplitDialogTemplate](../Topic/COccManager::SplitDialogTemplate.md)|指定されたダイアログ テンプレートのコモン コントロールから既存の ActiveX コントロールを区切ります。|  
  
## 解説  
 基本クラス、**CNoTrackObject**は、非公開基本クラス \(AFXTLS.H にある\) です。  MFC フレームワークによって使用されるようにデザインされている **CNoTrackObject** のクラスから派生したクラスは、メモリ リークの検出は適用されません。  **CNoTrackObject**から直接派生させることはお勧めできません。  
  
## 継承階層  
 `CNoTrackObject`  
  
 `COccManager`  
  
## 必要条件  
 **ヘッダー :** afxocc.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleControlSite クラス](../../mfc/reference/colecontrolsite-class.md)   
 [COleControlContainer クラス](../../mfc/reference/colecontrolcontainer-class.md)
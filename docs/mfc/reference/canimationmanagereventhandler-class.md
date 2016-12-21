---
title: "CAnimationManagerEventHandler クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationManagerEventHandler"
  - "CAnimationManagerEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationManagerEventHandler クラス"
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationManagerEventHandler クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーション マネージャーのステータスの変更時に Animation API によって呼び出されるコールバックを実装します。  
  
## 構文  
  
```  
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](../Topic/CAnimationManagerEventHandler::CAnimationManagerEventHandler.md)|`CAnimationManagerEventHandler` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationManagerEventHandler::CreateInstance](../Topic/CAnimationManagerEventHandler::CreateInstance.md)|`CAnimationManagerEventHandler` オブジェクトのインスタンスを作成します。|  
|[CAnimationManagerEventHandler::OnManagerStatusChanged](../Topic/CAnimationManagerEventHandler::OnManagerStatusChanged.md)|アニメーション マネージャーのステータスが変化したときに呼び出されます。  \(`CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged` をオーバーライドします。\)|  
|[CAnimationManagerEventHandler::SetAnimationController](../Topic/CAnimationManagerEventHandler::SetAnimationController.md)|イベントをルーティングするアニメーション コントローラーへのポインターを格納します。|  
  
## 解説  
 このイベント ハンドラーは、CAnimationController::EnableAnimationManagerEvent を呼び出すと作成され、IUIAnimationManager::SetManagerEventHandler メソッドに渡されます。  
  
## 継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationManagerEventHandlerBase`  
  
 `CAnimationManagerEventHandler`  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
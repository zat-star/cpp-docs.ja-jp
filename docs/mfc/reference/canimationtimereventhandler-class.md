---
title: "CAnimationTimerEventHandler クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationTimerEventHandler"
  - "CAnimationTimerEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationTimerEventHandler クラス"
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CAnimationTimerEventHandler クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

タイミング イベントの発生時に Animation API によって呼び出されるコールバックを実装します。  
  
## 構文  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationTimerEventHandler::CreateInstance](../Topic/CAnimationTimerEventHandler::CreateInstance.md)|`CAnimationTimerEventHandler` のコールバックのインスタンスを作成します。|  
|[CAnimationTimerEventHandler::OnPostUpdate](../Topic/CAnimationTimerEventHandler::OnPostUpdate.md)|アニメーションの更新の完了後に発生するイベントを処理します。  \(`CUIAnimationTimerEventHandlerBase::OnPostUpdate` をオーバーライドします。\)|  
|[CAnimationTimerEventHandler::OnPreUpdate](../Topic/CAnimationTimerEventHandler::OnPreUpdate.md)|アニメーションの更新の開始前に発生するイベントを処理します。  \(`CUIAnimationTimerEventHandlerBase::OnPreUpdate` をオーバーライドします。\)|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](../Topic/CAnimationTimerEventHandler::OnRenderingTooSlow.md)|アニメーションのレンダリング フレーム レートが推奨されるフレーム レートの最小値を下回ったときに発生するイベントを処理します。  \(`CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow` をオーバーライドします。\)|  
|[CAnimationTimerEventHandler::SetAnimationController](../Topic/CAnimationTimerEventHandler::SetAnimationController.md)|イベントをルーティングするアニメーション コントローラーへのポインターを格納します。|  
  
## 解説  
 このイベント ハンドラーは、CAnimationController::EnableAnimationTimerEventHandler を呼び出すと作成され、IUIAnimationTimer::SetTimerEventHandler に渡されます。  
  
## 継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
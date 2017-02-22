---
title: "CAnimationStoryboardEventHandler クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationStoryboardEventHandler"
  - "CAnimationStoryboardEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationStoryboardEventHandler クラス"
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CAnimationStoryboardEventHandler クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストーリーボードのステータスの変更時またはストーリーボードの更新時に Animation API によって呼び出されるコールバックを実装します。  
  
## 構文  
  
```  
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](../Topic/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler.md)|`CAnimationStoryboardEventHandler` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationStoryboardEventHandler::CreateInstance](../Topic/CAnimationStoryboardEventHandler::CreateInstance.md)|`CAnimationStoryboardEventHandler` のコールバックのインスタンスを作成します。|  
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](../Topic/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged.md)|ストーリーボードのステータスが変化したときに発生する `OnStoryboardStatusChanged` イベントを処理します \(をオーバーライド `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`\)。|  
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](../Topic/CAnimationStoryboardEventHandler::OnStoryboardUpdated.md)|ストーリーボードの更新時に発生 `OnStoryboardUpdated` イベントを処理します \(をオーバーライド `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`\)。|  
|[CAnimationStoryboardEventHandler::SetAnimationController](../Topic/CAnimationStoryboardEventHandler::SetAnimationController.md)|イベントをルーティングするアニメーション コントローラーへのポインターを格納します。|  
  
## 解説  
 このイベント ハンドラーは `IUIAnimationStoryboard::SetStoryboardEventHandler` に `CAnimationController::EnableStoryboardEventHandler`を呼び出すと作成され、メソッドに渡されます。  
  
## 継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationStoryboardEventHandlerBase`  
  
 `CAnimationStoryboardEventHandler`  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
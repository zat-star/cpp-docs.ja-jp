---
title: "CAnimationVariableIntegerChangeHandler クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationVariableIntegerChangeHandler"
  - "CAnimationVariableIntegerChangeHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariableIntegerChangeHandler クラス"
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CAnimationVariableIntegerChangeHandler クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーション変数の値が変化したときに Animation API によって呼び出されるコールバックを実装します。  
  
## 構文  
  
```  
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](../Topic/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler.md)|`CAnimationVariableIntegerChangeHandler` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationVariableIntegerChangeHandler::CreateInstance](../Topic/CAnimationVariableIntegerChangeHandler::CreateInstance.md)|`CAnimationVariableIntegerChangeHandler` のコールバックのインスタンスを作成します。|  
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](../Topic/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged.md)|アニメーション変数の値が変化したときに呼び出されます。  \(`CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged` をオーバーライドします。\)|  
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](../Topic/CAnimationVariableIntegerChangeHandler::SetAnimationController.md)|イベントをルーティングするアニメーション コントローラーへのポインターを格納します。|  
  
## 解説  
 このイベント ハンドラーは、CAnimationVariable::EnableIntegerValueChangedEvent または CAnimationBaseObject::EnableIntegerValueChangedEvent \(アニメーション オブジェクトにカプセル化されたすべてのアニメーション変数に対してこのイベントを有効にするメソッド\) を呼び出すと作成され、IUIAnimationVariable::SetVariableIntegerChangeHandler メソッドに渡されます。  
  
## 継承階層  
 [MFC クラス](../Topic/MFC%20Classes.md)  
  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableIntegerChangeHandlerBase`  
  
 `CAnimationVariableIntegerChangeHandler`  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
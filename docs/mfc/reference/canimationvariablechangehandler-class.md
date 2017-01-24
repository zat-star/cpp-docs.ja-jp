---
title: "CAnimationVariableChangeHandler クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationVariableChangeHandler"
  - "CAnimationVariableChangeHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariableChangeHandler クラス"
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationVariableChangeHandler クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーション変数の値が変化したときに Animation API によって呼び出されるコールバックを実装します。  
  
## 構文  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|`CAnimationVariableChangeHandler` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CAnimationVariableChangeHandler::CreateInstance`|`CAnimationVariableChangeHandler` オブジェクトのインスタンスを作成します。|  
|[CAnimationVariableChangeHandler::OnValueChanged](../Topic/CAnimationVariableChangeHandler::OnValueChanged.md)|アニメーション変数の値が変化したときに呼び出されます。  \(`CUIAnimationVariableChangeHandlerBase::OnValueChanged` をオーバーライドします。\)|  
|[CAnimationVariableChangeHandler::SetAnimationController](../Topic/CAnimationVariableChangeHandler::SetAnimationController.md)|イベントをルーティングするアニメーション コントローラーへのポインターを格納します。|  
  
## 解説  
 このイベント ハンドラーは `IUIAnimationVariable::SetVariableChangeHandler` に \(アニメーション オブジェクトにカプセル化されたすべてのアニメーション変数に対してこのイベントを有効にするか `CAnimationBaseObject::EnableValueChangedEvent``CAnimationVariable::EnableValueChangedEvent` \) を呼び出すと作成され、メソッドに渡されます。  
  
## 継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
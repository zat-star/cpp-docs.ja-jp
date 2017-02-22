---
title: "CInterpolatorBase クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CInterpolatorBase"
  - "CInterpolatorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterpolatorBase クラス"
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CInterpolatorBase クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーション変数の新しい値を計算する必要があるときに、Animation API によって呼び出されるコールバックを実装します。  
  
## 構文  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CInterpolatorBase::CInterpolatorBase](../Topic/CInterpolatorBase::CInterpolatorBase.md)|`CInterpolatorBase` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CInterpolatorBase::CreateInstance](../Topic/CInterpolatorBase::CreateInstance.md)|`CInterpolatorBase` のインスタンスを作成し、イベントを処理するカスタムのインターポレータへのポインターを格納します。|  
|[CInterpolatorBase::GetDependencies](../Topic/CInterpolatorBase::GetDependencies.md)|インターポレータの依存関係を取得します   \(`CUIAnimationInterpolatorBase::GetDependencies` をオーバーライドします。\)|  
|[CInterpolatorBase::GetDuration](../Topic/CInterpolatorBase::GetDuration.md)|インターポレータの継続時間を取得します   \(`CUIAnimationInterpolatorBase::GetDuration` をオーバーライドします。\)|  
|[CInterpolatorBase::GetFinalValue](../Topic/CInterpolatorBase::GetFinalValue.md)|インターポレータによる最終値を取得します   \(`CUIAnimationInterpolatorBase::GetFinalValue` をオーバーライドします。\)|  
|[CInterpolatorBase::InterpolateValue](../Topic/CInterpolatorBase::InterpolateValue.md)|補間します。指定したオフセット位置 \(をオーバーライドします。\) に値を `CUIAnimationInterpolatorBase::InterpolateValue`|  
|[CInterpolatorBase::InterpolateVelocity](../Topic/CInterpolatorBase::InterpolateVelocity.md)|補間します \(をオーバーライド指定したオフセット位置で速度を `CUIAnimationInterpolatorBase::InterpolateVelocity`。|  
|[CInterpolatorBase::SetCustomInterpolator](../Topic/CInterpolatorBase::SetCustomInterpolator.md)|イベントを処理するカスタムのインターポレータへのポインターを格納します。|  
|[CInterpolatorBase::SetDuration](../Topic/CInterpolatorBase::SetDuration.md)|インターポレータの継続時間を `CUIAnimationInterpolatorBase::SetDuration` \(をオーバーライドします。\)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](../Topic/CInterpolatorBase::SetInitialValueAndVelocity.md)|インターポレータの初期値および初期速度を設定します   \(`CUIAnimationInterpolatorBase::SetInitialValueAndVelocity` をオーバーライドします。\)|  
  
## 解説  
 このハンドラーは `IUIAnimationTransitionFactory::CreateTransition` に `CCustomTransition` のオブジェクトとしてアニメーションの初期化処理の一環作成されるときに作成され、渡されます \( `CAnimationController::AnimateGroup`が開始される\)   通常 `CCustomInterpolator`に、すべてのイベントをルーティングするだけ\-ポインターが `CCustomTransition`のコンストラクターに渡される派生クラスにこのクラスを直接使用する必要はありません。  
  
## 継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
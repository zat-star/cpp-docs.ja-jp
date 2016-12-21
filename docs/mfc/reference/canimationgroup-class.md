---
title: "CAnimationGroup クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationGroup"
  - "CAnimationGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationGroup クラス"
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationGroup クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーションを定義するアニメーション ストーリーボード、アニメーション オブジェクト、および遷移を組み合わせたアニメーション グループを実装します。  
  
## 構文  
  
```  
class CAnimationGroup;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationGroup::CAnimationGroup](../Topic/CAnimationGroup::CAnimationGroup.md)|アニメーション グループを構築します。|  
|[CAnimationGroup::~CAnimationGroup](../Topic/CAnimationGroup::~CAnimationGroup.md)|デストラクターです。  アニメーション グループが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationGroup::Animate](../Topic/CAnimationGroup::Animate.md)|グループをアニメーション化します。|  
|[CAnimationGroup::ApplyTransitions](../Topic/CAnimationGroup::ApplyTransitions.md)|アニメーション オブジェクトに遷移を適用します。|  
|[CAnimationGroup::FindAnimationObject](../Topic/CAnimationGroup::FindAnimationObject.md)|指定したアニメーション変数が格納されたアニメーション オブジェクトを検索します。|  
|[CAnimationGroup::GetGroupID](../Topic/CAnimationGroup::GetGroupID.md)|GroupID を返します。|  
|[CAnimationGroup::RemoveKeyframes](../Topic/CAnimationGroup::RemoveKeyframes.md)|アニメーション グループに属するすべてのキーフレームを削除します。必要に応じて破棄することもできます。|  
|[CAnimationGroup::RemoveTransitions](../Topic/CAnimationGroup::RemoveTransitions.md)|アニメーション グループに属するアニメーション オブジェクトから遷移を削除します。|  
|[CAnimationGroup::Schedule](../Topic/CAnimationGroup::Schedule.md)|指定した時刻にアニメーションをスケジュールします。|  
|[CAnimationGroup::SetAutodestroyTransitions](../Topic/CAnimationGroup::SetAutodestroyTransitions.md)|グループに属するすべてのアニメーション オブジェクトに対し、遷移を自動的に破棄するように指示します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationGroup::AddKeyframes](../Topic/CAnimationGroup::AddKeyframes.md)|ストーリーボードにキーフレームを追加するヘルパー。|  
|[CAnimationGroup::AddTransitions](../Topic/CAnimationGroup::AddTransitions.md)|ストーリーボードに遷移を追加するヘルパー。|  
|[CAnimationGroup::CreateTransitions](../Topic/CAnimationGroup::CreateTransitions.md)|COM 遷移オブジェクトを作成するヘルパー。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationGroup::m\_bAutoclearTransitions](../Topic/CAnimationGroup::m_bAutoclearTransitions.md)|グループに属するアニメーション オブジェクトから遷移をクリアする方法を指定します。  このメンバーが TRUE の場合、アニメーションがスケジュールされたときに自動的に遷移が削除されます。  それ以外の場合、遷移は手動で削除する必要があります。|  
|[CAnimationGroup::m\_bAutodestroyAnimationObjects](../Topic/CAnimationGroup::m_bAutodestroyAnimationObjects.md)|アニメーション オブジェクトを破棄する方法を指定します。  このパラメーターが TRUE の場合、グループが破棄されるときに自動的にアニメーション オブジェクトが破棄されます。  それ以外の場合、アニメーション オブジェクトは手動で破棄する必要があります。  既定値は FALSE です。  この値は、グループに属するすべてのアニメーション オブジェクトが new 演算子を使用して動的に割り当てられる場合にのみ TRUE に設定します。|  
|[CAnimationGroup::m\_bAutodestroyKeyframes](../Topic/CAnimationGroup::m_bAutodestroyKeyframes.md)|キーフレームを破棄する方法を指定します。  この値が TRUE の場合、すべてのキーフレームが削除および破棄されます。それ以外の場合は、リストからのみ削除されます。  既定値は TRUE です。|  
|[CAnimationGroup::m\_lstAnimationObjects](../Topic/CAnimationGroup::m_lstAnimationObjects.md)|アニメーション オブジェクトのリストを格納します。|  
|[CAnimationGroup::m\_lstKeyFrames](../Topic/CAnimationGroup::m_lstKeyFrames.md)|キーフレームのリストを格納します。|  
|[CAnimationGroup::m\_pStoryboard](../Topic/CAnimationGroup::m_pStoryboard.md)|アニメーションのストーリーボードへのポインター。  このポインターは、Animate で呼び出すまでは有効になりません。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationGroup::m\_nGroupID](../Topic/CAnimationGroup::m_nGroupID.md)|アニメーション グループの一意の ID。|  
|[CAnimationGroup::m\_pParentController](../Topic/CAnimationGroup::m_pParentController.md)|このグループが属するアニメーション コントローラーへのポインター。|  
  
## 解説  
 アニメーション グループは、CAnimationController::AddAnimationObject を使用してアニメーション オブジェクトを追加するとアニメーション コントローラー \(CAnimationController\) で自動的に作成されます。  アニメーション グループは GroupID で識別され、通常は GroupID をパラメーターとして使用して操作されます。  GroupID は、新しいアニメーション グループに追加された最初のアニメーション オブジェクトから取得されます。  カプセル化されたアニメーション ストーリーボードは、CAnimationController::AnimateGroup を呼び出した後に作成され、パブリック メンバーの m\_pStoryboard を使用してアクセスできます。  
  
## 継承階層  
 [CAnimationGroup](../../mfc/reference/canimationgroup-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
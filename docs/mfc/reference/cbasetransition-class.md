---
title: "CBaseTransition クラス | Microsoft Docs"
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
  - "CBaseTransition"
  - "afxanimationcontroller/CBaseTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTransition クラス"
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBaseTransition クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

基本遷移を表します。  
  
## 構文  
  
```  
class CBaseTransition : public CObject;  
```  
  
## メンバー  
  
### パブリック列挙型  
  
|名前|説明|  
|--------|--------|  
|[CBaseTransition::TRANSITION\_TYPE 列挙型](../Topic/CBaseTransition::TRANSITION_TYPE%20Enumeration.md)|Windows Animation API の MFC 実装で現在サポートされている遷移の種類を定義します。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CBaseTransition::CBaseTransition](../Topic/CBaseTransition::CBaseTransition.md)|基本遷移オブジェクトを構築します。|  
|[CBaseTransition::~CBaseTransition](../Topic/CBaseTransition::~CBaseTransition.md)|デストラクターです。  遷移オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CBaseTransition::AddToStoryboard](../Topic/CBaseTransition::AddToStoryboard.md)|ストーリーボードに遷移を追加します。|  
|[CBaseTransition::AddToStoryboardAtKeyframes](../Topic/CBaseTransition::AddToStoryboardAtKeyframes.md)|ストーリーボードに遷移を追加します。|  
|[CBaseTransition::Clear](../Topic/CBaseTransition::Clear.md)|カプセル化された IUIAnimationTransition COM オブジェクトを解放します。|  
|[CBaseTransition::Create](../Topic/CBaseTransition::Create.md)|COM 遷移を作成します。|  
|[CBaseTransition::GetEndKeyframe](../Topic/CBaseTransition::GetEndKeyframe.md)|開始キーフレームを返します。|  
|[CBaseTransition::GetRelatedVariable](../Topic/CBaseTransition::GetRelatedVariable.md)|関連する変数へのポインターを返します。|  
|[CBaseTransition::GetStartKeyframe](../Topic/CBaseTransition::GetStartKeyframe.md)|開始キーフレームを返します。|  
|[CBaseTransition::GetTransition](../Topic/CBaseTransition::GetTransition.md)|オーバーロードされます。  基になる COM 遷移オブジェクトへのポインターを返します。|  
|[CBaseTransition::GetType](../Topic/CBaseTransition::GetType.md)|遷移の種類を返します。|  
|[CBaseTransition::IsAdded](../Topic/CBaseTransition::IsAdded.md)|ストーリーボードに遷移が追加されているかどうかを示します。|  
|[CBaseTransition::SetKeyframes](../Topic/CBaseTransition::SetKeyframes.md)|遷移のキーフレームを設定します。|  
|[CBaseTransition::SetRelatedVariable](../Topic/CBaseTransition::SetRelatedVariable.md)|アニメーション変数と遷移の関係を確立します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CBaseTransition::m\_bAdded](../Topic/CBaseTransition::m_bAdded.md)|ストーリーボードに遷移が追加されているかどうかを示します。|  
|[CBaseTransition::m\_pEndKeyframe](../Topic/CBaseTransition::m_pEndKeyframe.md)|遷移の終了を指定するキーフレームへのポインターを格納します。|  
|[CBaseTransition::m\_pRelatedVariable](../Topic/CBaseTransition::m_pRelatedVariable.md)|m\_transition に格納された遷移を使用してアニメーション化されるアニメーション変数へのポインター。|  
|[CBaseTransition::m\_pStartKeyframe](../Topic/CBaseTransition::m_pStartKeyframe.md)|遷移の開始を指定するキーフレームへのポインターを格納します。|  
|[CBaseTransition::m\_transition](../Topic/CBaseTransition::m_transition.md)|IUIAnimationTransition へのポインターを格納します。  COM 遷移オブジェクトが作成されていない場合は NULL になります。|  
|[CBaseTransition::m\_type](../Topic/CBaseTransition::m_type.md)|遷移の種類を格納します。|  
  
## 解説  
 このクラスは、IUIAnimationTransition インターフェイスをカプセル化し、すべての遷移の基本クラスとして機能します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
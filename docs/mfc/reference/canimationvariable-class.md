---
title: "CAnimationVariable クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationVariable"
  - "afxanimationcontroller/CAnimationVariable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariable クラス"
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationVariable クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーション変数を表します。  
  
## 構文  
  
```  
class CAnimationVariable;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationVariable::CAnimationVariable](../Topic/CAnimationVariable::CAnimationVariable.md)|アニメーション変数オブジェクトを構築します。|  
|[CAnimationVariable::~CAnimationVariable](../Topic/CAnimationVariable::~CAnimationVariable.md)|デストラクターです。  CAnimationVariable オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationVariable::AddTransition](../Topic/CAnimationVariable::AddTransition.md)|遷移を追加します。|  
|[CAnimationVariable::ApplyTransitions](../Topic/CAnimationVariable::ApplyTransitions.md)|内部リストからストーリーボードに遷移を追加します。|  
|[CAnimationVariable::ClearTransitions](../Topic/CAnimationVariable::ClearTransitions.md)|遷移をクリアします。|  
|[CAnimationVariable::Create](../Topic/CAnimationVariable::Create.md)|基になるアニメーション変数 COM オブジェクトを作成します。|  
|[CAnimationVariable::CreateTransitions](../Topic/CAnimationVariable::CreateTransitions.md)|このアニメーション変数に適用するすべての遷移を作成します。|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](../Topic/CAnimationVariable::EnableIntegerValueChangedEvent.md)|IntegerValueChanged イベントを有効または無効にします。|  
|[CAnimationVariable::EnableValueChangedEvent](../Topic/CAnimationVariable::EnableValueChangedEvent.md)|ValueChanged イベントを有効または無効にします。|  
|[CAnimationVariable::GetDefaultValue](../Topic/CAnimationVariable::GetDefaultValue.md)|既定値を返します。|  
|[CAnimationVariable::GetParentAnimationObject](../Topic/CAnimationVariable::GetParentAnimationObject.md)|親アニメーション オブジェクトを返します。|  
|[CAnimationVariable::GetValue](../Topic/CAnimationVariable::GetValue.md)|オーバーロードされます。  アニメーション変数の現在の値を返します。|  
|[CAnimationVariable::GetVariable](../Topic/CAnimationVariable::GetVariable.md)|IUIAnimationVariable COM オブジェクトへのポインターを返します。|  
|[CAnimationVariable::SetDefaultValue](../Topic/CAnimationVariable::SetDefaultValue.md)|既定値を設定し、IUIAnimationVariable COM オブジェクトを解放します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationVariable::SetParentAnimationObject](../Topic/CAnimationVariable::SetParentAnimationObject.md)|アニメーション変数とアニメーション オブジェクトの関係を設定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationVariable::m\_bAutodestroyTransitions](../Topic/CAnimationVariable::m_bAutodestroyTransitions.md)|関連する遷移オブジェクトを破棄するかどうかを指定します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationVariable::m\_dblDefaultValue](../Topic/CAnimationVariable::m_dblDefaultValue.md)|IUIAnimationVariable に反映される既定値を指定します。|  
|[CAnimationVariable::m\_lstTransitions](../Topic/CAnimationVariable::m_lstTransitions.md)|このアニメーション変数をアニメーション化する遷移のリストを格納します。|  
|[CAnimationVariable::m\_pParentObject](../Topic/CAnimationVariable::m_pParentObject.md)|このアニメーション変数をカプセル化するアニメーション オブジェクトへのポインター。|  
|[CAnimationVariable::m\_variable](../Topic/CAnimationVariable::m_variable.md)|IUIAnimationVariable COM オブジェクトへのポインターを格納します。  COM オブジェクトがまだ作成されていない場合、または作成に失敗した場合は、NULL になります。|  
  
## 解説  
 CAnimationVariable クラスは、IUIAnimationVariable COM オブジェクトをカプセル化します。  また、ストーリーボードのアニメーション変数に適用する遷移の内部リストも保持します。  CAnimationVariable オブジェクトは、アニメーション オブジェクトに埋め込まれ、アニメーション化された値、点、サイズ、色、および四角形をアプリケーションで表すことができます。  
  
## 継承階層  
 [CAnimationVariable](../../mfc/reference/canimationvariable-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
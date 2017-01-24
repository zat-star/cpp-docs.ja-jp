---
title: "CAnimationBaseObject クラス | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationBaseObject"
  - "CAnimationBaseObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationBaseObject クラス"
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationBaseObject クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

すべてのアニメーション オブジェクトの基本クラスです。  
  
## 構文  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationBaseObject::CAnimationBaseObject](../Topic/CAnimationBaseObject::CAnimationBaseObject.md)|オーバーロードされます。  アニメーション オブジェクトを構築します。|  
|[CAnimationBaseObject::~CAnimationBaseObject](../Topic/CAnimationBaseObject::~CAnimationBaseObject.md)|デストラクターです。  アニメーション オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationBaseObject::ApplyTransitions](../Topic/CAnimationBaseObject::ApplyTransitions.md)|カプセル化されたアニメーション変数と共に遷移をストーリーボードに追加します。|  
|[CAnimationBaseObject::ClearTransitions](../Topic/CAnimationBaseObject::ClearTransitions.md)|関連するすべての遷移を削除します。|  
|[CAnimationBaseObject::ContainsVariable](../Topic/CAnimationBaseObject::ContainsVariable.md)|アニメーション オブジェクトに特定のアニメーション変数が格納されているかどうかを調べます。|  
|[CAnimationBaseObject::CreateTransitions](../Topic/CAnimationBaseObject::CreateTransitions.md)|アニメーション オブジェクトに関連付けられた遷移を作成します。|  
|[CAnimationBaseObject::DetachFromController](../Topic/CAnimationBaseObject::DetachFromController.md)|親アニメーション コントローラーからアニメーション オブジェクトをデタッチします。|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](../Topic/CAnimationBaseObject::EnableIntegerValueChangedEvent.md)|Integer Value Changed イベント ハンドラーを設定します。|  
|[CAnimationBaseObject::EnableValueChangedEvent](../Topic/CAnimationBaseObject::EnableValueChangedEvent.md)|Value Changed イベント ハンドラーを設定します。|  
|[CAnimationBaseObject::GetAutodestroyTransitions](../Topic/CAnimationBaseObject::GetAutodestroyTransitions.md)|関連する遷移が自動的に破棄されるかどうかを示します。|  
|[CAnimationBaseObject::GetGroupID](../Topic/CAnimationBaseObject::GetGroupID.md)|現在のグループ ID を返します。|  
|[CAnimationBaseObject::GetObjectID](../Topic/CAnimationBaseObject::GetObjectID.md)|現在のオブジェクト ID を返します。|  
|[CAnimationBaseObject::GetUserData](../Topic/CAnimationBaseObject::GetUserData.md)|ユーザー定義データを返します。|  
|[CAnimationBaseObject::SetAutodestroyTransitions](../Topic/CAnimationBaseObject::SetAutodestroyTransitions.md)|遷移を自動的に破棄するように指示するフラグを設定します。|  
|[CAnimationBaseObject::SetID](../Topic/CAnimationBaseObject::SetID.md)|新しい ID を設定します。|  
|[CAnimationBaseObject::SetUserData](../Topic/CAnimationBaseObject::SetUserData.md)|ユーザー定義データを設定します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md)|格納されているアニメーション変数へのポインターを収集します。|  
|[CAnimationBaseObject::SetParentAnimationObjects](../Topic/CAnimationBaseObject::SetParentAnimationObjects.md)|アニメーション オブジェクトに格納されるアニメーション変数とそのコンテナーの関係を確立します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationBaseObject::m\_bAutodestroyTransitions](../Topic/CAnimationBaseObject::m_bAutodestroyTransitions.md)|関連する遷移を自動的に破棄するかどうかを示します。|  
|[CAnimationBaseObject::m\_dwUserData](../Topic/CAnimationBaseObject::m_dwUserData.md)|ユーザー定義データを格納します。|  
|[CAnimationBaseObject::m\_nGroupID](../Topic/CAnimationBaseObject::m_nGroupID.md)|アニメーション オブジェクトのグループ ID を指定します。|  
|[CAnimationBaseObject::m\_nObjectID](../Topic/CAnimationBaseObject::m_nObjectID.md)|アニメーション オブジェクトのオブジェクト ID を指定します。|  
|[CAnimationBaseObject::m\_pParentController](../Topic/CAnimationBaseObject::m_pParentController.md)|親アニメーション コントローラーへのポインター。|  
  
## 解説  
 このクラスは、すべてのアニメーション オブジェクトの基本メソッドを実装します。  アニメーション オブジェクトは、値、点、サイズ、四角形、または色をアプリケーションで表すことができます。カスタム エンティティを表すこともできます。  アニメーション オブジェクトはアニメーション グループに格納されます \(CAnimationGroup を参照してください\)。  各グループは個別にアニメーション化でき、ストーリーボードのように扱うことができます。  アニメーション オブジェクトは、その論理表現に応じて 1 つまたは複数のアニメーション変数をカプセル化します \(CAnimationVariable を参照してください\)。  たとえば、CAnimationRect には、四角形の辺ごとに 1 つずつ、4 つのアニメーション変数が格納されます。  各アニメーション オブジェクト クラスは、オーバーロードされた AddTransition メソッドを公開します。カプセル化されたアニメーション変数に遷移を適用するにはそのメソッドを使用する必要があります。  アニメーション オブジェクトは、オブジェクト ID \(オプション\) とグループ ID で識別できます。  アニメーション オブジェクトを正しいグループに配置するにはグループ ID が必要です。グループ ID が指定されていない場合は ID 0 の既定のグループに配置されます。  別の GroupID を使用して SetID を呼び出すと、アニメーション オブジェクトが別のグループに移動されます \(必要に応じて、新しいグループが作成されます\)。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)
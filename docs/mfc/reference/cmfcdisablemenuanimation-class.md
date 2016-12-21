---
title: "CMFCDisableMenuAnimation クラス | Microsoft Docs"
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
  - "CMFCDisableMenuAnimation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDisableMenuAnimation クラス"
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDisableMenuAnimation クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ポップアップ メニューのアニメーションを無効にします。  
  
## 構文  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|`CMFCDisableMenuAnimation` オブジェクトを構築します。|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|デストラクターです。|  
  
### パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCDisableMenuAnimation::Restore](../Topic/CMFCDisableMenuAnimation::Restore.md)|フレームワークがポップアップ メニューの表示に使用した前のアニメーションを復元します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDisableMenuAnimation::m_animType`|前のポップアップ メニューのアニメーションの種類を格納します。|  
  
### 解説  
 ポップアップ メニューのアニメーションを一時的に無効にする \(マウスまたはキーボードのコマンドを処理するなど\) 場合に、このヘルパー クラスを使用します。  
  
 `CMFCDisableMenuAnimation` オブジェクトは、その有効期間中にポップアップ メニューのアニメーションを無効にします。  コンストラクターは、現在のポップアップ メニューのアニメーションの種類を `m_animType` フィールドに格納し、現在のアニメーションの種類を `CMFCPopupMenu::NO_ANIMATION` に設定します。  デストラクターは、前のアニメーションの種類を復元します。  
  
 スタックに `CMFCDisableMenuAnimation` オブジェクトを作成して、1 つの関数の中でポップアップ メニューのアニメーションを無効にすることができます。  関数ごとにポップアップ メニューのアニメーションを無効にする場合は、ヒープに `CMFCDisableMenuAnimation` オブジェクトを作成します。ポップアップ メニューのアニメーションを復元する場合は、ヒープのオブジェクトを削除します。  
  
## 使用例  
 スタックを使用してメニューのアニメーションを一時的に無効にする方法を次の例に示します。  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/CPP/cmfcdisablemenuanimation-class_1.h)]  
  
## 継承階層  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## 必要条件  
 **ヘッダー :** afxpopupmenu.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCPopupMenu クラス](../Topic/CMFCPopupMenu%20Class.md)
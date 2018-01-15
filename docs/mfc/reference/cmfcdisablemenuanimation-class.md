---
title: "CMFCDisableMenuAnimation クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
dev_langs: C++
helpviewer_keywords: CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 458a35e708db41ee393da70aedd653aca44cf802
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFCDisableMenuAnimation クラス
ポップアップ メニューのアニメーションを無効にします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDisableMenuAnimation  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|`CMFCDisableMenuAnimation` オブジェクトを構築します。|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCDisableMenuAnimation::Restore](#restore)|ポップアップ メニューを表示するために、フレームワークが使用される前のアニメーションを復元します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|name|説明|  
|`CMFCDisableMenuAnimation::m_animType`|以前のポップアップ メニューのアニメーションの種類を格納します。|  
  
### <a name="remarks"></a>コメント  
 このヘルパー クラスを使用すると、(マウスやキーボードのコマンドを処理する場合など) 用のポップアップ メニューのアニメーションを一時的に無効にします。  
  
 A`CMFCDisableMenuAnimation`オブジェクトがその有効期間中に、ポップアップ メニューのアニメーションを無効にします。 コンス トラクターでは、現在のポップアップ メニューのアニメーション型を格納する、`m_animType`フィールドと現在のアニメーションの種類をセット`CMFCPopupMenu::NO_ANIMATION`です。 デストラクターは、前のアニメーションの種類を復元します。  
  
 作成することができます、`CMFCDisableMenuAnimation`を 1 つの関数全体でポップアップ メニューのアニメーションを無効にするスタック上のオブジェクト。 関数の間でポップアップ メニューのアニメーションを無効にする場合は、作成、`CMFCDisableMenuAnimation`ヒープ上のオブジェクトし、し、ポップアップ メニューのアニメーションを復元するときに削除します。  
  
## <a name="example"></a>例  
 次の例では、スタックを使用して、メニューのアニメーションを一時的に無効にする方法を示します。  
  
 [!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxpopupmenu.h  
  
##  <a name="restore"></a>CMFCDisableMenuAnimation::Restore  
 ポップアップ メニューを表示するために、フレームワークが使用される前のアニメーションを復元します。  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`CMFCDisableMenuAnimation`デストラクターが、framework ポップアップ メニューを表示するために使用する前のアニメーションを復元します。  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)

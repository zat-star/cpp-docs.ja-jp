---
title: "CMFCDisableMenuAnimation クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
dev_langs:
- C++
helpviewer_keywords:
- CMFCDisableMenuAnimation class
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ea0be944ca70d6f8317fd4bc60fdd50ecc714438
ms.lasthandoff: 02/24/2017

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
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|
          `CMFCDisableMenuAnimation` オブジェクトを構築します。|  
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCDisableMenuAnimation::Restore](#restore)|ポップアップ メニューを表示するフレームワークが使用される前のアニメーションを復元します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDisableMenuAnimation::m_animType`|前のポップアップ メニューのアニメーションの種類を格納します。|  
  
### <a name="remarks"></a>コメント  
 このヘルパー クラスを使用すると、(たとえば、マウスまたはキーボードのコマンドを処理するときに) ポップアップ メニューのアニメーションを一時的に無効にします。  
  
 A`CMFCDisableMenuAnimation`オブジェクトがその有効期間中に、ポップアップ メニューのアニメーションを無効にします。 コンス トラクターで現在のポップアップ メニュー アニメーションの種類を格納する、`m_animType`フィールドと現在のアニメーションの種類をセット`CMFCPopupMenu::NO_ANIMATION`します。 デストラクターは、前のアニメーションの種類を復元します。  
  
 作成することができます、`CMFCDisableMenuAnimation`を&1; つの関数全体でのポップアップ メニューのアニメーションを無効にするスタック上のオブジェクト。 関数の間でのポップアップ メニューのアニメーションを無効にする場合は、作成、`CMFCDisableMenuAnimation`ヒープ上のオブジェクトし、し、ポップアップ メニューのアニメーションを復元するときに削除します。  
  
## <a name="example"></a>例  
 次の例では、スタックを使用して、メニューのアニメーションを一時的に無効にする方法を示します。  
  
 [!code-cpp[NVC_MFC_Misc&#1;](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCDisableMenuAnimation](../../mfc/reference/cmfcdisablemenuanimation-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpopupmenu.h  
  
##  <a name="restore"></a>CMFCDisableMenuAnimation::Restore  
 ポップアップ メニューを表示するフレームワークが使用される前のアニメーションを復元します。  
  
```  
void Restore ();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`CMFCDisableMenuAnimation`デストラクターが、framework ポップアップ メニューを表示するために使用する前のアニメーションを復元します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)


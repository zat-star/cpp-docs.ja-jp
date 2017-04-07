---
title: "CMFCDesktopAlertWndButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndButton class
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 52294143c6caf5a8e0458c152540c41f7df78c57
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton クラス
デスクトップ通知ダイアログ ボックスに追加するボタンを使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|既定のコンストラクター|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|キャプション領域のアラート ダイアログ ボックスで、ボタンを表示するかどうかを決定します。|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|ボタンが、[アラート] ダイアログ ボックスを閉じるかどうかを決定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|キャプション領域のアラート ダイアログ ボックスで、ボタンを表示するかどうかを指定するブール値。|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|ボタンが、[アラート] ダイアログ ボックスを閉じるかどうかを指定するブール値。|  
  
### <a name="remarks"></a>コメント  
 コンス トラクターは既定では、設定、`m_bIsCaptionButton`と`m_bIsCloseButton`データ メンバーに`FALSE`します。 親`CMFCDesktopAlertDialog`のオブジェクト セット`m_bIsCaptionButton`に`TRUE`アラート ダイアログ ボックスのキャプション領域で、ボタンが配置されている場合。 `CMFCDesktopAlertDialog`クラスを作成、`CMFCDesktopAlertWndButton`ボックス警告のダイアログを閉じるボタンとして機能し、設定をオブジェクト`m_bIsCloseButton`に`TRUE`します。  
  
 追加`CMFCDesktopAlertWndButton`オブジェクトを`CMFCDesktopAlertDialog`オブジェクトのいずれかのボタンを追加する場合とします。 詳細については`CMFCDesktopAlertDialog`を参照してください[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、使用して、`SetImage`メソッドで、`CMFCDesktopAlertWndButton`クラスです。 このコード スニペットの一部である、[デスクトップ アラート デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&4;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo&#5;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdesktopalertwnd.h  
  
##  <a name="iscaptionbutton"></a>CMFCDesktopAlertWndButton::IsCaptionButton  
 キャプション領域のアラート ダイアログ ボックスで、ボタンを表示するかどうかを決定します。  
  
```  
BOOL IsCaptionButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 警告ダイアログ ボックスのキャプション領域で、ボタンが表示されている場合は 0 以外。それ以外の場合、0 を返します。  
  
##  <a name="isclosebutton"></a>CMFCDesktopAlertWndButton::IsCloseButton  
 ボタンが、[アラート] ダイアログ ボックスを閉じるかどうかを決定します。  
  
```  
BOOL IsCloseButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンは、通知ダイアログ ボックスを閉じる場合は 0 以外それ以外の場合、0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)


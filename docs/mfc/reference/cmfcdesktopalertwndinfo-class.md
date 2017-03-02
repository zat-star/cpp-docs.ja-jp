---
title: "CMFCDesktopAlertWndInfo クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo class
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 26
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
ms.openlocfilehash: 7013a7c9b29c6dc9e6324ca0490a667ed79c88f7
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo クラス
`CMFCDesktopAlertWndInfo`クラスが使用されて、 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)します。 デスクトップ通知ウィンドウがポップアップする場合に表示されるコントロールを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[アイコン](#m_hicon)|表示されるアイコンのハンドル。|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|デスクトップ通知ウィンドウのリンクに関連付けられたコマンド ID。|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|デスクトップ通知ウィンドウに表示されるテキストです。|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|デスクトップ通知ウィンドウに表示されるリンクです。|  
  
## <a name="remarks"></a>コメント  
 `CMFCDesktopAlertWndInfo`クラスは、 [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)デスクトップ通知ウィンドウの [既定] ダイアログ ボックスに表示される要素を指定します。 既定のダイアログ ボックスでは、3 つの項目を含めることができます。  
  
-   アイコンは、呼び出すことによって設定[アイコン](#m_hicon)します。  
  
-   ラベル、またはテキスト メッセージは、呼び出すことによって設定[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)します。  
  
-   呼び出すことによって設定されたリンク[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)します。 タスクを設定するには、リンクがクリックされたときに実行されるコマンドを呼び出す[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)します。  
  
 既定のダイアログ ボックスが十分でない場合は、カスタム ダイアログを作成およびに渡す、 [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)メソッドの代わりに、このクラスを使用します。 詳細については、次を参照してください。 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)します。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメンバーを使用して、`CMFCDesktopAlertWndInfo`クラスです。 この例では、ハンドルをデスクトップ通知ウィンドウ、デスクトップ通知ウィンドウに表示されているリンクおよびデスクトップ通知ウィンドウ上のリンクに関連付けられているコマンド ID に表示されるテキスト、アイコンが表示されたらに設定する方法を示します。 この例は、[デスクトップ アラート デモのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo&#3;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDesktopAlertDialog.h  
  
##  <a name="a-nameoperatoreqa--cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a>CMFCDesktopAlertWndInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemhicona--cmfcdesktopalertwndinfomhicon"></a><a name="m_hicon"></a>アイコン  
 表示されるアイコンのハンドル。  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemnurlcmdida--cmfcdesktopalertwndinfomnurlcmdid"></a><a name="m_nurlcmdid"></a>CMFCDesktopAlertWndInfo::m_nURLCmdID  
 デスクトップ通知ウィンドウのリンクに関連付けられたコマンド ID。  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>コメント  
 ユーザーによって指定されたリンクをクリックするとコマンド ID がポップアップ ウィンドウの所有者に送信される[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)します。  
  
##  <a name="a-namemstrtexta--cmfcdesktopalertwndinfomstrtext"></a><a name="m_strtext"></a>CMFCDesktopAlertWndInfo::m_strText  
 デスクトップ通知ウィンドウに表示されるテキストです。  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namemstrurla--cmfcdesktopalertwndinfomstrurl"></a><a name="m_strurl"></a>CMFCDesktopAlertWndInfo::m_strURL  
 デスクトップ通知ウィンドウに表示されるリンクです。  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>コメント  
 ユーザーは、リンクをクリックすると、コマンドを含む、 [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)コマンド ID は、ポップアップ ウィンドウの所有者に送信されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd クラス](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)


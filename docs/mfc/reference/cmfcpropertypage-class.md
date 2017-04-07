---
title: "CMFCPropertyPage クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyPage::PreTranslateMessage method
- CMFCPropertyPage::CreateObject method
- CMFCPropertyPage class
- CMFCPropertyPage::OnSetActive method
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
caps.latest.revision: 30
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
ms.openlocfilehash: 0e9cdfa8a98c034839fac119c828cf1b92a1867a
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertypage-class"></a>CMFCPropertyPage クラス
`CMFCPropertyPage`クラスは、[プロパティ] ページのポップアップ メニューの表示をサポートしています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|`CMFCPropertyPage` オブジェクトを構築します。|  
|`CMFCPropertyPage::~CMFCPropertyPage`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCPropertyPage::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCPropertyPage::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|`CMFCPropertyPage::OnSetActive`|このメンバー関数は、ページは、ユーザーが選択され、アクティブになったときに、framework によって呼び出されます。 (上書き[CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive))。|  
|`CMFCPropertyPage::PreTranslateMessage`|ウィンドウのメッセージの変換にディスパッチされる前に、 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955)と[DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 関数です。 詳細およびメソッドの構文は、「 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)します。 (`CPropertyPage::PreTranslateMessage` をオーバーライドします)。|  
  
## <a name="remarks"></a>コメント  
 `CMFCPropertyPage`クラスはタブ ダイアログ ボックスとして知られている、プロパティ シートの各ページを表します。  
  
 使用して、`CMFCPropertyPage`と共に、 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)クラスです。 [プロパティ] ページのメニューを使用する箇所をすべて、`CPropertyPage`クラス、`CMFCPropertyPage`クラスです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpropertypage.h  
  
##  <a name="cmfcpropertypage"></a>CMFCPropertyPage::CMFCPropertyPage  
 `CMFCPropertyPage` オブジェクトを構築します。  
  
```  
CMFCPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption=0);

 
CMFCPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption=0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDTemplate`  
 このページのテンプレートのリソース ID です。  
  
 `nIDCaption`  
 このページのタブにラベルのリソース ID です。 0 の場合、このページのダイアログ ボックスのテンプレートから、名前を取得します。 既定値は 0 です。  
  
 `lpszTemplateName`  
 このページのテンプレートの名前を指します。 ことはできません`NULL`します。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 コンス トラクターのパラメーターの詳細については、次を参照してください。 [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)


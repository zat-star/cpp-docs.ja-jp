---
title: "CMFCRibbonCustomizeDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetThisClass
- CMFCRibbonCustomizeDialog
- ~CMFCRibbonCustomizeDialog
- CMFCRibbonCustomizeDialog::GetThisClass
- CMFCRibbonCustomizeDialog.~CMFCRibbonCustomizeDialog
- CMFCRibbonCustomizeDialog.GetThisClass
- CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonCustomizeDialog class
- CMFCRibbonCustomizeDialog class, destructor
- ~CMFCRibbonCustomizeDialog destructor
- GetThisClass method
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
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
ms.openlocfilehash: d27247f89901adad1778313cdde6fe206a569f0d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog クラス
リボンが表示されます**カスタマイズ**ページです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|`CMFCRibbonCustomizeDialog` オブジェクトを構築します。|  
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonCustomizeDialog::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 AFX_WM_ON_RIBBON_CUSTOMIZE メッセージを処理しない場合、またはメッセージ ハンドラーから 0 を返す場合は、MFC を自動的にこのクラスをインスタンス化します。  
  
 アプリケーションにこのクラスを使用して、リボンを表示する**カスタマイズ** ダイアログ ボックスでのみインスタンス化しを呼び出す、`DoModal`メソッドです。  
  
 このクラスがから派生しているため[CMFCPropertySheet クラス](../../mfc/reference/cmfcpropertysheet-class.md)を使用してカスタム ページを追加することができます、 `CMFCPropertySheet` API です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)  
  
 [CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribboncustomizedialog.h  
  
##  <a name="a-namecmfcribboncustomizedialoga--cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a>CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog  
 `CMFCRibbonCustomizeDialog` オブジェクトを構築します。  
  
```  
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,  
    CMFCRibbonBar* pRibbon);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParent`  
 親ウィンドウ (通常はメイン フレーム) へのポインター。  
  
 [入力] `pRibbon`  
 ポインター、`CMFCRibbonBar`カスタマイズ可能です。  
  
### <a name="example"></a>例  
 次の例では、構築、`CMFCRibbonCustomizeDialog`オブジェクトです。  
  
 [!code-cpp[NVC_MFC_RibbonApp&#18;](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]  
  
### <a name="remarks"></a>コメント  
 コンス トラクターのインスタンスを作成、 [CMFCRibbonCustomizePropertyPage クラス](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)オブジェクトし、プロパティ シートのページのコレクションに追加します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)


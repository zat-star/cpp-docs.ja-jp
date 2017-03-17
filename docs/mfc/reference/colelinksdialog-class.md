---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinksDialog
- AFXODLGS/COleLinksDialog
- AFXODLGS/COleLinksDialog::COleLinksDialog
- AFXODLGS/COleLinksDialog::DoModal
- AFXODLGS/COleLinksDialog::m_el
dev_langs:
- C++
helpviewer_keywords:
- Edit Links dialog box
- COleLinksDialog class
- dialog boxes, OLE
- OLE Edit Links dialog box
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
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
ms.openlocfilehash: ed256b3a4d3236863e3dcccb7614949f650f058b
ms.lasthandoff: 02/24/2017

---
# <a name="colelinksdialog-class"></a>関数のクラス
OLE の [リンクの編集] ダイアログ ボックスに使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|`COleLinksDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|OLE の [リンクの編集] ダイアログ ボックスが表示されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|型の構造体**される** ダイアログ ボックスの動作を制御します。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COleLinksDialog`このダイアログ ボックスを呼び出そうとするとします。 後に、`COleLinksDialog`使用すると、オブジェクトが構築された、[各](#m_el)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_el`型の構造は、**される**します。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
> [!NOTE]
>  アプリケーション ウィザードで生成されたコンテナーのコードでは、このクラスを使用します。  
  
 詳細については、次を参照してください。、[される](http://msdn.microsoft.com/library/windows/desktop/ms678492)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 OLE 固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [関数](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="domodal"></a>COleLinksDialog::DoModal  
 OLE の [リンクの編集] ダイアログ ボックスが表示されます。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出しが返される、`COleDialog::GetLastError`の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、[される](http://msdn.microsoft.com/library/windows/desktop/ms679703)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、[各](#m_el)構造体、行う必要があります、呼び出す前に`DoModal`はダイアログ オブジェクトを構築します。  
  
##  <a name="colelinksdialog"></a>COleLinksDialog::COleLinksDialog  
 `COleLinksDialog` オブジェクトを構築します。  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 編集しようとするリンクを含む OLE ドキュメントへのポインター。  
  
 `pView`  
 上の現在のビューを指す`pDoc`します。  
  
 `dwFlags`  
 0 を含む作成フラグまたは**ELF_SHOWHELP**  ダイアログ ボックスが表示されたときに ヘルプ ボタンを表示するかどうかを指定します。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の`CWnd`) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ ボックスの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>コメント  
 この関数はのみ、`COleLinksDialog`オブジェクトです。 ダイアログ ボックスを表示するには[DoModal](#domodal)関数です。  
  
##  <a name="m_el"></a>COleLinksDialog::m_el  
 型の構造体**される**リンクの編集 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。  
  
 詳細については、次を参照してください。、[される](http://msdn.microsoft.com/library/windows/desktop/ms678492)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)


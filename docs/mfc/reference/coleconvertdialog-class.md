---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
dev_langs:
- C++
helpviewer_keywords:
- COleConvertDialog class
- OLE Convert dialog box
- dialog boxes, OLE
- OLE dialog boxes, Convert
- Convert dialog box
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6db5caf443e7f71c58e2c65b46794c2c9d246d38
ms.lasthandoff: 02/24/2017

---
# <a name="coleconvertdialog-class"></a>メンバー クラス
詳細については、次を参照してください。、[使わ](http://msdn.microsoft.com/library/windows/desktop/ms686657)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="syntax"></a>構文  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|`COleConvertDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|ダイアログ ボックスで指定した変換を行います。|  
|[COleConvertDialog::DoModal](#domodal)|OLE の [項目の変更] ダイアログ ボックスが表示されます。|  
|[COleConvertDialog::GetClassID](#getclassid)|取得、 **CLSID**選択したアイテムに関連付けられています。|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|アイテムをアイコンとして描画するかどうかを指定します。|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|この項目のアイコン形式に関連付けられているメタファイルを識別するハンドルを取得します。|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|選択の種類を取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|ダイアログ ボックスの動作を制御する構造体。|  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  アプリケーション ウィザードで生成されたコンテナーのコードでは、このクラスを使用します。  
  
 OLE 固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [関数](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>COleConvertDialog::COleConvertDialog  
 のみを構築、`COleConvertDialog`オブジェクトです。  
  
```  
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 アクティブ化または変換する項目へのポインター。  
  
 `dwFlags`  
 作成フラグは、次の値の任意の数が含まれていますが、ビットごとの使用を組み合わせるの or 演算子。  
  
- **CF_SELECTCONVERTTO**  ダイアログ ボックスが呼び出されたときに、変換 ラジオ ボタンをクリックした状態を指定します。 既定値です。  
  
- **CF_SELECTACTIVATEAS** ] ダイアログ ボックスが呼び出されたときに、[オプション ボタンをクリックした状態を指定します。  
  
- **CF_SETCONVERTDEFAULT**を指定するクラスが**CLSID**で指定された、 **clsidConvertDefault**のメンバー、`m_cv`構造体の変換 ラジオ ボタンを選択すると、クラスのリスト ボックスで、既定の選択として使用されます。  
  
- **CF_SETACTIVATEDEFAULT**を指定するクラスが**CLSID**で指定された、 **clsidActivateDefault**のメンバー、`m_cv`構造体は、オプション ボタンを選択すると、クラスのリスト ボックスに既定の選択として使用されます。  
  
- **CF_SHOWHELPBUTTON**  ダイアログ ボックスが呼び出されたときに、ヘルプ ボタンを表示するように指定します。  
  
 `pClassID`  
 アクティブ化または変換する項目の CLSID へのポインター。 場合**NULL**、 **CLSID**に関連付けられている`pItem`が適用されます。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の`CWnd`) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ ボックスの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスを表示するには[DoModal](#domodal)関数です。  
  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424)と[使わ](http://msdn.microsoft.com/library/windows/desktop/ms686657)構造体。  
  
##  <a name="doconvert"></a>COleConvertDialog::DoConvert  
 この関数の呼び出しから正常に戻った後[DoModal](#domodal)変換するか、型のオブジェクトをアクティブにするか、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)します。  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 アクティブ化または変換する項目へのポインター。 ことはできません**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 項目を変換または変換 ダイアログ ボックスでユーザーが選択されている情報に従って有効にします。  
  
##  <a name="domodal"></a>COleConvertDialog::DoModal  
 OLE の [変換] ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出しが返される、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、[使わ](http://msdn.microsoft.com/library/windows/desktop/ms680694)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、 [m_cv](#m_cv)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**、他のメンバーの設定やユーザー ダイアログ ボックスに入力した情報を取得する関数を呼び出すことができます。  
  
##  <a name="getclassid"></a>COleConvertDialog::GetClassID  
 取得するには、この関数を呼び出す、 **CLSID**変換 ダイアログ ボックスで選択された項目に関連付けられています。  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 **CLSID**変換 ダイアログ ボックスで選択した項目に関連付けられています。  
  
### <a name="remarks"></a>コメント  
 後でのみこの関数の呼び出し[DoModal](#domodal)返します**IDOK**します。  
  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getdrawaspect"></a>COleConvertDialog::GetDrawAspect  
 ユーザーがアイコンとして選択した項目を表示する選択したかどうかを判断するには、この関数を呼び出します。  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メソッドは、オブジェクトのレンダリングに必要です。  
  
- `DVASPECT_CONTENT`アイコンで表示 チェック ボックスがオフかどうかに返されます。  
  
- `DVASPECT_ICON`アイコンで表示 チェック ボックスがオンになっているかどうかに返されます。  
  
### <a name="remarks"></a>コメント  
 後でのみこの関数の呼び出し[DoModal](#domodal)返します**IDOK**します。  
  
 縦横の描画の詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で構造化データ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="geticonicmetafile"></a>COleConvertDialog::GetIconicMetafile  
 選択した項目のアイコンの外観を持つメタファイルを識別するハンドルを取得するには、この関数を呼び出します。  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択して、ダイアログが終了したときにオンの場合はアイコンで表示 チェック ボックスが選択した項目のアイコンの外観を持つメタファイル ハンドル**OK**。 そうしないと**NULL**します。  
  
##  <a name="getselectiontype"></a>COleConvertDialog::GetSelectionType  
 この関数では、[変換] ダイアログ ボックスで選択された変換の種類を判断します。  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択内容の種類です。  
  
### <a name="remarks"></a>コメント  
 戻り値の型の値がで指定された、**選択**で宣言された列挙型、`COleConvertDialog`クラスです。  
  
```  
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };  
```  
  
 これらの値の簡単な説明に従ってください。  
  
- **COleConvertDialog::noConversion**  ダイアログ ボックスがキャンセルされたか、ユーザーが選択されていない変換が返されます。 場合`COleConvertDialog::DoModal`返される**IDOK**ユーザーが選択されていたものとは異なるアイコンを選択することができます。  
  
- **COleConvertDialog::convertItem** 、ユーザーに変換するさまざまな項目を選択して変換 ラジオ ボタンが選択した場合、返されると`DoModal`返される**IDOK**します。  
  
- **COleConvertDialog::activateAs**をアクティブ化すると、別の項目をユーザーが選択したオプション ボタンが選択した場合、返されると`DoModal`返される**IDOK**します。  
  
##  <a name="m_cv"></a>COleConvertDialog::m_cv  
 型の構造体**使わ**変換 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。  
  
 詳細については、次を参照してください。、[使わ](http://msdn.microsoft.com/library/windows/desktop/ms686657)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)


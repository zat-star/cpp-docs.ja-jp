---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
dev_langs:
- C++
helpviewer_keywords:
- OLE dialog boxes, Change Icon
- OLE Change Icon dialog box
- dialog boxes, OLE
- COleChangeIconDialog class
- Change Icon dialog box
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 07dfd7995bbbdb0f52f55dceedc318d8d702111b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="colechangeicondialog-class"></a>メンバー クラス
OLE の [アイコンの変更] ダイアログ ボックスに使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|`COleChangeIconDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|ダイアログ ボックスで指定した変更を実行します。|  
|[COleChangeIconDialog::DoModal](#domodal)|OLE 2 変更 ダイアログ ボックスが表示されます。|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|この項目のアイコン形式に関連付けられているメタファイルを識別するハンドルを取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|ダイアログ ボックスの動作を制御する構造体。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COleChangeIconDialog`このダイアログ ボックスを呼び出そうとするとします。 後に、`COleChangeIconDialog`使用すると、オブジェクトが構築された、[各](#m_ci)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_ci`型の構造は、 **OLEUICHANGEICON**します。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
 詳細については、次を参照してください。、 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 OLE 固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [関数](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="colechangeicondialog"></a>COleChangeIconDialog::COleChangeIconDialog  
 この関数はのみ、`COleChangeIconDialog`オブジェクトです。  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 変換する項目へのポインター。  
  
 `dwFlags`  
 作成フラグは、次の値の任意の数が含まれていますが、ビットごとの使用を組み合わせるの or 演算子。  
  
- **CIF_SELECTCURRENT** ] ダイアログ ボックスが呼び出されたときに、[現在のラジオ ボタンをクリックした状態を指定します。 既定値です。  
  
- **CIF_SELECTDEFAULT** ] ダイアログ ボックスが呼び出されたときに、[既定のオプション ボタンをクリックした状態を指定します。  
  
- **CIF_SELECTFROMFILE**  ダイアログ ボックスが呼び出されたときに、ファイルから ラジオ ボタンをクリックした状態を指定します。  
  
- **CIF_SHOWHELP**  ダイアログ ボックスが呼び出されたときに、ヘルプ ボタンを表示するように指定します。  
  
- **CIF_USEICONEXE**で指定された実行可能ファイルからアイコンを抽出することを指定、 **szIconExe**フィールド[各](#m_ci)の代わりに、型から取得します。 これは、埋め込みまたは非 OLE ファイルにリンクするのに便利です。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の`CWnd`) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ ボックスの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスを表示するには[DoModal](#domodal)関数です。  
  
 詳細については、次を参照してください。、 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="dochangeicon"></a>COleChangeIconDialog::DoChangeIcon  
 後のダイアログ ボックスで選択した項目を表すアイコンを変更するには、この関数を呼び出す[DoModal](#domodal)返します**IDOK**します。  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 そのアイコンを変更する項目へのポインター。  
  
### <a name="return-value"></a>戻り値  
 変更が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="domodal"></a>COleChangeIconDialog::DoModal  
 OLE の [アイコンの変更] ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出しが返される、`COleDialog::GetLastError`の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、[各](#m_ci)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**、他のメンバーの設定やユーザー ダイアログ ボックスに入力した情報を取得する関数を呼び出すことができます。  
  
##  <a name="geticonicmetafile"></a>COleChangeIconDialog::GetIconicMetafile  
 選択した項目のアイコンの外観を持つメタファイルを識別するハンドルを取得するには、この関数を呼び出します。  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択してダイアログ ボックスを閉じた場合は、新しいアイコンのアイコンの外観を持つメタファイルを識別するハンドル**OK**、それ以外とアイコンが、ダイアログ ボックスが表示される前にします。  
  
##  <a name="m_ci"></a>COleChangeIconDialog::m_ci  
 型の構造体**OLEUICHANGEICON**アイコンの変更 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。  
  
 詳細については、次を参照してください。、 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)


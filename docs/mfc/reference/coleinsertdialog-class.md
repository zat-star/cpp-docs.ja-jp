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
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
dev_langs:
- C++
helpviewer_keywords:
- OLE Insert Object dialog box
- dialog boxes, OLE
- COleInsertDialog class
- Insert Object dialog box
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
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
ms.openlocfilehash: 078f421dacc79ff929249cd35c520b0c4d4a222e
ms.lasthandoff: 02/24/2017

---
# <a name="coleinsertdialog-class"></a>メンバー クラス
OLE の [オブジェクトの挿入] ダイアログ ボックスで使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|`COleInsertDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[クリック](#createitem)|ダイアログ ボックスで選択した項目を作成します。|  
|[COleInsertDialog::DoModal](#domodal)|OLE の [オブジェクトの挿入] ダイアログ ボックスが表示されます。|  
|[COleInsertDialog::GetClassID](#getclassid)|取得、 **CLSID**選択したアイテムに関連付けられています。|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|アイコンとして項目を描画するかどうかを指示します。|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|この項目のアイコン形式に関連付けられているメタファイルを識別するハンドルを取得します。|  
|[COleInsertDialog::GetPathName](#getpathname)|ダイアログ ボックスで選択したファイルへの完全パスを取得します。|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|選択したオブジェクトの種類を取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|型の構造体**使う** ダイアログ ボックスの動作を制御します。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COleInsertDialog`このダイアログ ボックスを呼び出そうとするとします。 後に、`COleInsertDialog`使用すると、オブジェクトが構築された、 [m_io](#m_io)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_io`型の構造は、**使う**します。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
> [!NOTE]
>  アプリケーション ウィザードで生成されたコンテナーのコードでは、このクラスを使用します。  
  
 詳細については、次を参照してください。、[使う](http://msdn.microsoft.com/library/windows/desktop/ms691316)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 OLE 固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [関数](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="coleinsertdialog"></a>COleInsertDialog::COleInsertDialog  
 この関数はのみ、`COleInsertDialog`オブジェクトです。  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 任意の数のビットごとの OR 演算子を使用して結合するのには、次の値を含む作成フラグ:  
  
- **IOF_SHOWHELP**  ダイアログ ボックスが呼び出されたときに、ヘルプ ボタンを表示するように指定します。  
  
- **IOF_SELECTCREATENEW**  ダイアログ ボックスが呼び出されたときに、新規作成 をクリックした状態を指定します。 既定値は、これとは併用できません**IOF_SELECTCREATEFROMFILE**します。  
  
- **IOF_SELECTCREATEFROMFILE** ] ダイアログ ボックスが呼び出されたときに、[ファイルから作成するラジオ ボタンをクリックした状態を指定します。 は使用できません**IOF_SELECTCREATENEW**します。  
  
- **IOF_CHECKLINK**  ダイアログ ボックスが呼び出されたときに、リンク チェック ボックスを最初に確認することを指定します。  
  
- **IOF_DISABLELINK**リンク チェック ボックスは無効にする ダイアログ ボックスが呼び出されたときを指定します。  
  
- **IOF_CHECKDISPLAYASICON**アイコンで表示 チェック ボックスを最初にチェックを現在のアイコンが表示されます ダイアログ ボックスが呼び出されたときに、アイコンの変更 ボタンが有効にすることを指定します。  
  
- **IOF_VERIFYSERVERSEXIST**指定 ダイアログ ボックスが、ダイアログ ボックスが表示される前に、registration データベースに指定されたサーバーが存在するようにすることで、リスト ボックスに追加のクラスを検証する必要があります。 このフラグを設定すると、パフォーマンスが低下することができますが大幅にします。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の`CWnd`) ダイアログ オブジェクトが属しています。 ある場合**NULL**アプリケーションのメイン ウィンドウに、ダイアログ オブジェクトの親ウィンドウが設定されています。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスを表示するには[DoModal](#domodal)関数です。  
  
##  <a name="createitem"></a>クリック  
 型のオブジェクトを作成するには、この関数を呼び出す[COleClientItem](../../mfc/reference/coleclientitem-class.md)場合にのみ、 [DoModal](#domodal)返します**IDOK**します。  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 作成される項目へのポインター。  
  
### <a name="return-value"></a>戻り値  
 アイテムが作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 割り当てる必要があります、`COleClientItem`オブジェクトの前に、この関数を呼び出すことができます。  
  
##  <a name="domodal"></a>COleInsertDialog::DoModal  
 OLE の [オブジェクトの挿入] ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 次のいずれかの値です。  
  
 `COleInsertDialog::DocObjectsOnly`DocObjects のみを挿入します。  
  
 `COleInsertDialog::ControlsOnly`ActiveX コントロールのみを挿入します。  
  
 0 は、DocObject も ActiveX コントロールを挿入します。 この値は結果の最初のプロトタイプとして同じ実装では、上に示したします。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
-   IDOK ダイアログ ボックスが正常に表示された場合。  
  
-   IDCANCEL 場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
-   IDABORT 場合はエラーが発生しました。 IDABORT が返される場合、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、[使う](http://msdn.microsoft.com/library/windows/desktop/ms694325)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、 [m_io](#m_io)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`IDOK を返す他のメンバーは、ユーザーがダイアログ ボックスに情報の入力や設定を取得する関数で呼び出すことができます。  
  
##  <a name="getclassid"></a>COleInsertDialog::GetClassID  
 取得するには、この関数を呼び出す、 **CLSID**場合にのみ、選択した項目に関連付けられている[DoModal](#domodal)返します**IDOK**選択の種類は**フルパス名**します。  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します。、 **CLSID**選択した項目に関連付けられています。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CLSID キー](http://msdn.microsoft.com/library/windows/desktop/ms691424)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getdrawaspect"></a>COleInsertDialog::GetDrawAspect  
 選択項目のアイコンとして表示する、ユーザーが選択したかどうかを判断するには、この関数を呼び出します。  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メソッドは、オブジェクトのレンダリングに必要です。  
  
- `DVASPECT_CONTENT`アイコンで表示 チェック ボックスがオフかどうかに返されます。  
  
- `DVASPECT_ICON`アイコンで表示 チェック ボックスがオンになっているかどうかに返されます。  
  
### <a name="remarks"></a>コメント  
 場合にのみ、この関数を呼び出す[DoModal](#domodal)返します**IDOK**します。  
  
 縦横の描画の詳細については、次を参照してください。 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)で構造化データ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="geticonicmetafile"></a>COleInsertDialog::GetIconicMetafile  
 選択した項目のアイコンの外観を持つメタファイルを識別するハンドルを取得するには、この関数を呼び出します。  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択して、ダイアログが終了したときにオンの場合はアイコンで表示 チェック ボックスが選択した項目のアイコンの外観を持つメタファイル ハンドル**OK**。 そうしないと**NULL**します。  
  
##  <a name="getpathname"></a>COleInsertDialog::GetPathName  
 場合にのみ、選択したファイルの完全なパスを取得するには、この関数を呼び出す[DoModal](#domodal)返します**IDOK**選択範囲の種類と**フルパス名**します。  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスで選択されたファイルの完全パス。 場合は、選択の種類は`createNewItem`、この関数は、意味のない返します`CString`リリース モードでまたはデバッグ モードでのアサーションを発生させます。  
  
##  <a name="getselectiontype"></a>COleInsertDialog::GetSelectionType  
 選択してオブジェクトの挿入 ダイアログ ボックスが終了したときに選択した型を取得するには、この関数を呼び出す**OK**します。  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択内容の種類です。  
  
### <a name="remarks"></a>コメント  
 戻り値の型の値がで指定された、**選択**で宣言された列挙型、`COleInsertDialog`クラスです。  
  
 `enum Selection`  
  
 `{`  
  
 `createNewItem,`  
  
 `insertFromFile,`  
  
 `linkToFile`  
  
 `};`  
  
 これらの値の簡単な説明に従ってください。  
  
- **フルパス名**[新規作成] を選択します。  
  
- **COleInsertDialog::insertFromFile**ファイルからの作成 を選択し、リンク チェック ボックスが確認されていませんでした。  
  
- **COleInsertDialog::linkToFile**ファイルからの作成 を選択し、リンク チェック ボックスがオンにします。  
  
##  <a name="m_io"></a>COleInsertDialog::m_io  
 型の構造体**使う**オブジェクトの挿入 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数のいずれかに変更できます。  
  
 詳細については、次を参照してください。、[使う](http://msdn.microsoft.com/library/windows/desktop/ms691316)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)


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
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
dev_langs:
- C++
helpviewer_keywords:
- Paste Special dialog box
- dialog boxes, Paste Special
- OLE Paste Special dialog box
- COlePasteSpecialDialog class
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
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
ms.openlocfilehash: 6984d714248815b062c564c7eed5c315990855af
ms.lasthandoff: 02/24/2017

---
# <a name="colepastespecialdialog-class"></a>関数のクラス
OLE の [形式を選択して貼り付け] ダイアログ ボックス用に使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|`COlePasteSpecialDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|ユーザー定義の形式をアプリケーションで貼り付けできる形式の一覧に追加します。|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|クリップボードのサポートされている形式の一覧に新しいエントリを追加します。|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|追加**CF_BITMAP**、 **CF_DIB**、 `CF_METAFILEPICT`、および必要に応じて`CF_LINKSOURCE`形式の一覧に、アプリケーションを貼り付けることができます。|  
|[静的オブジェクト](#createitem)|指定された形式を使用して、コンテナー ドキュメント内の項目を作成します。|  
|[COlePasteSpecialDialog::DoModal](#domodal)|OLE の [形式を選択して貼り付け] ダイアログ ボックスが表示されます。|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|かアイテムをアイコンとして描画するかどうかを指示します。|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|この項目のアイコン形式に関連付けられているメタファイルを識別するハンドルを取得します。|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|ユーザーが選択した利用可能な貼り付けのオプションのインデックスを取得します。|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|選択の種類を取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|型の構造体**選択して貼り付け** ダイアログ ボックスの機能を制御します。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COlePasteSpecialDialog`このダイアログ ボックスを呼び出そうとするとします。 後に、`COlePasteSpecialDialog`使用すると、オブジェクトが構築された、 [AddFormat](#addformat)と[AddStandardFormats](#addstandardformats)  ダイアログ ボックスにクリップボードの形式を追加するメンバー関数。 使用することも、[塗りつぶす対象となる](#m_ps)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_ps`型の構造は、**選択して貼り付け**します。  
  
 詳細については、次を参照してください。、[選択して貼り付け](http://msdn.microsoft.com/library/windows/desktop/ms692434)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 OLE 固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [関数](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="addformat"></a>COlePasteSpecialDialog::AddFormat  
 この関数では、新しい形式をアプリケーションが貼り付け操作でサポートできる形式の一覧に追加します。  
  
```  
void AddFormat(
    const FORMATETC& formatEtc,  
    LPTSTR lpszFormat,  
    LPTSTR lpszResult,  
    DWORD flags);

 
void AddFormat(
    UINT cf,  
    DWORD tymed,  
    UINT nFormatID,  
    BOOL bEnableIcon,  
    BOOL bLink);
```  
  
### <a name="parameters"></a>パラメーター  
 *fmt*  
 追加するデータ型への参照。  
  
 `lpszFormat`  
 ユーザーに形式を説明する文字列。  
  
 *lpszResult*  
 この形式は、ダイアログ ボックスで選択した場合の結果を表す文字列です。  
  
 `flags`  
 さまざまなリンクと埋め込みこの形式の使用可能なオプションです。 このフラグは、1 つまたは複数の異なる値のビットごとの組み合わせ、 **OLEUIPASTEFLAG**列挙型。  
  
 `cf`  
 クリップボードの形式を追加します。  
  
 *tymed*  
 この形式で利用可能なメディアの種類。 これは、1 つまたは複数の値のビットごとの組み合わせ、 **TYMED**列挙型。  
  
 `nFormatID`  
 この形式を識別する文字列の ID です。 この文字列の形式は、"\n"文字で区切られた&2; つの文字列です。 最初の文字列はで渡されるものと同じ、 *lpstrFormat*パラメーター、および&2; つ目と同じ、 *lpstrResult*パラメーター。  
  
 *bEnableIcon*  
 この形式は、リスト ボックスで選択されたときにアイコンで表示 チェック ボックスが有効にするかどうかを決定するフラグです。  
  
 *点滅*  
 この形式は、リスト ボックスで選択されたときに、リンクの貼り付けのオプション ボタンを有効かどうかを決定するフラグです。  
  
### <a name="remarks"></a>コメント  
 など、標準的な形式を追加するこの関数を呼び出すことができる**エディット**または**呼び出す**や、アプリケーションがシステムに登録されているカスタムの形式です。 詳細については、アプリケーションにデータ オブジェクトを貼り付け、記事を参照してください。[データ オブジェクトとデータ ソース: 操作](../../mfc/data-objects-and-data-sources-manipulation.md)します。  
  
 詳細については、次を参照してください。、 [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227)列挙型、および[FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 詳細については、次を参照してください。、 [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172)列挙型で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="addlinkentry"></a>COlePasteSpecialDialog::AddLinkEntry  
 クリップボードのサポートされている形式の一覧に新しいエントリを追加します。  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>パラメーター  
 `cf`  
 クリップボードの形式を追加します。  
  
### <a name="return-value"></a>戻り値  
 [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172)構造体の新しいリンク エントリの情報を格納します。  
  
##  <a name="addstandardformats"></a>COlePasteSpecialDialog::AddStandardFormats  
 次のクリップボード形式をアプリケーションが貼り付け操作でサポートできる形式の一覧に追加するには、この関数を呼び出します。  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEnableLink*  
 追加するかどうかを決定するフラグ`CF_LINKSOURCE`形式の一覧に、アプリケーションを貼り付けることができます。  
  
### <a name="remarks"></a>コメント  
  
- **CF_BITMAP**  
  
- **CF_DIB**  
  
- `CF_METAFILEPICT`  
  
- **「埋め込みオブジェクト」**  
  
-   (省略可能)**「リンク元」**  
  
 これらの形式は、埋め込みとリンクをサポートするために使用されます。  
  
##  <a name="colepastespecialdialog"></a>COlePasteSpecialDialog::COlePasteSpecialDialog  
 `COlePasteSpecialDialog` オブジェクトを構築します。  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwFlags`  
 作成フラグには、次のフラグのビットごとの OR 演算子を使用して結合の任意の数が含まれています。  
  
- `PSF_SELECTPASTE`ダイアログ ボックスが呼び出されたときに、[貼り付け] ラジオ ボタンをクリックした状態を指定します。 組み合わせて使用できない`PSF_SELECTPASTELINK`します。 既定値です。  
  
- `PSF_SELECTPASTELINK`ラジオ ボタンがあるリンクを貼り付けオンになっている最初にダイアログ ボックスが呼び出されるタイミングを指定します。 組み合わせて使用できない`PSF_SELECTPASTE`します。  
  
- `PSF_CHECKDISPLAYASICON`ダイアログ ボックスが呼び出されたときにアイコンで表示 チェック ボックスを最初に確認することを指定します。  
  
- `PSF_SHOWHELP`ダイアログ ボックスが呼び出されたときに、[ヘルプ] ボタンが表示されることを指定します。  
  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)貼り付けられるようにします。 この値は、する場合**NULL**、取得、`COleDataObject`クリップボードからです。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の`CWnd`) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ ボックスの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、`COlePasteSpecialDialog`オブジェクトです。 ダイアログ ボックスを表示するには[DoModal](#domodal)関数です。  
  
 詳細については、次を参照してください。、 [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172)列挙型で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="createitem"></a>静的オブジェクト  
 貼り付け ダイアログ ボックスで選択された新しい項目を作成します。  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *pNewItem*  
 指す、`COleClientItem`インスタンス。 ことはできません**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 項目が正常に作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、後にのみ呼び出す必要があります[DoModal](#domodal)返します**IDOK**します。  
  
##  <a name="domodal"></a>COlePasteSpecialDialog::DoModal  
 OLE の [形式を選択して貼り付け] ダイアログ ボックスが表示されます。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出しが返される、`COleDialog::GetLastError`の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、[選択して貼り付け](http://msdn.microsoft.com/library/windows/desktop/ms694512)で機能、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、[塗りつぶす対象となる](#m_ps)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**、他のメンバー ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数を呼び出すことができます。  
  
##  <a name="getdrawaspect"></a>COlePasteSpecialDialog::GetDrawAspect  
 ユーザーがアイコンとして選択した項目を表示する選択したかどうかを判断します。  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>戻り値  
 メソッドは、オブジェクトのレンダリングに必要です。  
  
- `DVASPECT_CONTENT`ダイアログ ボックスを閉じたときに、アイコンで表示 チェック ボックスがチェックされないかどうかに返されます。  
  
- `DVASPECT_ICON`かどうかは、アイコンで表示 チェック ボックスがオン ダイアログ ボックスを閉じたときに返されます。  
  
### <a name="remarks"></a>コメント  
 この関数の後にのみ呼び出す[DoModal](#domodal)返します**IDOK**します。  
  
 縦横の描画の詳細については、次を参照してください。、 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="geticonicmetafile"></a>COlePasteSpecialDialog::GetIconicMetafile  
 ユーザーが選択した項目に関連付けられているメタファイルを取得します。  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ハンドルを選択してダイアログ ボックスを閉じたときにアイコンで表示 チェック ボックスを選択した場合、選択した項目のアイコンの外観を持つメタファイル**OK**以外の場合**NULL**します。  
  
##  <a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex  
 取得、ユーザーが選択したエントリに関連付けられているインデックス値。  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>戻り値  
 配列のインデックス**OLEUIPASTEENTRY**ユーザーが選択された構造体。 貼り付け操作を実行するときに、選択されたインデックスに対応する形式を使用する必要があります。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。、 [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getselectiontype"></a>COlePasteSpecialDialog::GetSelectionType  
 ユーザーが選択したの種類を決定します。  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択された型を返す。  
  
### <a name="remarks"></a>コメント  
 戻り値の型の値がで指定された、**選択**で宣言された列挙型、`COlePasteSpecialDialog`クラスです。  
  
 `enum Selection`  
  
 `{`  
  
 `pasteLink,`  
  
 `pasteNormal,`  
  
 `pasteOther,`  
  
 `pasteStatic`  
  
 `};`  
  
 次のこれらの値の簡単に説明します。  
  
- **COlePasteSpecialDialog::pasteLink**リンクの貼り付け ラジオ ボタンがオンになって、選択した形式は、標準の OLE 形式です。  
  
- **COlePasteSpecialDialog::pasteNormal** [貼り付け] ラジオ ボタンが選択されましたが、選択した形式が標準の OLE 形式です。  
  
- **COlePasteSpecialDialog::pasteOther**選択した形式は、標準の OLE 形式ではありません。  
  
- **COlePasteSpecialDialog::pasteStatic**は選択した形式が、メタファイルです。  
  
##  <a name="m_ps"></a>COlePasteSpecialDialog::m_ps  
 型の構造体**選択して貼り付け**貼り付け ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数を使って変更できます。  
  
 詳細については、次を参照してください。、[選択して貼り付け](http://msdn.microsoft.com/library/windows/desktop/ms692434)構造体、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)


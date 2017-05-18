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
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
dev_langs:
- C++
helpviewer_keywords:
- OLE Change Source dialog box
- COleChangeSourceDialog class
- dialog boxes, OLE
- OLE dialog boxes, Change Source
- OleUIChangeSource structure
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4a1af032b9a10a0262f0267056b675eed7da509c
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="colechangesourcedialog-class"></a>メンバー クラス
OLE の [ソースの変更] ダイアログ ボックスに使用します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|`COleChangeSourceDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|OLE の [ソースの変更] ダイアログ ボックスが表示されます。|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|完全なソースの表示名を取得します。|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|ソース名からファイル名を取得します。|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|以前のソースのプレフィックスを取得します。|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|ソース名、項目の名前を取得します。|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|新しいソースのプレフィックスを取得します。|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|ソースが有効なかどうかを示します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|ダイアログ ボックスの動作を制御する構造体。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COleChangeSourceDialog`このダイアログ ボックスを呼び出そうとするとします。 後に、`COleChangeSourceDialog`使用すると、オブジェクトが構築された、 [m_cs](#m_cs)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_cs`型の構造は、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)します。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]します。  
  
 OLE 固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [関数](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>COleChangeSourceDialog::COleChangeSourceDialog  
 この関数は、作成、`COleChangeSourceDialog`オブジェクトです。  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pItem`  
 リンクへのポインター [COleClientItem](../../mfc/reference/coleclientitem-class.md)を更新するにはソース。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウのオブジェクトを指します (型の`CWnd`) ダイアログ オブジェクトが属しています。 ある場合**NULL**、ダイアログ ボックスの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスを表示するには[DoModal](#domodal)関数です。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造と[OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497)で[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]します。  
  
##  <a name="domodal"></a>COleChangeSourceDialog::DoModal  
 OLE の [ソースの変更] ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出しが返される、 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror)の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497)で[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]します。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定して、さまざまなダイアログ ボックス コントロールを初期化する場合、 [m_cs](#m_cs)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**、ダイアログ ボックスからユーザーが入力した設定や情報を取得する関数メンバーを呼び出すことができます。 一般的なクエリ関数の名前を次の一覧にします。  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>COleChangeSourceDialog::GetDisplayName  
 この関数では、リンクされているクライアント アイテムの完全な表示名を取得します。  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>戻り値  
 完全なソース表示名 (moniker)、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。  
  
##  <a name="getfilename"></a>COleChangeSourceDialog::GetFileName  
 ファイルのモニカーがリンクされているクライアント アイテムの表示名の部分を取得するには、この関数を呼び出します。  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>戻り値  
 ファイルのモニカーのソースの表示名の部分、 [COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。  
  
### <a name="remarks"></a>コメント  
 アイテム モニカーと共にファイル モニカーは、完全な表示名を示します。  
  
##  <a name="getfromprefix"></a>COleChangeSourceDialog::GetFromPrefix  
 この関数では、ソースの以前のプレフィックス文字列を取得します。  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>戻り値  
 ソースの以前のプレフィックス文字列。  
  
### <a name="remarks"></a>コメント  
 後でのみこの関数の呼び出し[DoModal](#domodal)返します**IDOK**します。  
  
 この値は直接、 **lpszFrom**のメンバー、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]します。  
  
##  <a name="getitemname"></a>COleChangeSourceDialog::GetItemName  
 リンクされているクライアント アイテムの表示名のアイテム モニカーの部分を取得するには、この関数を呼び出します。  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>戻り値  
 アイテム モニカーの部分のソースの表示名の[COleClientItem](../../mfc/reference/coleclientitem-class.md)コンス トラクターで指定します。  
  
### <a name="remarks"></a>コメント  
 アイテム モニカーと共にファイル モニカーは、完全な表示名を示します。  
  
##  <a name="gettoprefix"></a>COleChangeSourceDialog::GetToPrefix  
 この関数では、ソースの新しいプレフィックス文字列を取得します。  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>戻り値  
 ソースの新しいプレフィックス文字列。  
  
### <a name="remarks"></a>コメント  
 後でのみこの関数の呼び出し[DoModal](#domodal)返します**IDOK**します。  
  
 この値は直接、 **lpszTo**のメンバー、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]します。  
  
##  <a name="m_cs"></a>COleChangeSourceDialog::m_cs  
 このデータ メンバーは型の構造体[OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)します。  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>コメント  
 `OLEUICHANGESOURCE`OLE の [ソースの変更] ダイアログ ボックスの動作の制御に使用されます。 この構造体のメンバーを直接変更することができます。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]します。  
  
##  <a name="isvalidsource"></a>COleChangeSourceDialog::IsValidSource  
 この関数では、新しいソースが有効かを判断します。  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>戻り値  
 新しいソースが、有効な場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 後でのみこの関数の呼び出し[DoModal](#domodal)返します**IDOK**します。  
  
 詳細については、次を参照してください。、 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)構造体[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]します。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [関数のクラス](../../mfc/reference/coledialog-class.md)


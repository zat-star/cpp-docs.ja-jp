---
title: "CComboBoxEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComboBoxEx
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes, CComboBoxEx class
- Windows common controls [C++], extended combo boxes
- common controls [C++], extended combo boxes
- combo boxes [C++], CComboBoxEx class
- Internet Explorer 4.0 common controls
- CComboBoxEx class
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e88ed701111b49e3a5d3b32868bfad8e77206086
ms.lasthandoff: 02/24/2017

---
# <a name="ccomboboxex-class"></a>CComboBoxEx クラス
イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。  
  
## <a name="syntax"></a>構文  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|`CComboBoxEx` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|コンボ ボックスを作成し、それにアタッチ、`CComboBoxEx`オブジェクトです。|  
|[CComboBoxEx::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してコンボ ボックスを作成しに、 **ComboBoxEx**オブジェクトです。|  
|[CComboBoxEx::DeleteItem](#deleteitem)|項目を削除、 **ComboBoxEx**コントロールです。|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|子のコンボ ボックス コントロールへのポインターを取得します。|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|編集コントロールの部分を識別するハンドルを取得、 **ComboBoxEx**コントロールです。|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|使用されている拡張スタイルを取得、 **ComboBoxEx**コントロールです。|  
|[CComboBoxEx::GetImageList](#getimagelist)|割り当てられているイメージ リストへのポインターを取得、 **ComboBoxEx**コントロールです。|  
|[CComboBoxEx::GetItem](#getitem)|項目の情報の取得、指定された**ComboBoxEx**項目。|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|内容をユーザーが変更されたかどうかを判断、 **ComboBoxEx** 」と入力してコントロールを編集します。|  
|[CComboBoxEx::InsertItem](#insertitem)|新しい項目を挿入、 **ComboBoxEx**コントロールです。|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|内で拡張スタイルを設定、 **ComboBoxEx**コントロールです。|  
|[CComboBoxEx::SetImageList](#setimagelist)|用のイメージ リストの設定、 **ComboBoxEx**コントロールです。|  
|[CComboBoxEx::SetItem](#setitem)|内の項目の属性を設定、 **ComboBoxEx**コントロールです。|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|Visual スタイル拡張コンボ ボックス コントロールを設定します。|  
  
## <a name="remarks"></a>コメント  
 使用して`CComboBoxEx`コンボ ボックス コントロールを作成するが不要に独自のイメージを描画コードを実装します。 代わりに、`CComboBoxEx`はイメージ リストのイメージをアクセスします。  
  
## <a name="image-list-support"></a>イメージ リストのサポート  
 標準のコンボ ボックスでは、コンボ ボックスの所有者は、イメージを描画するには、オーナー描画コントロールとコンボ ボックスの作成を担当します。 使用すると`CComboBoxEx`、描画スタイルを設定する必要はありません**CBS_OWNERDRAWFIXED**と**CBS_HASSTRINGS**は暗黙的に指定するためです。 それ以外の場合、描画操作を実行するコードを記述する必要があります。 A`CComboBoxEx`コントロールが項目ごとに最大&3; つのイメージをサポートしています: 選択された状態、選択されていない状態では、およびオーバーレイ イメージのいずれかです。  
  
## <a name="styles"></a>スタイル  
 `CComboBoxEx`スタイルをサポートしている**CBS_SIMPLE**、 **CBS_DROPDOWN**、 **CBS_DROPDOWNLIST**、および**WS_CHILD**します。 ウィンドウを作成するときに渡される他のすべてのスタイルがコントロールによって無視されます。 ウィンドウが作成されると、使用できるその他のコンボ ボックスのスタイルを呼び出して、`CComboBoxEx`メンバー関数[拡張](#setextendedstyle)します。 これらのスタイルは、次のことができます。  
  
-   大文字小文字を区別する一覧で、文字列の検索をセットします。  
  
-   コンボ ボックス コントロールを作成 ('/')、スラッシュを使用して円記号 ('\\')、および期間 ('. ') の単語の区切り記号として文字です。 これは、CTRL キーと方向のキーボード ショートカットを使用して、語間を移動するようにします。  
  
-   コンボ ボックス コントロールを表示またはイメージを表示しませんを設定します。 イメージが表示されていない場合、コンボ ボックスは、イメージに対応するテキストのインデントを削除できます。  
  
-   クリップが含まれているより広いコンボ ボックス幅の狭いコンボ ボックス コントロールを作成します。  
  
 これらのスタイル フラグの詳細については [を使用して CComboBoxEx](../../mfc/using-ccomboboxex.md)します。  
  
## <a name="item-retention-and-callback-item-attributes"></a>アイテムの保持と項目のコールバック属性  
 Win32 構造の項目とイメージ、インデントの幅、およびテキスト文字列のインデックスなどのアイテムの情報が格納されている[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 構造体には、コールバック フラグに対応するメンバーも含まれます。  
  
 詳細な概念的な詳細については、次を参照してください。[を使用して CComboBoxEx](../../mfc/using-ccomboboxex.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="a-nameccomboboxexa--ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a>CComboBoxEx::CComboBoxEx  
 作成するには、このメンバー関数を呼び出す、`CComboBoxEx`オブジェクトです。  
  
```  
CComboBoxEx();
```  
  
##  <a name="a-namecreatea--ccomboboxexcreate"></a><a name="create"></a>CComboBoxEx::Create  
 コンボ ボックスを作成し、それにアタッチ、`CComboBoxEx`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 コンボ ボックスに適用されるコンボ ボックス スタイルの組み合わせを指定します。 参照してください**解説**の下のスタイルの詳細についてです。  
  
 `rect`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造コンボ ボックスのサイズと位置です。  
  
 `pParentWnd`  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)コンボ ボックスの親ウィンドウにオブジェクト (通常、 `CDialog`)。 ことはできません**NULL**します。  
  
 `nID`  
 コンボ ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが正常に作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 作成、 `CComboBoxEx`&2; つのステップ内のオブジェクト。  
  
1.  呼び出す[CComboBoxEx](#ccomboboxex)を構築する、`CComboBoxEx`オブジェクトです。  
  
2.  このメンバー関数、拡張の Windows コンボ ボックスを作成し、それにアタッチする、`CComboBoxEx`オブジェクトです。  
  
 呼び出すと**作成**、MFC コモン コントロールを初期化します。  
  
 コンボ ボックスを作成するときに、次のコンボ ボックス スタイルの一部またはすべてを選択できます。  
  
- **CBS_SIMPLE**  
  
- **CBS_DROPDOWN**  
  
- **CBS_DROPDOWNLIST**  
  
- **CBS_AUTOHSCROLL**  
  
- **WS_CHILD**  
  
 ウィンドウを作成するときに渡される他のすべてのスタイルは無視されます。 **ComboBoxEx**コントロールも追加機能が備わっている拡張スタイルをサポートします。 これらのスタイルは「 [ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 これらのスタイルを呼び出すことによって設定[拡張](#setextendedstyle)します。  
  
 コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに**作成**します。  
  
##  <a name="a-namecreateexa--ccomboboxexcreateex"></a><a name="createex"></a>CComboBoxEx::CreateEx  
 拡張コンボ ボックス コントロール (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CComboBoxEx`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 コンボ ボックス コントロールのスタイル。 参照してください[作成](#create)スタイルの一覧です。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに**作成**、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
 `CreateEx`指定された拡張ウィンドウ スタイルを使用してコントロールが作成され`dwExStyle`します。 必要があります拡張スタイルに固有の設定拡張コンボ ボックス コントロールを使用して、[拡張](#setextendedstyle)します。 などを使用して`CreateEx`としてこのようなスタイルを設定する**WS_EX_CONTEXTHELP**を使用して、`SetExtendedStyle`としてこのようなスタイルを設定する**CBES_EX_CASESENSITIVE**します。 詳細については、トピックに記載されているスタイルを参照してください。 [ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namedeleteitema--ccomboboxexdeleteitem"></a><a name="deleteitem"></a>CComboBoxEx::DeleteItem  
 項目を削除、 **ComboBoxEx**コントロールです。  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `iIndex`  
 削除する項目の&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 コントロール内の残りの項目の数。 場合`iIndex`が有効でない関数を返します**返します**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装して[CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 DeleteItem を呼び出すときに、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージを**CBEN_DELETEITEM**を親ウィンドウに通知が送信されます。  
  
##  <a name="a-namegetcomboboxctrla--ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a>CComboBoxEx::GetComboBoxCtrl  
 内のコンボ ボックス コントロールへのポインターを取得するには、このメンバー関数を呼び出す、`CComboBoxEx`オブジェクトです。  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CComboBox`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 `CComboBoxEx`カプセル化されている親ウィンドウ コントロールでは、`CComboBox`です。  
  
 `CComboBox`戻り値によって指されるオブジェクトが一時オブジェクトし、次のアイドル状態の処理時に破棄します。  
  
##  <a name="a-namegeteditctrla--ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a>CComboBoxEx::GetEditCtrl  
 コンボ ボックスのエディット コントロールへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CEdit](../../mfc/reference/cedit-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 A`CComboBoxEx`使用して作成されたときに、コントロールが編集ボックスを使用して、 **CBS_DROPDOWN**スタイル。  
  
 `CEdit`戻り値によって指されるオブジェクトが一時オブジェクトし、次のアイドル状態の処理時に破棄します。  
  
##  <a name="a-namegetextendedstylea--ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a>CComboBoxEx::GetExtendedStyle  
 使用する拡張スタイルを取得するには、このメンバー関数を呼び出す、`CComboBoxEx`コントロールです。  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `DWORD`コンボ ボックス コントロールの使用されている拡張スタイルを表す値。  
  
### <a name="remarks"></a>コメント  
 参照してください[ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、これらのスタイル。  
  
##  <a name="a-namegetimagelista--ccomboboxexgetimagelist"></a><a name="getimagelist"></a>CComboBoxEx::GetImageList  
 使用されるイメージ リストへのポインターを取得するには、このメンバー関数を呼び出す、`CComboBoxEx`コントロールです。  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトです。 失敗したかどうか、このメンバー関数を返します**NULL**します。  
  
### <a name="remarks"></a>コメント  
 `CImageList`戻り値によって指されるオブジェクトが一時オブジェクトし、次のアイドル状態の処理時に破棄します。  
  
##  <a name="a-namegetitema--ccomboboxexgetitem"></a><a name="getitem"></a>CComboBoxEx::GetItem  
 項目の情報の取得、指定された**ComboBoxEx**項目。  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCBItem`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装して[CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namehaseditchangeda--ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a>CComboBoxEx::HasEditChanged  
 内容をユーザーが変更されたかどうかを判断、 **ComboBoxEx** 」と入力してコントロールを編集します。  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールの編集ボックスに、ユーザーが入力した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装して[CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameinsertitema--ccomboboxexinsertitem"></a><a name="insertitem"></a>CComboBoxEx::InsertItem  
 新しい項目を挿入、 **ComboBoxEx**コントロールです。  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCBItem`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目情報を受け取る構造体。 この構造体には、項目のコールバック フラグの値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 インデックスが正常に終了した場合に新しい項目の挿入それ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
 呼び出すと`InsertItem`、 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)メッセージを[CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764)を親ウィンドウに通知が送信されます。  
  
##  <a name="a-namesetextendedstylea--ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a>CComboBoxEx::SetExtendedStyle  
 コンボ ボックス コントロールを拡張するための拡張スタイルを設定するには、このメンバー関数を呼び出します。  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExMask`  
 A`DWORD`のスタイルを示す値`dwExStyles`の影響を受けています。 拡張のスタイルのみ`dwExMask`は変更されます。 その他のすべてのスタイルが保持されます。 このパラメーターが&0; の場合、すべてのスタイルの場合`dwExStyles`影響を受けます。  
  
 `dwExStyles`  
 A`DWORD`コンボ ボックスを含む値は、拡張スタイルがコントロールに対して設定を制御します。  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`コントロールの使用されていた拡張スタイルを表す値。  
  
### <a name="remarks"></a>コメント  
 参照してください[ComboBoxEx コントロールの拡張スタイル](http://msdn.microsoft.com/library/windows/desktop/bb775742)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]詳細については、これらのスタイル。  
  
 拡張ウィンドウ スタイルを使用してコントロールを拡張コンボ ボックスを作成するには使用[CreateEx](#createex)します。  
  
##  <a name="a-namesetimagelista--ccomboboxexsetimagelist"></a><a name="setimagelist"></a>CComboBoxEx::SetImageList  
 用のイメージ リストの設定、 **ComboBoxEx**コントロールです。  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>パラメーター  
 `pImageList`  
 ポインター、`CImageList`オブジェクトで使用するイメージを含む、`CComboBoxEx`コントロールです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトによって使用されていた画像を含む、`CComboBoxEx`コントロールです。 **NULL**イメージ リストが既に設定されていない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装して[CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 既定値 エディット コントロールの高さを変更する場合は、Win32 関数を呼び出して[SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545)を呼び出した後、コントロールのサイズを変更する`SetImageList`、正しく表示されるか。  
  
 `CImageList`戻り値によって指されるオブジェクトが一時オブジェクトし、次のアイドル状態の処理時に破棄します。  
  
##  <a name="a-namesetitema--ccomboboxexsetitem"></a><a name="setitem"></a>CComboBoxEx::SetItem  
 内の項目の属性を設定、 **ComboBoxEx**コントロールです。  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCBItem`  
 ポインター、[受け取る](http://msdn.microsoft.com/library/windows/desktop/bb775746)項目情報を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、メッセージの機能を実装して[CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-namesetwindowthemea--ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a>CComboBoxEx::SetWindowTheme  
 Visual スタイル拡張コンボ ボックス コントロールを設定します。  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>パラメーター  
 `pszSubAppName`  
 拡張コンボ ボックスの表示スタイル設定を含む Unicode 文字列へのポインター。  
  
### <a name="return-value"></a>戻り値  
 戻り値は使用されません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の機能をエミュレートする、 [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790) 」の説明に従って、メッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCIE](../../visual-cpp-samples.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)


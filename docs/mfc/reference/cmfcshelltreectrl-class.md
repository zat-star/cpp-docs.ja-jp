---
title: "CMFCShellTreeCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
dev_langs:
- C++
helpviewer_keywords:
- CMFCShellTreeCtrl class
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cf9c7c3577646895546c443c975a92431194d3f4
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeCtrl クラス
`CMFCShellTreeCtrl`クラスを拡張[CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)シェル項目の階層を表示することによって機能します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|有効またはショートカット メニューを無効にします。|  
|[CMFCShellTreeCtrl::GetFlags](#getflags)|渡されるフラグの組み合わせを返す[IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066)します。|  
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|アイテムのパスを取得します。|  
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|ポインターを返す、 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)これと共に使用されるオブジェクト`CMFCShellTreeCtrl`オブジェクト エクスプ ローラーのようなウィンドウを作成します。|  
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|このメンバー関数は、このウィンドウに適用される通知メッセージを受信したときに、このウィンドウの親ウィンドウによって呼び出されます。 (上書き[CWnd::OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify))。|  
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||  
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||  
|[CMFCShellTreeCtrl::Refresh](#refresh)|更新して、現在の再描画`CMFCShellTreeCtrl`オブジェクトです。|  
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|指定した PIDL または文字列のパスを基に適切なツリー コントロール項目を選択します。|  
|[CMFCShellTreeCtrl::SetFlags](#setflags)|ツリーのコンテキスト フィルターを適用するためのフラグを設定 (で使用するフラグのような`IShellFolder::EnumObjects`)。|  
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|現在の間の関係を設定`CMFCShellTreeCtrl`オブジェクトと`CMFCShellListCtrl`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、`CTreeCtrl`クラスをツリーに Windows シェル項目を含めるためにプログラムを有効にしています。 このクラスの関連付けできる、`CMFCShellListCtrl`完了エクスプ ローラー ウィンドウを作成するオブジェクト。 次に、ツリー内の項目の選択に表示されます Windows シェル項目の一覧、関連付けられたリスト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 `CMFCShellTreeCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxshelltreeCtrl.h  
  
## <a name="example"></a>例  
 次の例では、`CMFCShellTreeCtrl` クラスのオブジェクトを作成する方法を示します。 このコード スニペットの一部である、 [Explorer サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_Explorer&4;](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer&#5;](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]  
  
##  <a name="enableshellcontextmenu"></a>CMFCShellTreeCtrl::EnableShellContextMenu  
 ショートカット メニューを有効にします。  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 ショートカット メニューを有効にするかどうかを指定するブール値。  
  
##  <a name="getflags"></a>CMFCShellTreeCtrl::GetFlags  
 設定されているフラグを返す、 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトです。  
  
```  
DWORD GetFlags() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`現在フラグの組み合わせを指定する値を設定します。  
  
### <a name="remarks"></a>コメント  
 フラグを設定、`CMFCShellTreeCtrl`メソッドに送信される[IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066)オブジェクトが更新されるたびにします。 フラグを変更することができます、 [CMFCShellTreeCtrl::SetFlags](#setflags)メソッドです。  
  
##  <a name="getitempath"></a>CMFCShellTreeCtrl::GetItemPath  
 内の項目のパスを取得、 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトです。  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    HTREEITEM htreeItem = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `strPath`  
 文字列パラメーターへの参照。 メソッドは、このパラメーターに、アイテムのパスを書き込みます。  
  
 [入力] `htreeItem`  
 このメソッドは、このツリー コントロール項目のパスを取得します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドが失敗した場合、`strPath`空の文字列が含まれています。  
  
 指定しない場合`hTreeItem`、このメソッドは、現在選択されているアイテムの文字列を取得しようとしています。 項目が選択されていない場合、`hTreeItem`は`NULL`、このメソッドは失敗します。  
  
##  <a name="getrelatedlist"></a>CMFCShellTreeCtrl::GetRelatedList  
 ポインターを返す、 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)これに関連付けられているオブジェクト[CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトです。  
  
```  
CMFCShellListCtrl* GetRelatedList() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMFCShellListCtrl`ツリー コントロール オブジェクトに関連付けられているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 使用して、`CMFCShellListCtrl`オブジェクトと共に、`CMFCShellTreeCtrl`オブジェクト エクスプ ローラーのようなウィンドウを作成することができます。 メソッドを使用して[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)に&2; つのクラスを関連付けます。 フレームワークが自動的に更新が関連付けられている後、`CMFCShellListCtrl`場合に選択、`CMFCShellTreeCtrl`変更します。  
  
##  <a name="onchildnotify"></a>CMFCShellTreeCtrl::OnChildNotify  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL OnChildNotify(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pLResult);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `message`  
 [入力] `wParam`  
 [入力] `lParam`  
 [入力] `pLResult`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ongetitemicon"></a>CMFCShellTreeCtrl::OnGetItemIcon  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pItem`  
 [入力] `bSelected`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ongetitemtext"></a>CMFCShellTreeCtrl::OnGetItemText  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pItem`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="refresh"></a>CMFCShellTreeCtrl::Refresh  
 更新して再描画、 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)します。  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>コメント  
 表示される項目の階層構造を更新するには、このメソッドを呼び出して、`CMFCShellTreeCtrl`です。  
  
##  <a name="selectpath"></a>CMFCShellTreeCtrl::SelectPath  
 内の項目を選択、 [CMFCShellTreeCtrl クラス](../../mfc/reference/cmfcshelltreectrl-class.md)指定されたパスに基づきます。  
  
```  
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszPath`  
 アイテムのパスを指定する文字列。  
  
 [入力] `lpidl`  
 項目を指定する PIDL  
  
### <a name="return-value"></a>戻り値  
 `S_OK`成功した場合`E_FAIL`それ以外の場合。  
  
##  <a name="setflags"></a>CMFCShellTreeCtrl::SetFlags  
 ツリーのコンテキスト フィルターを適用するためのフラグを設定します。  
  
```  
void SetFlags(
    DWORD dwFlags,  
    BOOL bRefresh = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dwFlags`  
 設定するフラグ。  
  
 [入力] `bRefresh`  
 ブール値を指定するかどうか、`CMFCShellTreeCtrl`すぐに更新する必要があります。  
  
### <a name="remarks"></a>コメント  
 `CMFCShellTreeCtrl`すべてにフラグを設定するパス[IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066)します。 さまざまなフラグの値に関する詳細については、次を参照してください。 [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066)します。  
  
##  <a name="setrelatedlist"></a>CMFCShellTreeCtrl::SetRelatedList  
 関連付けます、 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)オブジェクトを[CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)オブジェクトです。  
  
```  
void SetRelatedList(CMFCShellListCtrl* pShellList);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pShellList`  
 ポインター、`CMFCShellListCtrl`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメソッドに関連付けます、`CMFCShellListCtrl`で、`CMFCShellTreeCtrl`です。 これらのオブジェクトは、エクスプ ローラーのようなウィンドウとして表示することがあります: ユーザーのオブジェクトを選択した場合、 `CMFCShellTreeCtrl`、内のアイテムに関連付けられている、`CMFCShellListCtrl`が自動的に更新します。  
  
 メソッドを使用して[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)を取得する、`CMFCShellListCtrl`に関連付けられている、`CMFCShellTreeCtrl`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl クラス](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl クラス](../../mfc/reference/cmfcshelllistctrl-class.md)


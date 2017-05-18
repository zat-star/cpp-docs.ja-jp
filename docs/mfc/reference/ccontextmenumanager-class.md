---
title: "CContextMenuManager クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
dev_langs:
- C++
helpviewer_keywords:
- CContextMenuManager class
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
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
ms.openlocfilehash: fab322d0c60b33454504620170d9c77a98401ec8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager クラス
`CContextMenuManager`オブジェクト管理ショートカット メニュー、コンテキスト メニューとも呼ばれます。  
  
## <a name="syntax"></a>構文  
  
```  
class CContextMenuManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|`CContextMenuManager` オブジェクトを構築します。|  
|`CContextMenuManager::~CContextMenuManager`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CContextMenuManager::AddMenu](#addmenu)|新しいショートカット メニューを追加します。|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|指定されたリソース ID に関連付けられているメニューへのハンドルを返します|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|指定されたメニュー名に一致するメニューにハンドルを返します。|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|メニュー名の一覧を返します。|  
|[CContextMenuManager::LoadState](#loadstate)|Windows レジストリに格納されているショートカット メニューを読み込みます。|  
|[CContextMenuManager::ResetState](#resetstate)|コンテキスト メニュー マネージャーからショートカット メニューをクリアします。|  
|[CContextMenuManager::SaveState](#savestate)|ショートカット メニューを Windows レジストリに保存します。|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|コントロールかどうか、`CContextMenuManager`新しいショートカット メニューを表示すると、active のショートカット メニューを閉じます。|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|指定したショートカット メニューを表示します。|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|指定したショートカット メニューを表示します。 選択されたメニュー コマンドのインデックスを返します。|  
  
## <a name="remarks"></a>コメント  
 `CContextMenuManager`ショートカット メニューを管理、一貫した外観であることを確認します。  
  
 作成しないで、`CContextMenuManager`手動でのオブジェクトします。 アプリケーションのフレームワークを作成、`CContextMenuManager`オブジェクトです。 ただし、呼び出す必要があります[CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager)アプリケーションが初期化される場合。 コンテキスト マネージャーを初期化した後、メソッドを使用して[CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)アプリケーションのコンテキスト マネージャーへのポインターを取得します。  
  
 実行時にショートカット メニューを作成するにを呼び出して`AddMenu`します。 受信側の最初のユーザー入力なくのメニューを表示する場合は、呼び出す`ShowPopupMenu`します。 `TrackPopupMenu`メニューを作成し、ユーザー入力を待機するときに表示されます。 `TrackPopupMenu`ユーザーが何も選択せずに終了した場合は、選択したコマンドまたは 0 のインデックスを返します。  
  
 `CContextMenuManager`も保存して、Windows レジストリにその状態を読み込むことができます。  
  
## <a name="example"></a>例  
 次の例では、メニューを追加、`CContextMenuManager`オブジェクト、およびアクティブなポップアップ メニューを閉じる方法と、`CContextMenuManager`オブジェクトには、新しいポップアップ メニューが表示されます。 このコード スニペットの一部である、[カスタム ページ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_CustomPages&4;](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CContextMenuManager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcontextmenumanager.h  
  
##  <a name="addmenu"></a>CContextMenuManager::AddMenu  
 新しいショートカット メニューを追加、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)します。  
  
```  
BOOL AddMenu(
    UINT uiMenuNameResId,  
    UINT uiMenuResId);

 
BOOL AddMenu(
    LPCTSTR lpszName,  
    UINT uiMenuResId);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiMenuNameResId`  
 新しいメニューの名前を含む文字列のリソース ID。  
  
 [入力] `uiMenuResId`  
 メニュー リソースの id。  
  
 [入力] `lpszName`  
 新しいメニューの名前を表す文字列。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。メソッドが失敗した場合は 0。  
  
### <a name="remarks"></a>コメント  
 このメソッドは失敗`uiMenuResId`が無効か、同じ名前の別のメニューに既に存在するかどうか、`CContextMenuManager`です。  
  
##  <a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager  
 構築、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)オブジェクトです。  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>コメント  
 ほとんどの場合は作成しないで、`CContextMenuManager`手動でします。 アプリケーションのフレームワークを作成、`CContextMenuManager`オブジェクトです。 呼び出す必要があります[CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager)アプリケーションの初期化中にします。 コンテキスト マネージャーへのポインターを取得する[CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager)します。  
  
##  <a name="getmenubyid"></a>CContextMenuManager::GetMenuById  
 指定されたリソース ID に関連付けられているメニューへのハンドルを返します  
  
```  
HMENU GetMenuById(UINT nMenuResId) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nMenuResId`  
 メニューのリソース ID です。  
  
### <a name="return-value"></a>戻り値  
 関連付けられている menu へのハンドルまたは`NULL`メニューが見つからない場合。  
  
##  <a name="getmenubyname"></a>CContextMenuManager::GetMenuByName  
 特定のメニューには、ハンドルを返します。  
  
```  
HMENU GetMenuByName(
    LPCTSTR lpszName,  
    UINT* puiOrigResID = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszName`  
 取得するメニューの名前を表す文字列。  
  
 [出力] `puiOrigResID`  
 `UINT` へのポインター。 このパラメーターには、指定されたメニューのリソース ID が含まれる場合が見つかりました。  
  
### <a name="return-value"></a>戻り値  
 指定された名前に一致するメニューへのハンドル`lpszName`します。 `NULL`呼ばれるメニューがないかどうかは`lpszName`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドには、一致するメニューが検出されると`lpszName`、`GetMenuByName`パラメーターでのメニュー リソース ID を格納`puiOrigResID`します。  
  
##  <a name="getmenunames"></a>CContextMenuManager::GetMenuNames  
 追加されたメニュー名のリストを返す、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)します。  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `listOfNames`  
 参照、 [CStringList](../../mfc/reference/cstringlist-class.md)パラメーター。 このメソッドは、このパラメーターにあるメニュー名の一覧を書き込みます。  
  
##  <a name="loadstate"></a>CContextMenuManager::LoadState  
 関連付けられている情報を読み込み、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)Windows レジストリからです。  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 レジストリ キーの相対パスを含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `lpszProfileName`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パスをアプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase)と[CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase)それぞれします。  
  
 メソッドを使用して[CContextMenuManager::SaveState](#savestate)ショートカット メニューをレジストリに保存します。  
  
##  <a name="resetstate"></a>CContextMenuManager::ResetState  
 すべての項目に関連付けられているショートカット メニューから消去、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)します。  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メソッドが成功した場合`FALSE`障害が発生した場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ポップアップ メニューをクリアし、削除してから、`CContextMenuManager`です。  
  
##  <a name="savestate"></a>CContextMenuManager::SaveState  
 関連付けられている情報を保存、 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)Windows レジストリにします。  
  
```  
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 レジストリ キーの相対パスを含む文字列です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `lpszProfileName`パラメーターは、レジストリ エントリの絶対パスではありません。 相対パスをアプリケーションの既定のレジストリ キーの末尾に追加することをお勧めします。 を取得または既定のレジストリ キーを設定するには、メソッドを使用して[CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase)と[CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase)それぞれします。  
  
 メソッドを使用して[CContextMenuManager::LoadState](#loadstate)レジストリからショートカット メニューをロードします。  
  
##  <a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenu  
 コントロールかどうか、 [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md)新しいポップアップ メニューを表示するときに、アクティブなポップアップ メニューを閉じます。  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 アクティブなポップアップ メニューを閉じるかどうかを制御するブール値パラメーター。 値`TRUE`アクティブなポップアップ メニューが閉じられていないことを示します。 `FALSE`アクティブなポップアップ メニューを閉じたことを示します。  
  
### <a name="remarks"></a>コメント  
 既定では、`CContextMenuManager`アクティブなポップアップ メニューを閉じます。  
  
##  <a name="showpopupmenu"></a>CContextMenuManager::ShowPopupMenu  
 指定したショートカット メニューを表示します。  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bRightAlign = FALSE);

 
virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bAutoDestroy = TRUE,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiMenuResId`  
 このメソッドが表示されるメニューのリソース ID です。  
  
 [入力] `x`  
 水平方向のショートカット メニューのクライアント座標でのオフセットします。  
  
 [入力] `y`  
 クライアント座標でショートカット メニューを縦方向のオフセット  
  
 [入力] `pWndOwner`  
 ショートカット メニューの親ウィンドウへのポインター。  
  
 [入力] `bOwnMessage`  
 メッセージのルーティング方法を示すブール値パラメーターです。 場合`bOwnMessage`は`FALSE`MFC の標準的なルーティングが使用されます。 それ以外の場合、`pWndOwner`メッセージを受信します。  
  
 [入力] `hmenuPopup`  
 このメソッドが表示されるメニューのハンドル。  
  
 [入力] `bAutoDestroy`  
 メニューが自動的に破棄されるかどうかを示すブール値パラメーターです。  
  
 [入力] `bRightAlign`  
 メニュー項目がどのように配置するかを示すブール値パラメーターです。 場合`bRightAlign`は`TRUE`メニューが右から左への読み取り順序の右側に配置します。  
  
### <a name="return-value"></a>戻り値  
 最初のメソッドのオーバー ロードは、メソッドが正常にメニューを表示する場合は 0 以外を返しますそれ以外の場合 0 を返します。 2 番目のメソッドのオーバー ロードへのポインターを返す[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)正しく。 そうしないと、ショートカット メニューが表示される場合`NULL`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドがメソッドに似ています[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)点で、両方のメソッドは、ショートカット メニューを表示します。 ただし、`TrackPopupMenu`選択されたメニュー コマンドのインデックスを返します。  
  
 場合、パラメーター`bAutoDestroy`は`FALSE`、手動で呼び出す必要があります、継承された`DestroyMenu`メモリ リソースを解放します。 既定の実装`ShowPopupMenu`パラメーターを使用しない`bAutoDestroy`します。 将来使用するため、またはから派生したカスタム クラスを提供して、`CContextMenuManager`クラスです。  
  
##  <a name="trackpopupmenu"></a>CContextMenuManager::TrackPopupMenu  
 指定されたショートカット メニューを表示し、選択したショートカット メニュー コマンドのインデックスを返します。  
  
```  
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hmenuPopup`  
 このメソッドは、表示されるショートカット メニューのハンドル。  
  
 [入力] `x`  
 水平方向のショートカット メニューのクライアント座標でのオフセットします。  
  
 [入力] `y`  
 垂直方向のショートカット メニューのクライアント座標でのオフセットします。  
  
 [入力] `pWndOwner`  
 ショートカット メニューの親ウィンドウへのポインター。  
  
 [入力] `bRightAlign`  
 メニュー項目がどのように配置するかを示すブール値パラメーターです。 場合`bRightAlign`は`TRUE`メニューが右から左への読み取り順序の右側に配置します。 場合`bRightAlign`は`FALSE`メニューが左から右への読み取り順序の左側に配置します。  
  
### <a name="return-value"></a>戻り値  
 ユーザーが選択したコマンドのメニュー コマンド IDユーザーがメニュー コマンドを選択せずに、ショートカット メニューを閉じた場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ショートカット メニューを表示するモーダル呼び出しとして機能します。 アプリケーションは、ユーザーはショートカット メニューを閉じるか、コマンドを選択するまでコードで、次の行には続行されません。 別の方法として使用できるショートカット メニューを表示する[CContextMenuManager::ShowPopupMenu](#showpopupmenu)します。 メソッドでは、モーダルの呼び出しではありませんし、選択したコマンドの ID は返されません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)


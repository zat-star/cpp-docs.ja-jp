---
title: "CMenu クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
dev_langs:
- C++
helpviewer_keywords:
- HMENU
- menus, class
- menus, base class
- menus, creating
- menus, managing
- CMenu class
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
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
ms.openlocfilehash: dcd353bf0be5d23c1782347f54b16a875ed190ed
ms.lasthandoff: 02/24/2017

---
# <a name="cmenu-class"></a>CMenu クラス
Windows の `HMENU`をカプセル化したものです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMenu : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMenu::CMenu](#cmenu)|`CMenu` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMenu::AppendMenu](#appendmenu)|このメニューの末尾に新しい項目を追加します。|  
|[CMenu::Attach](#attach)|Windows メニュー ハンドルをアタッチ、`CMenu`オブジェクトです。|  
|[CMenu::CheckMenuItem](#checkmenuitem)|チェック マークを横に配置またはポップアップ メニューのメニュー項目からチェック マークを削除します。|  
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|メニュー項目の横にあるラジオ ボタンを配置し、すべてのグループ内の他のメニュー項目から、ラジオ ボタンを削除します。|  
|[CMenu::CreateMenu](#createmenu)|空のメニューを作成し、それをアタッチ、`CMenu`オブジェクトです。|  
|[CMenu::CreatePopupMenu](#createpopupmenu)|空のポップアップ メニューを作成し、それをアタッチ、`CMenu`オブジェクトです。|  
|[なる](#deletemenu)|メニューから、指定した項目を削除します。 メニュー項目に関連付けられているポップアップ メニューがある場合は、ポップアップ メニューへのハンドルを破棄し、それによって使用されるメモリを解放します。|  
|[CMenu::DeleteTempMap](#deletetempmap)|一時的な削除`CMenu`によって作成されたオブジェクト、`FromHandle`メンバー関数。|  
|[メニューを破棄](#destroymenu)|接続されているメニューの破棄、`CMenu`オブジェクトし、メニューが占有されているメモリを解放します。|  
|[CMenu::Detach](#detach)|Windows メニュー ハンドルからのデタッチ、`CMenu`オブジェクトおよびハンドルを返します。|  
|[CMenu::DrawItem](#drawitem)|オーナー描画メニュー変更のビジュアルな部分のときに、フレームワークによって呼び出されます。|  
|[CMenu::EnableMenuItem](#enablemenuitem)|有効、無効化、または (グレー表示) を使用できなくなります。 メニュー項目です。|  
|[CMenu::FromHandle](#fromhandle)|ポインターを返す、`CMenu`オブジェクトの Windows メニュー ハンドルを指定します。|  
|[CMenu::GetDefaultItem](#getdefaultitem)|指定されたメニューで、既定のメニュー項目を決定します。|  
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|メニューに関連付けられているヘルプ コンテキスト ID を取得します。|  
|[CMenu::GetMenuInfo](#getmenuinfo)|特定のメニューに関する情報を取得します。|  
|[CMenu::GetMenuItemCount](#getmenuitemcount)|ポップアップまたは最上位メニュー内の項目数を決定します。|  
|[CMenu::GetMenuItemID](#getmenuitemid)|指定した位置にあるメニュー項目のメニュー項目の識別子を取得します。|  
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|メニュー項目に関する情報を取得します。|  
|[CMenu::GetMenuState](#getmenustate)|ポップアップ メニューで、指定されたメニュー項目または項目の数の状態を返します。|  
|[CMenu::GetMenuString](#getmenustring)|指定されたメニュー項目のラベルを取得します。|  
|[CMenu::GetSafeHmenu](#getsafehmenu)|返します。、`m_hMenu`これによってラップされた`CMenu`オブジェクトです。|  
|[CMenu::GetSubMenu](#getsubmenu)|ポップアップ メニューへのポインターを取得します。|  
|[CMenu::InsertMenu](#insertmenu)|その他の項目をたどって、メニューで指定した位置に新しいメニュー項目を挿入します。|  
|[CMenu::InsertMenuItem](#insertmenuitem)|メニュー内の指定位置に新しいメニュー項目を挿入します。|  
|[CMenu::LoadMenu](#loadmenu)|実行可能ファイルからメニュー リソースを読み込み、それにアタッチ、`CMenu`オブジェクトです。|  
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|メモリ上のメニューのテンプレートからメニューを読み込み、それにアタッチ、`CMenu`オブジェクトです。|  
|[CMenu::MeasureItem](#measureitem)|オーナー描画メニューは、の作成時に、メニューの大きさを調べるためにフレームワークによって呼び出されます。|  
|[CMenu::ModifyMenu](#modifymenu)|指定した位置にある既存のメニュー項目を変更します。|  
|[CMenu::RemoveMenu](#removemenu)|指定されたメニューから、関連付けられているポップアップ メニューのメニュー項目を削除します。|  
|[CMenu::SetDefaultItem](#setdefaultitem)|指定されたメニューの既定のメニュー項目を設定します。|  
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|メニューに関連するヘルプ コンテキスト ID を設定します。|  
|[CMenu::SetMenuInfo](#setmenuinfo)|特定のメニューに関する情報を設定します。|  
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|指定されたチェック マークのビットマップをメニュー項目に関連付けます。|  
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|メニュー項目に関する情報を変更します。|  
|[CMenu::TrackPopupMenu](#trackpopupmenu)|指定した場所にフローティング ポップアップ メニューを表示し、ポップアップ メニュー項目の選択を追跡します。|  
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|指定した場所にフローティング ポップアップ メニューを表示し、ポップアップ メニュー項目の選択を追跡します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CMenu::operator HMENU](#operator_hmenu)|メニュー オブジェクトのハンドルを取得します。|  
|[CMenu::operator! =](#operator_neq)|2 つのメニュー オブジェクトが等しくないかどうかを判断します。|  
|[CMenu::operator = =](#operator_eq_eq)|2 つのメニュー オブジェクトが等しいかどうかを判断します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMenu::m_hMenu](#m_hmenu)|接続されている Windows メニューへのハンドルを指定する、`CMenu`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 作成する、追跡、更新、およびメニューを破棄するため、メンバー関数を提供します。  
  
 作成、`CMenu`オブジェクトとして、ローカルのスタック フレームにし、呼び出す`CMenu`の必要に応じて、[新規] メニューを操作するメンバー関数。 次に、 [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) 、メニュー、ウィンドウを設定する直後にへの呼び出しによって、`CMenu`オブジェクトの[デタッチ](#detach)メンバー関数。 `CWnd::SetMenu`メンバー関数、ウィンドウのメニューを新規作成 を設定、によってメニューの変更を反映するように再描画されるウィンドウおよびメニューの所有権をウィンドウにも渡します。 呼び出し**デタッチ**デタッチ、`HMENU`から、`CMenu`オブジェクト、そのため時に、ローカル`CMenu`変数がスコープ外に渡す、`CMenu`オブジェクトのデストラクターは不要になった所有しているメニューを破棄しようとはしません。 メニュー自体は、ウィンドウが破棄されるときに自動的に破棄されます。  
  
 使用することができます、 [LoadMenuIndirect](#loadmenuindirect)メンバー関数を作成、メモリ内のテンプレートからメニューへの呼び出しによってリソースから作成] メニューの [ [LoadMenu](#loadmenu)はより簡単に維持し、メニュー リソース自体が作成され、メニュー エディターで変更することができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="appendmenu"></a>CMenu::AppendMenu  
 メニューの最後に、新しい項目を追加します。  
  
```  
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 メニューに追加されたときに、新しいメニュー項目の状態に関する情報を指定します。 1 つまたは複数の「解説」セクションに示されている値で構成されます。  
  
 `nIDNewItem`  
 新しいメニュー項目のコマンド ID を指定したり、`nFlags`に設定されている**ならば**、メニュー ハンドル ( `HMENU`) のポップアップ メニュー。 `nIDNewItem`パラメーターは無視されます (必要ではない) 場合`nFlags`に設定されている**MF_SEPARATOR**します。  
  
 `lpszNewItem`  
 新しいメニュー項目の内容を指定します。 `nFlags`の解釈にパラメーターを使用`lpszNewItem`次のようにします。  
  
|nFlags|LpszNewItem の解釈|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|アプリケーションでメニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値は、処理するときに、アプリケーションで使用できる`WM_MEASUREITEM`と`WM_DRAWITEM`メッセージです。 値が格納されている、**取得**それらのメッセージで提供される構造体のメンバーです。|  
|**MF_STRING**|Null で終わる文字列へのポインターが含まれています。 これは、既定の解釈です。|  
|**MF_SEPARATOR**|`lpszNewItem` (必要ありません) パラメーターは無視されます。|  
  
 *pBmp*  
 指す、`CBitmap`メニュー項目として使用されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションで値を設定 メニュー項目の状態を指定できます`nFlags`します。 `nIDNewItem`ポップアップ メニューでは、指定が追加されます メニューの一部となります。 メニューが破棄されると、追加したメニューも破棄されます。 追加したメニューからデタッチする必要があります、`CMenu`競合を避けるためのオブジェクト。 なお**MF_STRING**と`MF_OWNERDRAW`のビットマップのバージョンが無効な`AppendMenu`です。  
  
 次のとおりに設定することができるフラグ`nFlags`:  
  
- ****でトグルとして機能**MF_UNCHECKED**項目の横にある既定のチェック マークを配置します。 チェック マークのビットマップをアプリケーションが提供する場合 (を参照してください、 [SetMenuItemBitmaps](#setmenuitembitmaps)メンバー関数)、「にあるチェック マーク」ビットマップが表示されます。  
  
- **MF_UNCHECKED**でトグルとして機能**を**項目の横にあるチェック ボックスをオフにします。 チェック マークのビットマップをアプリケーションが提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「チェック マークをオフ」ビットマップが表示されます。  
  
- **MF_DISABLED**ように選択することはできませんが、淡色表示には、メニュー項目を無効にします。  
  
- `MF_ENABLED`選択することができ、グレーの状態から復元できるようには、メニュー項目を有効にします。  
  
- **MF_GRAYED**選択ことはできませんし、淡色表示にするようにメニュー項目を無効にします。  
  
- **MF_MENUBARBREAK**静的メニューまたはポップアップ メニューに新しい列の新しい行にアイテムを配置します。 新しいポップアップ メニュー列が、古い列から垂直方向の境界線で区切られます。  
  
- **MF_MENUBREAK**静的メニューまたはポップアップ メニューに新しい列の新しい行にアイテムを配置します。 列の間の区切り線は適用されません。  
  
- `MF_OWNERDRAW`オーナー描画項目に項目を指定します。 メニューを所有するウィンドウを受け取る最初に、メニューが表示されたら、`WM_MEASUREITEM`高さおよびメニュー項目の幅を取得するメッセージ。 `WM_DRAWITEM`メッセージがたび、所有者は、メニュー項目の表示を更新する必要があります。 このオプションは、トップレベルのメニュー項目に対して無効ではありません。  
  
- **ならば**メニュー項目が関連付けられているポップアップ メニューを持つことを指定します。 ID パラメーターでは、ポップアップ メニューの項目に関連するを識別するハンドルを指定します。 ポップアップ メニュー項目を最上位レベルのポップアップ メニューまたは階層のポップアップ メニューを追加するために使用します。  
  
- **MF_SEPARATOR**水平分割線を描画します。 ポップアップ メニューでのみ使用できます。 この行の淡色表示になります、無効になっている、または強調表示されていることはできません。 その他のパラメーターは無視されます。  
  
- **MF_STRING**メニュー項目が文字の文字列であることを指定します。  
  
 次のグループのそれぞれには、フラグが相互に排他的で一緒に使用できませんが一覧表示します。  
  
- **MF_DISABLED**、 `MF_ENABLED`、および**MF_GRAYED**  
  
- **MF_STRING**、 `MF_OWNERDRAW`、 **MF_SEPARATOR**、およびビットマップ バージョン  
  
- **MF_MENUBARBREAK**と**MF_MENUBREAK**  
  
- ****と**MF_UNCHECKED**  
  
 内に存在するメニュー (ウィンドウが表示されます) かどうか、ウィンドウが変更されて、アプリケーションを呼び出す必要があります[かかわらず](../../mfc/reference/cwnd-class.md#drawmenubar)します。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::CreateMenu](#createmenu)します。  
  
##  <a name="attach"></a>CMenu::Attach  
 アタッチに既存の Windows メニュー、`CMenu`オブジェクトです。  
  
```  
BOOL Attach(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMenu`  
 Windows メニューへのハンドルを指定します。  
  
### <a name="return-value"></a>戻り値  
 操作が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューに既にアタッチされている場合、この関数は呼び出されませんが、`CMenu`オブジェクトです。 メニューのハンドルに格納されている、`m_hMenu`データ メンバーです。  
  
 使用することを操作するメニューが既にウィンドウに関連付けられている場合、[とき](../../mfc/reference/cwnd-class.md#getmenu)メニューへのハンドルを取得します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&21;](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="checkmenuitem"></a>CMenu::CheckMenuItem  
 チェック マークを追加またはポップアップ メニューのメニュー項目からチェック マークを削除します。  
  
```  
UINT CheckMenuItem(
    UINT nIDCheckItem,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDCheckItem`  
 によって決定される、確認するメニュー項目を指定`nCheck`します。  
  
 `nCheck`  
 メニュー項目を確認して、メニュー内の項目の位置を確認する方法を指定します。 `nCheck`パラメーターの組み合わせを指定できます**を**または**MF_UNCHECKED**と**MF_BYPOSITION**または**とき**フラグ。 これらのフラグは、ビットごとの OR 演算子を使用して組み合わせることができます。 次の意味があります。  
  
- **とき**パラメーターが既存のメニュー項目のコマンド ID を使用することを指定します。 既定値です。  
  
- **MF_BYPOSITION**パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。  
  
- ****でトグルとして機能**MF_UNCHECKED**項目の横にある既定のチェック マークを配置します。  
  
- **MF_UNCHECKED**でトグルとして機能**を**項目の横にあるチェック ボックスをオフにします。  
  
### <a name="return-value"></a>戻り値  
 項目の以前の状態:**を**または**MF_UNCHECKED**、または 0 xffffffff メニュー項目が存在しなかった場合です。  
  
### <a name="remarks"></a>コメント  
 `nIDCheckItem`パラメーターを変更する項目を指定します。  
  
 `nIDCheckItem`メニュー項目と同様に、ポップアップ メニュー項目のパラメーターが見つかる場合があります。 ポップアップ メニュー項目を確認するのには、特別な手順は必要ありません。 トップレベルのメニュー項目をチェックすることはできません。 関連付けられているメニュー項目の識別子がないために、位置によってポップアップ メニュー項目をチェックする必要があります。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::GetMenuState](#getmenustate)します。  
  
##  <a name="checkmenuradioitem"></a>CMenu::CheckMenuRadioItem  
 指定されたメニュー項目を確認し、オプション項目を使用します。  
  
```  
BOOL CheckMenuRadioItem(
    UINT nIDFirst,  
    UINT nIDLast,  
    UINT nIDItem,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDFirst`  
 指定 (ID またはの値に応じて、オフセットと`nFlags`) オプション ボタン グループの最初のメニュー項目です。  
  
 `nIDLast`  
 指定 (ID またはの値に応じて、オフセットと`nFlags`) オプション ボタン グループの最後のメニュー項目です。  
  
 `nIDItem`  
 指定 (ID またはの値に応じて、オフセットと`nFlags`) オプション ボタンがオンになっているグループ内の項目。  
  
 `nFlags`  
 解釈を指定`nIDFirst`、 `nIDLast`、および`nIDItem`次のようにします。  
  
|nFlags|解釈|  
|------------|--------------------|  
|**とき**|パラメーターが既存のメニュー項目のコマンド ID を利用すればことを指定します。 これは、どちらの場合の既定値**とき**も**MF_BYPOSITION**が設定されます。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合 0  
  
### <a name="remarks"></a>コメント  
 同時に、関数は関連付けられているグループの他のすべてのメニュー項目をオフにし、それらの項目のオプション項目の種類のフラグをクリアします。 チェック マークのビットマップではなくラジオのボタン (または行頭文字) のビットマップを使用してチェックされている項目が表示されます。  
  
### <a name="example"></a>例  
  例を参照してください[ON_COMMAND_RANGE](http://msdn.microsoft.com/library/c52719fc-dd6e-48c9-af79-383f48d608e0)します。  
  
##  <a name="cmenu"></a>CMenu::CMenu  
 空のメニューを作成し、それをアタッチ、`CMenu`オブジェクトです。  
  
```  
CMenu();
```  
  
### <a name="remarks"></a>コメント  
 作成または読み込みのメンバー関数のいずれかを呼び出すまで、メニューは作成されません**CMenu:**  
  
- [CreateMenu](#createmenu)  
  
- [CreatePopupMenu](#createpopupmenu)  
  
- [LoadMenu](#loadmenu)  
  
- [LoadMenuIndirect](#loadmenuindirect)  
  
- [添付](#attach)  
  
##  <a name="createmenu"></a>CMenu::CreateMenu  
 メニューを作成し、それをアタッチ、`CMenu`オブジェクトです。  
  
```  
BOOL CreateMenu();
```  
  
### <a name="return-value"></a>戻り値  
 メニューが正常に作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューは、最初は空です。 メニュー項目を追加するにを使用、`AppendMenu`または`InsertMenu`メンバー関数。  
  
 メニューがウィンドウに割り当てられている場合、ウィンドウが破棄されるときに自動的に破棄されます。  
  
 終了前に、アプリケーションは、メニューがウィンドウに割り当てられていない場合は、メニューに関連付けられているシステム リソースを解放する必要があります。 アプリケーション メニューを呼び出して、 [DestroyMenu](#destroymenu)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&22;](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]  
  
##  <a name="createpopupmenu"></a>CMenu::CreatePopupMenu  
 ポップアップ メニューを作成し、それをアタッチ、`CMenu`オブジェクトです。  
  
```  
BOOL CreatePopupMenu();
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニューが作成された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューは、最初は空です。 メニュー項目を追加するにを使用、`AppendMenu`または`InsertMenu`メンバー関数。 アプリケーションでは、既存のメニューまたはポップアップ メニューに、ポップアップ メニューを追加できます。 `TrackPopupMenu`フローティング ポップアップ メニューとしてこのメニューを表示して、ポップアップ メニューで選択内容を追跡するために、メンバー関数を使用することがあります。  
  
 メニューがウィンドウに割り当てられている場合、ウィンドウが破棄されるときに自動的に破棄されます。 既存のメニューにメニューを追加する場合は、そのメニューが破棄されるときに自動的に破棄されます。  
  
 終了前に、アプリケーションは、メニューがウィンドウに割り当てられていない場合は、ポップアップ メニューに関連付けられているシステム リソースを解放する必要があります。 アプリケーション メニューを呼び出して、 [DestroyMenu](#destroymenu)メンバー関数。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::CreateMenu](#createmenu)します。  
  
##  <a name="deletemenu"></a>なる  
 メニューから項目を削除します。  
  
```  
BOOL DeleteMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPosition`  
 によって決定される、削除するにはメニュー項目を指定`nFlags`します。  
  
 `nFlags`  
 解釈に使用`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターが既存のメニュー項目のコマンド ID を利用すればことを指定します。 これは、どちらの場合の既定値**とき**も**MF_BYPOSITION**が設定されます。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニュー項目に関連付けられているポップアップ メニューがある場合`DeleteMenu`ポップアップ メニューへのハンドルを破棄し、ポップアップ メニューで使用されるメモリを解放します。  
  
 内に存在するメニュー (ウィンドウが表示されます) かどうか、ウィンドウが変更されて、アプリケーションを呼び出す必要があります[かかわらず](../../mfc/reference/cwnd-class.md#drawmenubar)します。  
  
### <a name="example"></a>例  
  例を参照してください[とき](../../mfc/reference/cwnd-class.md#getmenu)します。  
  
##  <a name="deletetempmap"></a>CMenu::DeleteTempMap  
 によって自動的と呼ばれる、`CWinApp`アイドル時間のハンドラーは、一時的なを削除`CMenu`によって作成されたオブジェクト、 [FromHandle](#fromhandle)メンバー関数。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>コメント  
 `DeleteTempMap`一時的に接続されている Windows メニュー オブジェクトをデタッチ`CMenu`オブジェクトを削除する前に、`CMenu`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing 第&23;](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]  
  
##  <a name="destroymenu"></a>メニューを破棄  
 メニューのおよび使用された Windows のシステム リソースを破棄します。  
  
```  
BOOL DestroyMenu();
```  
  
### <a name="return-value"></a>戻り値  
 メニューが破棄された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューが切り離された、`CMenu`オブジェクトが破棄される前にします。 Windows`DestroyMenu`で自動的に呼び出される関数は、`CMenu`デストラクターです。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::CreateMenu](#createmenu)します。  
  
##  <a name="detach"></a>CMenu::Detach  
 Windows のメニューからのデタッチ、`CMenu`オブジェクトおよびハンドルを返します。  
  
```  
HMENU Detach();
```  
  
### <a name="return-value"></a>戻り値  
 型のハンドル`HMENU`、成功した場合は、Windows メニュー **NULL**します。  
  
### <a name="remarks"></a>コメント  
 `m_hMenu`データ メンバーに設定されている**NULL**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&21;](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="drawitem"></a>CMenu::DrawItem  
 オーナー描画メニュー変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 `itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行するのには、描画の動作を定義します。 オーナー描画の描画を実装するには、この関数をオーバーライド`CMenu`オブジェクトです。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`このメンバー関数が終了する前にします。  
  
 参照してください[体](../../mfc/reference/cwnd-class.md#ondrawitem)の詳細については、`DRAWITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 次のコードは、MFC [CTRLTEST](../../visual-cpp-samples.md)サンプル。  
  
 [!code-cpp[NVC_MFCWindowing #&24;](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]  
  
##  <a name="enablemenuitem"></a>CMenu::EnableMenuItem  
 有効、無効化、またはメニュー項目を使用できなくなります。  
  
```  
UINT EnableMenuItem(
    UINT nIDEnableItem,  
    UINT nEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDEnableItem*  
 によって決定される、有効にするメニュー項目を指定`nEnable`します。 このパラメーターには、標準のメニュー項目だけでなく、ポップアップ メニュー項目を指定できます。  
  
 `nEnable`  
 実行するアクションを指定します。 組み合わせを可能に**MF_DISABLED**、 `MF_ENABLED`、または**MF_GRAYED**と**とき**または**MF_BYPOSITION**します。 これらの値は、ビットごとの OR 演算子を使用して組み合わせることができます。 これらの値には、次の意味があります。  
  
- **とき**パラメーターが既存のメニュー項目のコマンド ID を使用することを指定します。 既定値です。  
  
- **MF_BYPOSITION**パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。  
  
- **MF_DISABLED**ように選択することはできませんが、淡色表示には、メニュー項目を無効にします。  
  
- `MF_ENABLED`選択することができ、グレーの状態から復元できるようには、メニュー項目を有効にします。  
  
- **MF_GRAYED**選択ことはできませんし、淡色表示にするようにメニュー項目を無効にします。  
  
### <a name="return-value"></a>戻り値  
 以前の状態 ( **MF_DISABLED**、 `MF_ENABLED`、または**MF_GRAYED**) 有効でない場合は-1 を返します。  
  
### <a name="remarks"></a>コメント  
 [CreateMenu](#createmenu)、[項目](#insertmenu)、[メニュー](#modifymenu)、および[LoadMenuIndirect](#loadmenuindirect)メンバー関数は、メニュー項目の状態 (有効、無効になっている、または淡色表示になります) を設定もできます。  
  
 使用して、 **MF_BYPOSITION**値には、適切なを使用するアプリケーションが必要です。`CMenu`します。 場合、 `CMenu`  メニューのバーを使用すると、トップレベルのメニュー項目 (メニュー バーのアイテム) が影響を受けます。 位置によってポップアップまたは入れ子になったポップアップ メニューの項目の状態を設定するアプリケーションを指定する必要があります、`CMenu`ポップアップ メニューのです。  
  
 アプリケーションで指定すると、**とき**フラグは、Windows は下にあるすべてのポップアップ メニュー項目を確認、 `CMenu`。 したがって、重複するメニュー項目が存在しない限り、を使用して、 `CMenu`  メニューのバーは、十分なです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#25;](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CMenu::FromHandle  
 ポインターを返す、`CMenu`メニューに識別する Windows ハンドルを指定したオブジェクト。  
  
```  
static CMenu* PASCAL FromHandle(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMenu`  
 メニューへの Windows ハンドル。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMenu`一時的または永続的にある場合があります。  
  
### <a name="remarks"></a>コメント  
 場合、`CMenu`オブジェクトが、Windows のメニュー オブジェクトが一時的に既にアタッチされていない`CMenu`オブジェクトが作成され、接続されています。  
  
 この一時`CMenu`オブジェクトは、次のアプリケーションが、すべての一時オブジェクトの削除時、イベント ループのアイドル時間までのみ有効です。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::CreateMenu](#createmenu)します。  
  
##  <a name="getdefaultitem"></a>CMenu::GetDefaultItem  
 指定されたメニューで、既定のメニュー項目を決定します。  
  
```  
UINT GetDefaultItem(
    UINT gmdiFlags,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *gmdiFlags*  
 この関数でのメニュー項目を検索する方法を指定する値。 このパラメーターには、なし、1 つ、または、次の値の組み合わせを指定できます。  
  
|値|説明|  
|-----------|-------------|  
|**GMDI_GOINTOPOPUPS**|既定のアイテムをサブメニューを開く場合は、関数である、対応するサブメニューを再帰的に検索を指定します。 サブメニューには、既定の項目がなければ、戻り値は、サブメニューを開く項目を識別します。<br /><br /> 既定では、サブメニューを開く項目であるかどうかにかかわらず、指定されたメニューの既定の最初の項目を返します。|  
|**GMDI_USEDISABLED**|関数が無効になっている場合でも、既定の項目を返す、することを指定します。<br /><br /> 既定では、関数は無効になっているか、淡色表示されている項目をスキップします。|  
  
 `fByPos`  
 メニュー項目の識別子またはの位置を取得するかどうかを指定する値。 このパラメーターは場合**FALSE**識別子が返されます。 それ以外の場合、位置が返されます。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は識別子またはメニュー項目の位置を使用します。 関数が失敗した場合、戻り値は - 1 です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 関数の動作を実装して[GetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647976)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::InsertMenu](#insertmenu)します。  
  
##  <a name="getmenucontexthelpid"></a>CMenu::GetMenuContextHelpId  
 ID に関連付けられているコンテキスト ヘルプを取得`CMenu`します。  
  
```  
DWORD GetMenuContextHelpId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ID が現在関連付けられているコンテキスト ヘルプ`CMenu`; いずれかがある場合はそれ以外の場合&0; です。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::InsertMenu](#insertmenu)します。  
  
##  <a name="getmenuinfo"></a>CMenu::GetMenuInfo  
 メニューの情報を取得します。  
  
```  
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcmi`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/ms647575)構造、メニューの情報を格納します。  
  
### <a name="return-value"></a>戻り値  
 戻り値は&0; 以外の値は、関数が成功すると、それ以外の場合、戻り値は&0; です。  
  
### <a name="remarks"></a>コメント  
 この関数では、メニューに関する情報を取得します。  
  
##  <a name="getmenuitemcount"></a>CMenu::GetMenuItemCount  
 ポップアップまたは最上位メニュー内の項目数を決定します。  
  
```  
UINT GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は、メニュー内の項目数それ以外の場合 –&1; です。  
  
### <a name="example"></a>例  
  例を参照してください[とき](../../mfc/reference/cwnd-class.md#getmenu)します。  
  
##  <a name="getmenuitemid"></a>CMenu::GetMenuItemID  
 定義された位置にあるメニュー項目のメニュー項目 id 取得`nPos`します。  
  
```  
UINT GetMenuItemID(int nPos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 位置 (0 から始まる) メニュー項目の ID を取得するを指定します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、ポップアップ メニューで指定された項目の項目の ID。 指定したアイテムに (ポップアップ メニュー内の項目) ではなくポップアップ メニューがある場合、戻り値は –&1; を使用します。 場合`nPos`に対応する、**区切り**メニュー項目、戻り値は 0 です。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::InsertMenu](#insertmenu)します。  
  
##  <a name="getmenuiteminfo"></a>CMenu::GetMenuItemInfo  
 メニュー項目に関する情報を取得します。  
  
```  
BOOL GetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `uItem`  
 識別子またはに関する情報を取得するメニュー項目の位置。 このパラメーターの意味は、の値によって異なります。`ByPos`します。  
  
 `lpMenuItemInfo`  
 ポインター、 [MENUITEMINFO](http://msdn.microsoft.com/library/windows/desktop/ms647578)」を参照して、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]、メニューに関する情報を格納します。  
  
 `fByPos`  
 意味を指定する値`nIDItem`です。 既定では、`ByPos`は**FALSE**では、メニュー項目の識別子。 場合`ByPos`に設定されていない**FALSE**、メニュー項目の位置を示します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は&0; 以外の値です。 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには、Win32 関数を使用して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の動作を実装して、Win32 関数の[GetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms647980)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 MFC 実装に注意してください。 `GetMenuItemInfo`、メニューへのハンドルを使用しないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&26;](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]  
  
##  <a name="getmenustate"></a>CMenu::GetMenuState  
 ポップアップ メニューで、指定されたメニュー項目または項目の数の状態を返します。  
  
```  
UINT GetMenuState(
    UINT nID,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 によって決定されるメニュー項目 ID を指定`nFlags`します。  
  
 `nFlags`  
 性質を指定`nID`します。 次の値のいずれかを指定できます。  
  
- **とき**パラメーターが既存のメニュー項目のコマンド ID を使用することを指定します。 既定値です。  
  
- **MF_BYPOSITION**パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。  
  
### <a name="return-value"></a>戻り値  
 指定した項目が存在しない場合、0 xffffffff の値です。 場合*nId*ポップアップ メニューを識別する上位バイトには、ポップアップ メニューの項目数が含まれています。 と下位バイトは、ポップアップ メニューに関連付けられているメニュー フラグを格納します。 戻り値は次の一覧から値のマスク (論理 OR) をそれ以外の場合 (このマスクは、メニューの状態を説明項目*nId*識別)。  
  
- ****でトグルとして機能**MF_UNCHECKED**項目の横にある既定のチェック マークを配置します。 チェック マークのビットマップをアプリケーションが提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「にあるチェック マーク」ビットマップが表示されます。  
  
- **MF_DISABLED**ように選択することはできませんが、淡色表示には、メニュー項目を無効にします。  
  
- `MF_ENABLED`選択することができ、グレーの状態から復元できるようには、メニュー項目を有効にします。 この定数の値は 0 になります。この値を使用する場合、アプリケーションのテストは失敗の 0 と比較しないでください。  
  
- **MF_GRAYED**選択ことはできませんし、淡色表示にするようにメニュー項目を無効にします。  
  
- **MF_MENUBARBREAK**静的メニューまたはポップアップ メニューに新しい列の新しい行にアイテムを配置します。 新しいポップアップ メニュー列が、古い列から垂直方向の境界線で区切られます。  
  
- **MF_MENUBREAK**静的メニューまたはポップアップ メニューに新しい列の新しい行にアイテムを配置します。 列の間の区切り線は適用されません。  
  
- **MF_SEPARATOR**水平分割線を描画します。 ポップアップ メニューでのみ使用できます。 この行の淡色表示になります、無効になっている、または強調表示されていることはできません。 その他のパラメーターは無視されます。  
  
- **MF_UNCHECKED**でトグルとして機能**を**項目の横にあるチェック ボックスをオフにします。 チェック マークのビットマップをアプリケーションが提供する場合 (を参照してください、`SetMenuItemBitmaps`メンバー関数)、「チェック マークをオフ」ビットマップが表示されます。 この定数の値は 0 になります。この値を使用する場合、アプリケーションのテストは失敗の 0 と比較しないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&27;](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]  
  
##  <a name="getmenustring"></a>CMenu::GetMenuString  
 指定されたメニュー項目のラベルを指定したバッファーにコピーします。  
  
```  
int GetMenuString(
    UINT nIDItem,  
    LPTSTR lpString,  
    int nMaxCount,  
    UINT nFlags) const;  
  
int GetMenuString(
    UINT nIDItem,  
    CString& rString,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDItem`  
 値に応じて、メニューにメニュー項目の整数識別子またはメニュー項目のオフセットを指定`nFlags`します。  
  
 `lpString`  
 ラベルを受信するバッファーへのポインター。  
  
 `rString`  
 参照、`CString`をコピーしたメニュー文字列を受け取るオブジェクト。  
  
 `nMaxCount`  
 コピーされるラベルの文字) 単位で最大長を指定します。 指定された最大値よりも長い場合は、ラベル`nMaxCount`、余分な文字は切り捨てられます。  
  
 `nFlags`  
 指定の解釈、`nIDItem`パラメーター。 次の値のいずれかを指定できます。  
  
|nFlags|NIDItem の解釈|  
|------------|-------------------------------|  
|**とき**|パラメーターが既存のメニュー項目のコマンド ID を利用すればことを指定します。 これは、どちらの場合の既定値**とき**も**MF_BYPOSITION**が設定されます。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
### <a name="return-value"></a>戻り値  
 実際の null 終端文字を含まない、バッファーにコピーされた文字数を指定します。  
  
### <a name="remarks"></a>コメント  
 `nMaxCount`パラメーターは、文字列の終端の null 文字に対応するラベルの文字数より&1; 大きいにする必要があります。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::InsertMenu](#insertmenu)します。  
  
##  <a name="getsafehmenu"></a>CMenu::GetSafeHmenu  
 返します。、`HMENU`これによってラップされた`CMenu`オブジェクト、または**NULL** `CMenu`ポインター。  
  
```  
HMENU GetSafeHmenu() const;  
```  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::LoadMenu](#loadmenu)します。  
  
##  <a name="getsubmenu"></a>CMenu::GetSubMenu  
 取得、`CMenu`ポップアップ メニューのオブジェクト。  
  
```  
CMenu* GetSubMenu(int nPos) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 メニューに含まれるポップアップ メニューの位置を指定します。 位置の値は、最初のメニュー項目の 0 から始まります。 この関数では、ポップアップ メニューの識別子を使用できません。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CMenu`オブジェクト`m_hMenu`メンバーは、ポップアップ メニューが指定された位置に存在する場合に、ポップアップ メニューへのハンドルを含むそれ以外の場合**NULL**します。 場合、`CMenu`オブジェクトが存在しない、一時的なものを作成します。 `CMenu`返されたポインターを格納しない必要があります。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::TrackPopupMenu](#trackpopupmenu)します。  
  
##  <a name="insertmenu"></a>CMenu::InsertMenu  
 指定された位置に新しいメニュー項目を挿入`nPosition`し、その他のアイテムで、メニューの下に移動します。  
  
```  
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPosition`  
 新しいメニュー項目の挿入前にあるメニュー項目を指定します。 `nFlags`の解釈にパラメーターを使用できる`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターが既存のメニュー項目のコマンド ID を利用すればことを指定します。 これは、どちらの場合の既定値**とき**も**MF_BYPOSITION**が設定されます。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。 場合`nPosition`-1 で、新しいメニュー項目がメニューの末尾に追加されます。|  
  
 `nFlags`  
 指定する方法`nPosition`解釈され、メニューに追加されたときに、新しいメニュー項目の状態に関する情報を指定します。 設定することがフラグの一覧は、次を参照してください。、[は](#appendmenu)メンバー関数。 複数の値を指定するを組み合わせることでビットごとの OR 演算子を使用、**とき**または**MF_BYPOSITION**フラグ。  
  
 `nIDNewItem`  
 新しいメニュー項目のコマンド ID を指定したり、`nFlags`に設定されている**ならば**、メニュー ハンドル ( `HMENU`)、ポップアップ メニューのです。 `nIDNewItem`パラメーターは無視されます (必要ではない) 場合`nFlags`に設定されている**MF_SEPARATOR**します。  
  
 `lpszNewItem`  
 新しいメニュー項目の内容を指定します。 `nFlags`解釈に使用できる`lpszNewItem`次のようにします。  
  
|nFlags|LpszNewItem の解釈|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|アプリケーションでメニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値はアプリケーション内で使用できる、**取得**によって提供される構造体のメンバー、[よう](http://msdn.microsoft.com/library/windows/desktop/bb775925)と[WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923)メッセージです。 メニュー項目が最初に表示されるかが変更される、これらのメッセージが送信されます。|  
|**MF_STRING**|Null で終わる文字列への long ポインターが含まれています。 これは、既定の解釈です。|  
|**MF_SEPARATOR**|`lpszNewItem` (必要ありません) パラメーターは無視されます。|  
  
 *pBmp*  
 指す、`CBitmap`メニュー項目として使用されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションで値を設定 メニュー項目の状態を指定できます`nFlags`します。  
  
 内に存在するメニュー (ウィンドウが表示されます) かどうか、ウィンドウが変更されて、アプリケーションを呼び出す必要があります`CWnd::DrawMenuBar`します。  
  
 ときに`nIDNewItem`ポップアップ メニューの指定が挿入されるメニューの一部となります。 メニューが破棄されると、挿入されたメニューも破棄されます。 挿入メニューからデタッチする必要があります、`CMenu`競合を避けるためのオブジェクト。  
  
 マルチ ドキュメント インターフェイス (MDI) 子ウィンドウが最大化されているアクティブ ポイントとアプリケーションは、MDI アプリケーションのメニューにポップアップ メニューをこの関数を呼び出すことを指定することによって挿入される場合、 **MF_BYPOSITION**フラグは、メニューは、まま遠くに予想よりも&1; つの位置に挿入します。 これは、アクティブな MDI 子ウィンドウのコントロールのメニューが MDI フレーム ウィンドウのメニュー バーの最初の位置に挿入されるために発生します。 メニューを正しく配置するには、アプリケーションは、それ以外の場合に使用される位置の値に 1 を追加する必要があります。 アプリケーションで使用できる、 **WM_MDIGETACTIVE**を現在アクティブな子ウィンドウを最大化するかどうかを判別するメッセージ。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&28;](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]  
  
##  <a name="insertmenuitem"></a>CMenu::InsertMenuItem  
 メニュー内の指定位置に新しいメニュー項目を挿入します。  
  
```  
BOOL InsertMenuItem(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `uItem`  
 説明を参照してください`uItem`で[InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `lpMenuItemInfo`  
 説明を参照してください`lpmii`で**InsertMenuItem**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `fByPos`  
 説明を参照してください`fByPosition`で**InsertMenuItem**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 この関数をラップ[InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988)に記述されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="loadmenu"></a>CMenu::LoadMenu  
 アプリケーションの実行可能ファイルからメニュー リソースを読み込み、それにアタッチ、`CMenu`オブジェクトです。  
  
```  
BOOL LoadMenu(LPCTSTR lpszResourceName);  
BOOL LoadMenu(UINT nIDResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 読み込む] メニューの [リソースの名前を表す null で終わる文字列へのポインター。  
  
 `nIDResource`  
 読み込むメニュー リソースのメニュー ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースが正常に読み込まれた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 終了前に、アプリケーションは、メニューがウィンドウに割り当てられていない場合は、メニューに関連付けられているシステム リソースを解放する必要があります。 アプリケーション メニューを呼び出して、 [DestroyMenu](#destroymenu)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&29;](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]  
  
##  <a name="loadmenuindirect"></a>CMenu::LoadMenuIndirect  
 メモリ内のメニューのテンプレートからリソースを読み込みし、それにアタッチ、`CMenu`オブジェクトです。  
  
```  
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpMenuTemplate*  
 メニューのテンプレートを指す (これは、1 つ[MENUITEMTEMPLATEHEADER](http://msdn.microsoft.com/library/windows/desktop/ms647583)構造と、1 つまたは複数のコレクション[それに続く](http://msdn.microsoft.com/library/windows/desktop/ms647581)構造体)。 これら&2; つの構造体の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 メニュー リソースが正常に読み込まれた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューのテンプレートは、1 つまたは複数のコレクションを続けてヘッダー[それに続く](http://msdn.microsoft.com/library/windows/desktop/ms647581)構造体、これらの各メニュー項目とポップアップ メニューの&1; つまたは複数を含めることができます。  
  
 バージョン番号には、0 を指定する必要があります。  
  
 **MtOption**フラグを含める必要があります**MF_END**ポップアップ リストの最後の項目とメインのリストの最後の項目。 参照してください、`AppendMenu`のフラグを他のメンバー関数。 **MtId**からメンバーを省略する必要があります、**それに続く**ときに構造化**ならば**で指定された**mtOption**します。  
  
 割り当てられた領域、**それに続く**構造体に十分な大きさである必要があります**mtString** null で終わる文字列としてのメニュー項目の名を格納します。  
  
 終了前に、アプリケーションは、メニューがウィンドウに割り当てられていない場合は、メニューに関連付けられているシステム リソースを解放する必要があります。 アプリケーション メニューを呼び出して、 [DestroyMenu](#destroymenu)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&30;](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]  
  
##  <a name="m_hmenu"></a>CMenu::m_hMenu  
 指定、`HMENU`に接続されている Windows メニューのハンドル、`CMenu`オブジェクトです。  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::LoadMenu](#loadmenu)します。  
  
##  <a name="measureitem"></a>CMenu::MeasureItem  
 オーナー描画スタイルを持つメニューが作成されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMeasureItemStruct`  
 ポインター、`MEASUREITEMSTRUCT`構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数は何もしません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`構造、メニューのディメンションの Windows に通知します。  
  
 参照してください[CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)の詳細については、`MEASUREITEMSTRUCT`構造体。  
  
### <a name="example"></a>例  
 次のコードは、MFC [CTRLTEST](../../visual-cpp-samples.md)サンプル。  
  
 [!code-cpp[NVC_MFCWindowing #&31;](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]  
  
##  <a name="modifymenu"></a>CMenu::ModifyMenu  
 指定した位置にある既存のメニュー項目が変更`nPosition`します。  
  
```  
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPosition`  
 変更するメニュー項目を指定します。 `nFlags`の解釈にパラメーターを使用できる`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターが既存のメニュー項目のコマンド ID を利用すればことを指定します。 これは、どちらの場合の既定値**とき**も**MF_BYPOSITION**が設定されます。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
 `nFlags`  
 指定する方法`nPosition`解釈され、メニュー項目に対する変更に関する情報について説明します。 設定することがフラグの一覧は、次を参照してください。、[は](#appendmenu)メンバー関数。  
  
 `nIDNewItem`  
 変更されたメニュー項目のコマンド ID を指定したり、`nFlags`に設定されている**ならば**、メニュー ハンドル ( `HMENU`) ポップアップ メニューのです。 `nIDNewItem`パラメーターは無視されます (必要ではない) 場合`nFlags`に設定されている**MF_SEPARATOR**します。  
  
 `lpszNewItem`  
 新しいメニュー項目の内容を指定します。 `nFlags`の解釈にパラメーターを使用できる`lpszNewItem`次のようにします。  
  
|nFlags|LpszNewItem の解釈|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|アプリケーションでメニュー項目に関連付けられている追加のデータを維持するために使用できるアプリケーションによって提供される 32 ビット値が含まれています。 この 32 ビット値は、処理するときに、アプリケーションで使用できる**MF_MEASUREITEM**と**が**です。|  
|**MF_STRING**|Null で終わる文字列をまたはの long ポインターを含む、`CString`です。|  
|**MF_SEPARATOR**|`lpszNewItem` (必要ありません) パラメーターは無視されます。|  
  
 *pBmp*  
 指す、`CBitmap`メニュー項目として使用されるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、メニュー項目の新しい状態を指定値を設定して`nFlags`します。 この関数では、メニュー項目に関連付けられているポップアップ メニューが置き換え場合、は、古いポップアップ メニューを破棄し、ポップアップ メニューで使用されるメモリを解放します。  
  
 ときに`nIDNewItem`ポップアップ メニューの指定が挿入されるメニューの一部となります。 メニューが破棄されると、挿入されたメニューも破棄されます。 挿入メニューからデタッチする必要があります、`CMenu`競合を避けるためのオブジェクト。  
  
 内に存在するメニュー (ウィンドウが表示されます) かどうか、ウィンドウが変更されて、アプリケーションを呼び出す必要があります`CWnd::DrawMenuBar`します。 既存のメニュー項目の属性を変更するには使用する非常に短く、`CheckMenuItem`と`EnableMenuItem`メンバー関数。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::InsertMenu](#insertmenu)します。  
  
##  <a name="operator_hmenu"></a>CMenu::operator HMENU  
 この演算子のハンドルの取得を使用して、`CMenu`オブジェクトです。  
  
```  
operator HMENU() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合のハンドル、`CMenu`オブジェクト。 それ以外の場合、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 ハンドルを使用して、Windows Api を直接呼び出すことができます。  
  
##  <a name="operator_neq"></a>CMenu::operator! =  
 2 つのメニューが等しく論理的にないかどうかを判断します。  
  
```  
BOOL operator!=(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `menu`  
 A`CMenu`比較対象のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 左側にあるメニュー オブジェクトが右側にあるメニュー オブジェクトと等しくないかどうか。  
  
##  <a name="operator_eq_eq"></a>CMenu::operator = =  
 2 つのメニューが論理的に等しいかどうかを決定します。  
  
```  
BOOL operator==(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `menu`  
 A`CMenu`比較対象のオブジェクト。  
  
### <a name="remarks"></a>コメント  
 左側にあるメニュー オブジェクトが等しいかどうか (の観点で、`HMENU`値) の右側にあるメニュー オブジェクトにします。  
  
##  <a name="removemenu"></a>CMenu::RemoveMenu  
 メニューのメニュー項目に関連付けられているポップアップ メニューを削除します。  
  
```  
BOOL RemoveMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPosition`  
 削除するメニュー項目を指定します。 `nFlags`の解釈にパラメーターを使用できる`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターが既存のメニュー項目のコマンド ID を利用すればことを指定します。 これは、どちらの場合の既定値**とき**も**MF_BYPOSITION**が設定されます。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
 `nFlags`  
 指定する方法`nPosition`解釈されます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニューが再利用できるように、ポップアップ メニューのハンドルは破棄しません。 この関数を呼び出す前に、アプリケーションを呼び出すことがあります、`GetSubMenu`ポップアップを取得するメンバー関数を`CMenu`オブジェクトを再利用できるようにします。  
  
 内に存在するメニュー (ウィンドウが表示されます) かどうか、ウィンドウが変更されて、アプリケーションを呼び出す必要があります`CWnd::DrawMenuBar`します。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::InsertMenu](#insertmenu)します。  
  
##  <a name="setdefaultitem"></a>CMenu::SetDefaultItem  
 指定されたメニューの既定のメニュー項目を設定します。  
  
```  
BOOL SetDefaultItem(
    UINT uItem,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `uItem`  
 識別子または新しい既定のメニュー項目または 1 のない既定の項目の位置。 このパラメーターの意味は、の値によって異なります。`fByPos`します。  
  
 `fByPos`  
 意味を指定する値`uItem`です。 このパラメーターは、する場合**FALSE**、`uItem`メニュー項目の識別子を指定します。 それ以外の場合、メニュー項目の位置になります。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合、戻り値は&0; 以外の値です。 関数が失敗した場合は、0 を返します。 拡張エラー情報を取得するには、Win32 関数を使用して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 関数の動作を実装して[SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::InsertMenu](#insertmenu)します。  
  
##  <a name="setmenucontexthelpid"></a>CMenu::SetMenuContextHelpId  
 コンテキスト ヘルプ ID に関連付けます`CMenu`します。  
  
```  
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwContextHelpId`  
 コンテキスト ヘルプ ID に関連付ける`CMenu`します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合 0  
  
### <a name="remarks"></a>コメント  
 メニュー内のすべての項目は、この id を共有: ヘルプ コンテキスト id を個々 のメニュー項目にアタッチすることはできません。  
  
### <a name="example"></a>例  
  例を参照してください[CMenu::InsertMenu](#insertmenu)します。  
  
##  <a name="setmenuinfo"></a>CMenu::SetMenuInfo  
 メニューの情報を設定します。  
  
```  
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcmi`  
 ポインター、[保持](http://msdn.microsoft.com/library/windows/desktop/ms647575)構造、メニューの情報を格納します。  
  
### <a name="return-value"></a>戻り値  
 戻り値は&0; 以外の値は、関数が成功すると、それ以外の場合、戻り値は&0; です。  
  
### <a name="remarks"></a>コメント  
 特定のメニューに関する情報を設定するには、この関数を呼び出します。  
  
##  <a name="setmenuitembitmaps"></a>CMenu::SetMenuItemBitmaps  
 指定したビットマップをメニュー項目に関連付けます。  
  
```  
BOOL SetMenuItemBitmaps(
    UINT nPosition,  
    UINT nFlags,  
    const CBitmap* pBmpUnchecked,  
    const CBitmap* pBmpChecked);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPosition`  
 変更するメニュー項目を指定します。 `nFlags`の解釈にパラメーターを使用できる`nPosition`次のようにします。  
  
|nFlags|NPosition の解釈|  
|------------|---------------------------------|  
|**とき**|パラメーターが既存のメニュー項目のコマンド ID を利用すればことを指定します。 これは、どちらの場合の既定値**とき**も**MF_BYPOSITION**が設定されます。|  
|**MF_BYPOSITION**|パラメーターは、既存のメニュー項目の位置を指定します。 最初の項目は、位置 0 です。|  
  
 `nFlags`  
 指定する方法`nPosition`解釈されます。  
  
 `pBmpUnchecked`  
 チェックされているメニュー項目を使用してビットマップを指定します。  
  
 `pBmpChecked`  
 オンになっているメニュー項目を使用してビットマップを指定します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メニュー項目が checked または unchecked のか、メニュー項目の横にある適切なビットマップが表示されます。  
  
 いずれか`pBmpUnchecked`または`pBmpChecked`は**NULL**Windows では、属性に対応するメニュー項目の横に何が表示されます。 両方のパラメーターが場合**NULL**項目がチェックされ、項目がチェックされたときにチェック マークを削除時に、Windows が既定のチェック マークを使用します。  
  
 メニューが破棄されると、これらのビットマップは破棄されません。アプリケーションは、それらを破棄しなければなりません。  
  
 Windows **GetMenuCheckMarkDimensions**関数は、メニュー項目に使用される既定のチェック マークの寸法を取得します。 アプリケーションでは、これらの値を使用して、この関数に渡すビットマップの適切なサイズを決定します。 サイズを取得し、ビットマップを作成、それらを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#32;](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&33;](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]  
  
##  <a name="setmenuiteminfo"></a>CMenu::SetMenuItemInfo  
 メニュー項目に関する情報を変更します。  
  
```  
BOOL SetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `uItem`  
 説明を参照してください`uItem`で[SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `lpMenuItemInfo`  
 説明を参照してください`lpmii`で**SetMenuItemInfo**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `fByPos`  
 説明を参照してください`fByPosition`で**SetMenuItemInfo**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 この関数をラップ[SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001)に記述されている、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="trackpopupmenu"></a>CMenu::TrackPopupMenu  
 指定した場所にフローティング ポップアップ メニューを表示し、ポップアップ メニュー項目の選択を追跡します。  
  
```  
BOOL TrackPopupMenu(
    UINT nFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPCRECT lpRect = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFlags`  
 画面位置とマウス位置のフラグを指定します。 参照してください[TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002)の使用可能なフラグの一覧です。  
  
 *x*  
 画面座標で、ポップアップ メニューの横方向の位置を指定します。 値に応じて、`nFlags`パラメーター、メニューは左揃え、右揃え、またはこの位置から中央揃えにすることができます。  
  
 *y*  
 画面を画面座標で、メニューの上部の縦方向の位置を指定します。  
  
 `pWnd`  
 ポップアップ メニューを所有しているウィンドウを識別します。 このパラメーターを指定できません**NULL**場合でも、 **TPM_NONOTIFY**フラグが指定されています。 このウィンドウはすべて受信**WM_COMMAND**メニューからのメッセージ。 Windows 3.1 以降のバージョンで、ウィンドウを受け取りません**WM_COMMAND**までメッセージ`TrackPopupMenu`を返します。 Windows 3.0 では、ウィンドウを受け取ります**WM_COMMAND**する前にメッセージ`TrackPopupMenu`を返します。  
  
 `lpRect`  
 無視されます。  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、呼び出しの結果を返します。 [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 浮動小数点のポップアップ メニューは、画面に任意の場所に表示できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&34;](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]  
  
##  <a name="trackpopupmenuex"></a>CMenu::TrackPopupMenuEx  
 指定した場所にフローティング ポップアップ メニューを表示し、ポップアップ メニュー項目の選択を追跡します。  
  
```  
BOOL TrackPopupMenuEx(
    UINT fuFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPTPMPARAMS lptpm);
```  
  
### <a name="parameters"></a>パラメーター  
 `fuFlags`  
 拡張メニューのさまざまな関数を指定します。 すべての値の一覧とその意味では、次を参照してください。 [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003)します。  
  
 *x*  
 画面座標で、ポップアップ メニューの横方向の位置を指定します。  
  
 *y*  
 画面を画面座標で、メニューの上部の縦方向の位置を指定します。  
  
 `pWnd`  
 ポップアップ メニューを所有していると、[作成] メニューから、メッセージの受信ウィンドウへのポインター。 このウィンドウは、現在のアプリケーションからの任意のウィンドウを指定できますが、することはできません**NULL**します。 指定した場合**TPM_NONOTIFY**で、`fuFlags`パラメーター、関数はすべてのメッセージを送信しません`pWnd`します。 指すウィンドウ関数が返す必要があります`pWnd`を受信する、 **WM_COMMAND**メッセージです。  
  
 *lptpm*  
 ポインター、 [TPMPARAMS](http://msdn.microsoft.com/library/windows/desktop/ms647586)メニューの 画面の領域を指定する構造体は重複できません。 このパラメーターを指定できます**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 指定した場合**TPM_RETURNCMD**で、`fuFlags`パラメーター、戻り値は、ユーザーが選択した項目をメニュー項目の識別子。 ユーザーが、選択を行わず、メニューをキャンセルするか、エラーが発生した場合、戻り値は 0 です。  
  
 指定しない場合**TPM_RETURNCMD**で、`fuFlags`パラメーター、戻り値は、関数が成功した場合は 0 以外と 0、失敗した場合。 拡張エラー情報を取得する[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)します。  
  
### <a name="remarks"></a>コメント  
 浮動小数点のポップアップ メニューは、画面に任意の場所に表示できます。 ポップアップ メニューを作成するときにエラーの処理の詳細については、次を参照してください。 [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLTEST](../../visual-cpp-samples.md)   
 [MFC サンプル DYNAMENU](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)


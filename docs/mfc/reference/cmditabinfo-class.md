---
title: "CMDITabInfo クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo
- AFXMDICLIENTAREAWND/CMDITabInfo::Serialize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bAutoColor
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bDocumentMenu
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bEnableTabSwap
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bFlatFrame
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCloseButton
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabCustomTooltips
- AFXMDICLIENTAREAWND/CMDITabInfo::m_bTabIcons
- AFXMDICLIENTAREAWND/CMDITabInfo::m_nTabBorderSize
- AFXMDICLIENTAREAWND/CMDITabInfo::m_style
- AFXMDICLIENTAREAWND/CMDITabInfo::m_tabLocation
dev_langs:
- C++
helpviewer_keywords:
- CMDITabInfo class
- CMDITabInfo class, constructor
ms.assetid: 988ae1b7-4f7f-4239-b88f-7e28b3291c5e
caps.latest.revision: 37
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
ms.openlocfilehash: a45532c98d5da7d89d27e3d29d9b40075cf0376f
ms.lasthandoff: 02/24/2017

---
# <a name="cmditabinfo-class"></a>CMDITabInfo クラス
`CMDITabInfo`クラスを使用して、パラメーターを渡す[CMDIFrameWndEx::EnableMDITabbedGroups](../../mfc/reference/cmdiframewndex-class.md#enablemditabbedgroups)メソッドです。 MDI タブ付きグループの動作を制御するために、このクラスのメンバーを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMDITabInfo   
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMDITabInfo::CMDITabInfo`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDITabInfo::Serialize](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMDITabInfo::m_bActiveTabCloseButton です。](#m_bactivetabclosebutton_)|指定するかどうか、**閉じる**ボタンがアクティブなタブのラベルに表示されます。|  
|[CMDITabInfo::m_bAutoColor](#m_bautocolor)|MDI タブのカラーするかどうかを指定します。|  
|[CMDITabInfo::m_bDocumentMenu](#m_bdocumentmenu)|タブ グループが開いているドキュメントの一覧を表示またはスクロール ボタンを表示するポップアップ メニューを表示するかどうかを指定します。|  
|[CMDITabInfo::m_bEnableTabSwap](#m_benabletabswap)|ドラッグすることにより、ユーザーがタブの位置を入れ替えることができるかどうかを指定します。|  
|[CMDITabInfo::m_bFlatFrame](#m_bflatframe)|フラットなフレームがタブにあるかどうかを指定します。|  
|[CMDITabInfo::m_bTabCloseButton](#m_btabclosebutton)|各タブのラベルを表示するかどうかを指定する**閉じる** ボタンをクリックします。|  
|[CMDITabInfo::m_bTabCustomTooltips](#m_btabcustomtooltips)|カスタム ツール ヒントが有効になっているかどうかを指定します。|  
|[CMDITabInfo::m_bTabIcons](#m_btabicons)|MDI タブにアイコンを表示するかどうかを指定します。|  
|[CMDITabInfo::m_nTabBorderSize](#m_ntabbordersize)|各タブ ウィンドウの境界線のサイズを指定します。|  
|[CMDITabInfo::m_style](#m_style)|タブ ラベルのスタイルを指定します。|  
|[CMDITabInfo::m_tabLocation](#m_tablocation)|タブのラベルが、上またはページの下部にあるかどうかを指定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、フレームワークを作成する MDI タブ グループのパラメーターを指定します。  
  
## <a name="example"></a>例  
 次の例は、さまざまなメンバー変数の値を設定する方法を示します`CMDITabInfo`クラスです。  
  
 [!code-cpp[NVC_MFC_MDITab&#1;](../../mfc/reference/codesnippet/cpp/cmditabinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMDITabInfo](../../mfc/reference/cmditabinfo-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmdiclientareawnd.h  
  
##  <a name="m_bactivetabclosebutton_"></a>CMDITabInfo::m_bActiveTabCloseButton です。  
 指定するかどうか、**閉じる**ボタンがアクティブなタブのラベルに表示されます。  
  
```  
BOOL m_bActiveTabCloseButton;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、アクティブなタブのラベルが表示されます、**閉じる** ボタンをクリックします。 **閉じる**ボタンはタブ領域の右上隅から削除されます。 それ以外の場合、アクティブなタブのラベルは表示されない、**閉じる** ボタンをクリックします。 **閉じる**タブ領域の右上隅にあるボタンが表示されます。  
  
##  <a name="m_bautocolor"></a>CMDITabInfo::m_bAutoColor  
 MDI タブごとに、独自の色があるかどうかを指定します。  
  
```  
BOOL m_bAutoColor;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、各タブは、独自の色になります。 色のセットは、MFC ライブラリで管理されます。 それ以外の場合、タブは白色で表示されます。 既定値は `FALSE` です。  
  
##  <a name="m_bdocumentmenu"></a>CMDITabInfo::m_bDocumentMenu  
 各タブがタブ領域の右端に開いているドキュメントの一覧を表示するポップアップ メニューを表示するかどうかを指定します。  
  
```  
BOOL m_bDocumentMenu;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、各タブ ウィンドウには、タブ領域の右端に開いているドキュメントの一覧を表示するポップアップ メニューが表示されます。それ以外の場合、タブ ウィンドウは、タブ領域の右端にスクロール ボタンを表示します。 既定値は `FALSE` です。  
  
##  <a name="m_benabletabswap"></a>CMDITabInfo::m_bEnableTabSwap  
 ドラッグすることにより、ユーザーがタブの位置を入れ替えることができるかどうかを指定します。  
  
```  
BOOL m_bEnableTabSwap;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`タブをドラッグして、ユーザーがタブの位置を変更できます。 それ以外の場合、ユーザーは、タブ位置を変更することはできません。 既定値は `TRUE` です。  
  
##  <a name="m_bflatframe"></a>CMDITabInfo::m_bFlatFrame  
 各タブ ウィンドウにフラット フレームがあるかどうかを指定します。  
  
```  
BOOL m_bFlatFrame;  
```  
  
##  <a name="m_btabclosebutton"></a>CMDITabInfo::m_bTabCloseButton  
 各タブ ウィンドウを表示するかどうかを指定する**閉じる** ボタンをクリックします。  
  
```  
BOOL m_bTabCloseButton;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、各タブ ウィンドウを表示、**閉じる** タブの右端にボタンをクリックします。 それ以外の場合、**閉じる**ボタンは表示されません。 既定値は `TRUE` です。  
  
##  <a name="m_btabcustomtooltips"></a>CMDITabInfo::m_bTabCustomTooltips  
 タブがツールヒントを表示するかどうかを指定します。  
  
```  
BOOL m_bTabCustomTooltips;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、アプリケーションの送信、`AFX_WM_ON_GET_TAB_TOOLTIP`メインフレームへのメッセージ。 このメッセージを処理するを使用して、`ON_REGISTERED_MESSAGE`マクロです。  
  
##  <a name="m_btabicons"></a>CMDITabInfo::m_bTabIcons  
 MDI タブにアイコンを表示するかどうかを指定します。  
  
```  
BOOL m_bTabIcons;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`、各 MDI タブのアイコンが表示されます。 それ以外の場合、アイコンは、タブには表示されません。 既定値は `FALSE` です。  
  
##  <a name="m_ntabbordersize"></a>CMDITabInfo::m_nTabBorderSize  
 各タブ ウィンドウのピクセル単位の境界線のサイズを指定します。  
  
```  
int m_nTabBorderSize;  
```  
  
### <a name="remarks"></a>コメント  
 [CMFCVisualManager::GetMDITabsBordersSize](../../mfc/reference/cmfcvisualmanager-class.md#getmditabsborderssize)既定値を返します。  
  
##  <a name="m_style"></a>CMDITabInfo::m_style  
 タブ ラベルのスタイルを指定します。  
  
```  
CMFCTabCtrl::Style m_style  
```  
  
### <a name="remarks"></a>コメント  
 次のタブのラベルのスタイルのいずれかを指定します。  
  
 `STYLE_3D`  
 3D スタイル。  
  
 `STYLE_3D_ONENOTE`  
 Microsoft OneNote スタイルです。  
  
 `STYLE_3D_VS2005`  
 Microsoft Visual Studio 2005 のスタイル。  
  
 `STYLE_3D_SCROLLED`  
 四角形 タブのラベルが付いた&3;D スタイル。  
  
 `STYLE_FLAT_SHARED_HORZ_SCROLL`  
 共有の水平スクロール バーのフラット スタイルです。  
  
 `STYLE_3D_ROUNDED_SCROLL`  
 Round タブのラベルが付いた&3;D スタイル。  
  
##  <a name="m_tablocation"></a>CMDITabInfo::m_tabLocation  
 タブのラベルが、上またはページの下部にあるかどうかを指定します。  
  
```  
CMFCTabCtrl::Location m_tabLocation;  
```  
  
### <a name="remarks"></a>コメント  
 次の場所のフラグの&1; つのタブに適用されます。  
  
-   LOCATION_BOTTOM: タブのラベルは、ページの下部にあります。  
  
-   LOCATION_TOP: タブのラベルは、ページの上部には  
  
##  <a name="serialize"></a>CMDITabInfo::Serialize  
 読み取りまたはアーカイブからまたはアーカイブは、このオブジェクトを書き込みます。  
  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `ar`  
 A [CArchive クラス](../../mfc/reference/carchive-class.md)シリアル化するオブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)   
 [MDI タブ付きグループ](../../mfc/mdi-tabbed-groups.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)


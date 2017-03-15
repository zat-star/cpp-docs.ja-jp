---
title: "CBaseTabbedPane クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTabbedPane
dev_langs:
- C++
helpviewer_keywords:
- CBaseTabbedPane class
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b72804dd8b2ca2253caff4cebf5b0631ae6040c6
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane クラス
機能を拡張、 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)タブ付きウィンドウの作成をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseTabbedPane::AddTab](#addtab)|タブ付きペインに新しいタブを追加します。|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|空のタブ付きペインを破壊することができるかどうかを指定します。|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|タブ付きペインに、レジストリから読み込まれる タブの設定を適用します。|  
|[CBaseTabbedPane::CanFloat](#canfloat)|ペインをフローティングできるかどうかを決定します。 (上書き[CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat))。|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|タブ付きペインのキャプションがアクティブなタブとして同じテキストを表示するかどうかを指定します。|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(上書き[CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument))。|  
|[CBaseTabbedPane::DetachPane](#detachpane)|1 つまたは複数のドッキング可能ペインを MDI タブ付きドキュメントに変換します。|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|有効またはアクティブなタブにラベルのテキストとキャプションのテキストを同期するタブ付きペインの機能を無効にします。|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|内部のタブ オーダーを既定の状態に復元します。|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|タブが タブの&0; から始まるインデックスによって識別されると、タブにあるペインを返します。|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|ペインの ID によって識別されるペインを返します|  
|[CBaseTabbedPane::FloatTab](#floattab)|現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|ウィンドウでタブの既定の順序を返します。|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|最初に表示されているタブへのポインターを取得します。|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|最小のウィンドウのサイズを取得します。 (上書き[CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize))。|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|ペインのアイコンのハンドルを返します。 (上書き[CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon))。|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|タブ付きペインに含まれているウィンドウの一覧を返します。|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|上と下のタブ領域に外接する四角形を返します。|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|タブ ウィンドウでタブの数を返します。|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|基になる (ラップされた) タブ ウィンドウを取得します。|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|表示されるタブの数を返します。|  
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|タブ付きペインは、自動非表示モードに切り替えることができるかどうかを決定します。|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|だけは、1 つのタブが表示される場合に、タブ付きペインを非表示にするかどうかを決定します。|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|シリアル化中に内部的に使用します。|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|ウィンドウのレイアウト情報を再計算します。 (上書き[CPane::RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout))。|  
|[CBaseTabbedPane::RemovePane](#removepane)|タブ付きペインから、ウィンドウを削除します。|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|シリアル化中に内部的に使用します。|  
|`CBaseTabbedPane::Serialize`|(上書き[CDockablePane::Serialize](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6))。|  
|`CBaseTabbedPane::SerializeTabWindow`|シリアル化中に内部的に使用します。|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|タブ付きコントロール バーが自動的に破棄されるかどうかを決定します。|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|ドッキング ペインの表示を切り替えると自動的に隠すモード。 (上書き[CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode))。|  
|[CBaseTabbedPane::ShowTab](#showtab)|タブの表示と非表示を切り替えます。|  
  
## <a name="remarks"></a>コメント  
 このクラスは抽象クラスであり、インスタンス化することはできません。 タブ付きペインのすべての種類に共通しているサービスを実装します。  
  
 現時点では、ライブラリには&2; つのタブ付きペイン:[派生クラス](../../mfc/reference/ctabbedpane-class.md)と[があります](../../mfc/reference/cmfcoutlookbar-class.md)します。  
  
 A`CBaseTabbedPane`へのポインターをラップするオブジェクト、 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)オブジェクトです。 [CMFCBaseTabCtrl クラス](../../mfc/reference/cmfcbasetabctrl-class.md)タブ付きウィンドウの子ウィンドウになります。  
  
 タブ付きペインを作成する方法の詳細については、次を参照してください。 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)、[派生クラス](../../mfc/reference/ctabbedpane-class.md)、および[があります](../../mfc/reference/cmfcoutlookbar-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 `CBaseTabbedPane`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxBaseTabbedPane.h  
  
##  <a name="a-nameaddtaba--cbasetabbedpaneaddtab"></a><a name="addtab"></a>CBaseTabbedPane::AddTab  
 タブ付きペインに新しいタブを追加します。  
  
```  
virtual BOOL AddTab(
    CWnd* pNewBar,  
    BOOL bVisible = TRUE,  
    BOOL bSetActive = TRUE,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pNewBar`  
 追加するペインへのポインター。 このメソッドを呼び出した後でこのポインターが無効になります。 詳細については、「解説」を参照してください。  
  
 [入力] `bVisible`  
 `TRUE`タブが表示されるようにするにはそれ以外の場合、`FALSE`です。  
  
 [入力] `bSetActive`  
 `TRUE`アクティブなタブ、タブを作成するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `bDetachable`  
 `TRUE`タブをデタッチできるようにするにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウのタブとして正常に追加され、はなかった場合は、プロセスで破棄されます。 `FALSE`追加されるウィンドウが型のオブジェクトの場合`CBaseTabbedPane`します。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 タブ付きペイン上の新しいタブとして、ウィンドウを追加するには、このメソッドを呼び出します。 場合`pNewBar`型のオブジェクトを指し示す`CBaseTabbedPane`、そのすべてのタブはタブ付きペインにコピーし、`pNewBar`が破棄されます。 したがって、`pNewBar`無効なポインターとなり、使用しない必要があります。  
  
##  <a name="a-nameallowdestroyemptytabbedpanea--cbasetabbedpaneallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 空のタブ付きペインを破壊することができるかどうかを指定します。  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合は空のタブ付きペインを破壊することができます。それ以外の場合、`FALSE`です。 既定の実装を常に`TRUE`します。  
  
### <a name="remarks"></a>コメント  
 空のタブ付きペインが破棄されるを許可しない場合、framework は、ウィンドウを代わりに表示されません。  
  
##  <a name="a-nameapplyrestoredtabinfoa--cbasetabbedpaneapplyrestoredtabinfo"></a><a name="applyrestoredtabinfo"></a>CBaseTabbedPane::ApplyRestoredTabInfo  
 タブの設定をレジストリから読み込むし、タブ付きペインに適用します。  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bUseTabIndexes`  
 このパラメーターは、フレームワークによって内部的に使用します。  
  
### <a name="remarks"></a>コメント  
 ドッキング状態情報をレジストリからのプロジェクトを再読み込み、このメソッドは、フレームワークによって呼び出されます。 メソッドは、タブ オーダーおよびタブ付きペインのタブ名に関する情報を取得します。  
  
##  <a name="a-namecanfloata--cbasetabbedpanecanfloat"></a><a name="canfloat"></a>CBaseTabbedPane::CanFloat  
 タブ付きペインをフローティングできるかどうかを指定します。  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインをフローティングできる場合それ以外の場合、`FALSE`です。  
  
##  <a name="a-namecansetcaptiontexttotabnamea--cbasetabbedpanecansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane::CanSetCaptionTextToTabName  
 タブ付きペインのキャプションがアクティブなタブとして同じテキストを表示するかどうかを指定します。  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`アクティブなタブのテキストにタブ付きペインのキャプションのテキストが設定されている場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 メソッドはタブ付きペインのキャプションに表示されるテキストが、アクティブなタブのラベルを使用するかどうかを判断するために使用します。 有効にするか、呼び出すことによってこの機能を無効にする[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)します。  
  
##  <a name="a-nameconverttotabbeddocumenta--cbasetabbedpaneconverttotabbeddocument"></a><a name="converttotabbeddocument"></a>CBaseTabbedPane::ConvertToTabbedDocument  
 1 つまたは複数のドッキング可能ペインを MDI タブ付きドキュメントに変換します。  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bActiveTabOnly`  
 タブ付きペインを変換するときに指定`TRUE`にアクティブなタブのみを変換します。 指定`FALSE`ペイン内のすべてのタブに変換します。  
  
##  <a name="a-namedetachpanea--cbasetabbedpanedetachpane"></a><a name="detachpane"></a>CBaseTabbedPane::DetachPane  
 タブ付きペインからウィンドウをデタッチします。  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 デタッチするウィンドウへのポインター。  
  
 [入力] `bHide`  
 フレームワークがデタッチされた後、ウィンドウが非表示にするかどうかを示すブール値パラメーターです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`フレームワークが、ウィンドウを正常にデタッチ場合`FALSE`場合`pBar`は`NULL`か、タブ付きペインに含まれていないウィンドウを参照します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、可能であればデタッチ ペインをフローティング状態です。 詳細については、次を参照してください。 [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat)します。  
  
##  <a name="a-nameenablesetcaptiontexttotabnamea--cbasetabbedpaneenablesetcaptiontexttotabname"></a><a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane::EnableSetCaptionTextToTabName  
 有効またはアクティブなタブにラベルのテキストとキャプションのテキストを同期するタブ付きペインの機能を無効にします。  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 `TRUE`タブ付きペインのキャプションをアクティブなタブのキャプションと同期するにはそれ以外の場合、`FALSE`です。  
  
##  <a name="a-namefilldefaulttabsorderarraya--cbasetabbedpanefilldefaulttabsorderarray"></a><a name="filldefaulttabsorderarray"></a>CBaseTabbedPane::FillDefaultTabsOrderArray  
 内部のタブ オーダーを既定の状態に復元します。  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークの初期状態にある Outlook バーを復元することによってこのメソッドが呼び出されます。  
  
##  <a name="a-namefindpanebyida--cbasetabbedpanefindpanebyid"></a><a name="findpanebyid"></a>CBaseTabbedPane::FindPaneByID  
 ペインの ID によって識別されるペインを返します  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uBarID`  
 検索する、ウィンドウの ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 見つかった場合、ウィンドウへのポインターそれ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ペイン内のすべてのタブを比較しで指定された ID を持つものを返します、`uBarID`パラメーター。  
  
##  <a name="a-namefindbarbytabnumbera--cbasetabbedpanefindbarbytabnumber"></a><a name="findbarbytabnumber"></a>CBaseTabbedPane::FindBarByTabNumber  
 タブ内にあるペインを返します。  
  
```  
virtual CWnd* FindBarByTabNumber(
    int nTabNum,  
    BOOL bGetWrappedBar = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTabNum`  
 取得するタブの&0; から始まるインデックスを指定します。  
  
 [入力] `bGetWrappedBar`  
 `TRUE`ペイン自体ではなく、ウィンドウの (ラップされた) 基になるウィンドウに戻すそれ以外の場合`FALSE`します。 派生したウィンドウのみに限定される[CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが見つかった場合、検索対象のウィンドウに、有効なポインターが返されます。それ以外の場合、`NULL`です。  
  
### <a name="remarks"></a>コメント  
 指定したタブにあるウィンドウを取得するには、このメソッドを呼び出して、`nTabNum`パラメーター。  
  
##  <a name="a-namefloattaba--cbasetabbedpanefloattab"></a><a name="floattab"></a>CBaseTabbedPane::FloatTab  
 現在ペインが切り離し可能なタブに存在する場合のみ、そのペインを切り離して表示します。  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pBar`  
 浮動小数点数には、ウィンドウへのポインター。  
  
 [入力] `nTabID`  
 浮動小数点 タブの&0; から始まるインデックスを指定します。  
  
 [入力] `dockMethod`  
 ペインをフローティングの作成に使用する方法を指定します。 詳細については、「解説」を参照してください。  
  
 [入力] `bHide`  
 `TRUE`フローティングする前に、ウィンドウを非表示にするにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ペインをフローティング状態の場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 切り離し可能なタブにある現在ペインをフローティングするには、このメソッドを呼び出します。  
  
 プログラムを使用して、ウィンドウをデタッチする場合は、指定`DM_SHOW`の`dockMethod`パラメーター。 ここで、フロート以前の同じ位置にウィンドウをフローティングでを指定する場合`DM_DBL_CLICK`として、`dockMethod`パラメーター。  
  
##  <a name="a-namegetdefaulttabsordera--cbasetabbedpanegetdefaulttabsorder"></a><a name="getdefaulttabsorder"></a>CBaseTabbedPane::GetDefaultTabsOrder  
 ウィンドウでタブの既定の順序を返します。  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>戻り値  
 A`CArray`のウィンドウでタブの既定の順序を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、初期状態にある Outlook バーがリセットされると、このメソッドを呼び出します。  
  
##  <a name="a-namegetfirstvisibletaba--cbasetabbedpanegetfirstvisibletab"></a><a name="getfirstvisibletab"></a>CBaseTabbedPane::GetFirstVisibleTab  
 最初に表示されているタブへのポインターを取得します。  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTabNum`  
 整数への参照。 このメソッドの最初のタブに表示されている&0; から始まるインデックスを書き込みますこのパラメーターは、-1 表示されていない場合 タブがあります。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、最初に表示されているタブへのポインターそれ以外の場合、`NULL`です。  
  
##  <a name="a-namegetminsizea--cbasetabbedpanegetminsize"></a><a name="getminsize"></a>CBaseTabbedPane::GetMinSize  
 最小のウィンドウのサイズを取得します。  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `size`  
 A`CSize`は最小サイズで塗りつぶされたオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの最小サイズの一貫した処理がアクティブである場合 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize))、`size`はアクティブなタブのサイズが許容される最小で塗りつぶされます。 それ以外の場合、`size`の戻り値がだらけに[CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)します。  
  
##  <a name="a-namegetpaneicona--cbasetabbedpanegetpaneicon"></a><a name="getpaneicon"></a>CBaseTabbedPane::GetPaneIcon  
 最小のウィンドウのサイズを取得します。  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `size`  
 A`CSize`は最小サイズで塗りつぶされたオブジェクト。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの最小サイズの一貫した処理がアクティブである場合 ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize))、`size`はアクティブなタブのサイズが許容される最小で塗りつぶされます。 それ以外の場合、`size`の戻り値がだらけに[CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize)します。  
  
##  <a name="a-namegetpanelista--cbasetabbedpanegetpanelist"></a><a name="getpanelist"></a>CBaseTabbedPane::GetPaneList  
 タブ付きペインに含まれているウィンドウの一覧を返します。  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `lst`  
 A`CObList`タブ付きペインに含まれているペインとを入力します。  
  
 [入力] `pRTCFilter`  
 ない場合は`NULL`リストが返されますが、指定したランタイム クラスのウィンドウのみが含まれています。  
  
##  <a name="a-namegettabareaa--cbasetabbedpanegettabarea"></a><a name="gettabarea"></a>CBaseTabbedPane::GetTabArea  
 上と下のタブ領域に外接する四角形を返します。  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `rectTabAreaTop`  
 上部のタブ領域の画面座標を受け取ります。  
  
 [出力] `rectTabAreaBottom`  
 下のタブ領域の画面座標を受け取ります。  
  
### <a name="remarks"></a>コメント  
 外接する四角形の領域に関しては、上限と下限 タブの画面座標を判断するには、このメソッドを呼び出します。  
  
##  <a name="a-namegettabsnuma--cbasetabbedpanegettabsnum"></a><a name="gettabsnum"></a>CBaseTabbedPane::GetTabsNum  
 タブ ウィンドウでタブの数を返します。  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>戻り値  
 タブ付きペインにあるタブの数。  
  
##  <a name="a-namegetunderlyingwindowa--cbasetabbedpanegetunderlyingwindow"></a><a name="getunderlyingwindow"></a>CBaseTabbedPane::GetUnderlyingWindow  
 基になる (ラップされた) タブ ウィンドウを取得します。  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>戻り値  
 基になるタブ ウィンドウへのポインター。  
  
##  <a name="a-namegetvisibletabsnuma--cbasetabbedpanegetvisibletabsnum"></a><a name="getvisibletabsnum"></a>CBaseTabbedPane::GetVisibleTabsNum  
 表示されているタブの数を返します。  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以上の値をゼロになる表示されているタブの数。  
  
### <a name="remarks"></a>コメント  
 タブ付きペインに表示されているタブの数を確認するには、このメソッドを呼び出します。  
  
##  <a name="a-namehasautohidemodea--cbasetabbedpanehasautohidemode"></a><a name="hasautohidemode"></a>CBaseTabbedPane::HasAutoHideMode  
 タブ付きペインを AutoHide モードに切り替えられるかどうかを判断します。  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`ウィンドウを隠すモードに切り替えることができる場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 自動非表示モードが無効になっている場合、タブ付きペインのキャプションの暗証番号 (pin) ボタンは表示されません。  
  
##  <a name="a-nameishidesingletaba--cbasetabbedpaneishidesingletab"></a><a name="ishidesingletab"></a>CBaseTabbedPane::IsHideSingleTab  
 だけは、1 つのタブが表示される場合に、タブ付きペインを非表示にするかどうかを決定します。  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`1 つだけに表示されるタブ; がある場合に、タブ ウィンドウが表示されない場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 1 つだけのタブが開かれているために、ウィンドウが表示されていない場合は、タブ付きペインが正常に動作しているかどうかを確認するには、このメソッドを呼び出すことができます。  
  
##  <a name="a-nameremovepanea--cbasetabbedpaneremovepane"></a><a name="removepane"></a>CBaseTabbedPane::RemovePane  
 タブ付きペインから、ウィンドウを削除します。  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pBar`  
 タブ付きペインから削除するのには、ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブ付きペインから、ウィンドウが削除されましたと、タブ付きウィンドウがまだ有効である場合。 `FALSE`最後のウィンドウがタブ付きウィンドウおよびタブ付きペインから削除されている場合は、破棄されようとしてです。 戻り値が場合`FALSE`、かどうかをタブ付きペインを使用しないでください。  
  
### <a name="remarks"></a>コメント  
 指定されたウィンドウを削除するには、このメソッドを呼び出して、`pBar`タブ付きペインからのパラメーターです。  
  
##  <a name="a-namesetautodestroya--cbasetabbedpanesetautodestroy"></a><a name="setautodestroy"></a>CBaseTabbedPane::SetAutoDestroy  
 タブ付きコントロール バーが自動的に破棄されるかどうかを決定します。  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bAutoDestroy`  
 `TRUE`タブ付きペインが動的に作成され、; 有効期間を制御していない場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 設定の自動破棄モードを`TRUE`タブ付きペインを動的に作成し、その有効期間を制御していない場合。 場合は自動破棄モードは`TRUE`、タブ付きペインは、フレームワークによって自動的に破棄します。  
  
##  <a name="a-nameshowtaba--cbasetabbedpaneshowtab"></a><a name="showtab"></a>CBaseTabbedPane::ShowTab  
 タブの表示と非表示を切り替えます。  
  
```  
virtual BOOL ShowTab(
    CWnd* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pBar`  
 表示/非表示に、ウィンドウへのポインター。  
  
 [入力] `bShow`  
 `TRUE`ウィンドウを表示するには`FALSE`ウィンドウを非表示にします。  
  
 [入力] `bDelay`  
 `TRUE`タブ レイアウトの調整を遅延するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `bActivate`  
 `TRUE`アクティブなタブ、タブを作成するにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`タブの表示または非表示に正常にされた場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 ペインが表示または非表示の値に応じて、このメソッドを呼び出すときに、`bShow`パラメーター。 タブを非表示にして、基になるタブ ウィンドウの最後に表示されるタブは、タブ付きペインが表示されます。 存在しなかった以前タブ表示されているときにタブを表示する場合は、タブ付きペインが表示されます。  
  
##  <a name="a-namerecalclayouta--cbasetabbedpanerecalclayout"></a><a name="recalclayout"></a>CBaseTabbedPane::RecalcLayout  
 ウィンドウのレイアウト情報を再計算します。  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウがフローティング状態の場合、このメソッドは、ミニ フレームの現在のサイズには、ウィンドウのサイズを変更するために、フレームワークを通知します。  
  
 ウィンドウがドッキングされている場合は、このメソッドは何も行われません。  
  
##  <a name="a-namesetautohidemodea--cbasetabbedpanesetautohidemode"></a><a name="setautohidemode"></a>CBaseTabbedPane::SetAutoHideMode  
 タブ付きペインの取り外し可能なウィンドウの場合、自動非表示モードを設定します。  
  
```  
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMode`  
 `TRUE`自動非表示モードを有効にするには`FALSE`標準ドッキング モードを有効にします。  
  
 [入力] `dwAlignment`  
 作成する、自動非表示ウィンドウの配置を指定します。 使用可能な値の一覧は、次を参照してください。 [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment)します。  
  
 [in][out]`pCurrAutoHideBar`  
 現在を自動的に隠すツールバーへのポインター。 できる`NULL`です。  
  
 [入力] `bUseTimer`  
 自動非表示モードをユーザーが、ウィンドウを切り替えるときに自動的に隠す効果を使用するか、すぐに、ウィンドウを非表示にするかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 自動非表示モードに切り替えるときに作成されるを自動的に隠すツールバーへのポインターまたは`NULL`場合ツールバーは作成されません。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、ユーザーが自動非表示モードまたは標準ドッキング モードには、タブ付きペインを切り替えるには、暗証番号 (pin) ボタンを選択すると、このメソッドを呼び出します。  
  
 タブ付きペインに取り外し可能な各ウィンドウの自動非表示モードが設定されています。 非切り離し可能なペインは無視されます。 詳細については、次を参照してください。 [CMFCBaseTabCtrl::EnableTabDetach](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach)します。  
  
 プログラムを使用して、自動非表示モードにタブ付きペインを切り替えるには、このメソッドを呼び出します。 メイン フレーム ウィンドウに、ウィンドウをドッキングする必要があります ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider)への有効なポインターを返す必要があります、 [CPaneDivider](../../mfc/reference/cpanedivider-class.md))。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)


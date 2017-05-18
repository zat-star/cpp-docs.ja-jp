---
title: "CCheckListBox クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
dev_langs:
- C++
helpviewer_keywords:
- CCheckListBox class
- checklist boxes
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2cce91e3b6cb6cdf6ec2f4564fcf5090a54c917f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cchecklistbox-class"></a>CCheckListBox クラス
Windows のチェックリスト ボックスの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCheckListBox : public CListBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[サンプル](#cchecklistbox)|`CCheckListBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCheckListBox::Create](#create)|Windows チェックリスト ボックスを作成し、それをアタッチ、`CCheckListBox`オブジェクトです。|  
|[:Drawitem](#drawitem)|オーナー描画リスト ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。|  
|[CCheckListBox::Enable](#enable)|有効またはチェックリスト ボックス アイテムを無効にします。|  
|[CCheckListBox::GetCheck](#getcheck)|項目のチェック ボックスの状態を取得します。|  
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|コントロールのチェック ボックスのスタイルを取得します。|  
|[CCheckListBox::IsEnabled](#isenabled)|アイテムが有効になっているかどうかを決定します。|  
|[CCheckListBox::MeasureItem](#measureitem)|オーナー描画スタイルを持つリスト ボックスが作成されるときに、フレームワークによって呼び出されます。|  
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|項目のチェック ボックスの位置を取得するためにフレームワークによって呼び出されます。|  
|[CCheckListBox::SetCheck](#setcheck)|項目のチェック ボックスの状態を設定します。|  
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|コントロールのチェック ボックスのスタイルを設定します。|  
  
## <a name="remarks"></a>コメント  
 「チェックリスト ボックス」には、ファイル名などのアイテムの一覧が表示されます。 一覧には、各項目には、ユーザーがチェックまたはオフを隣のチェック ボックスがあります。  
  
 `CCheckListBox`オーナー描画コントロールに対してのみ、一覧に表示のテキスト文字列を超えるためです。 簡単に言うと、チェックリスト ボックスには、テキスト文字列とチェック ボックスが含まれていますが、テキストはまったく必要はありません。 たとえば、小さいビットマップでは各項目の横のチェック ボックスの一覧がある可能性があります。  
  
 独自のチェックリスト ボックスを作成するから独自のクラスを派生する必要があります`CCheckListBox`します。 派生クラスを記述するには、派生クラスのコンス トラクターを呼び出す、**作成**します。  
  
 リスト ボックスからその親に送信される Windows の通知メッセージを処理する場合 (通常から派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。  
  
 各メッセージ マップ エントリは、次の形式をとります。  
  
 **ON_**Notification **(**`id`, `memberFxn`**)**  
  
 ここで`id`通知を送信するコントロールの子ウィンドウの ID を指定し、`memberFxn`通知を処理する記述した親メンバー関数の名前を指定します。  
  
 親の関数のプロトタイプは次のとおりです。  
  
 **afx_msg** `void` `memberFxn` **( );**  
  
 特に関連する&1; つだけのメッセージ マップ エントリが**CCheckListBox** (メッセージ マップ エントリも参照してください。 が、 [CListBox](../../mfc/reference/clistbox-class.md))。  
  
- **ON_CLBN_CHKCHANGE**ユーザーが項目のチェック ボックスをオンの状態を変更します。  
  
 チェックリスト ボックスが既定のチェックリスト ボックス (文字列の左に既定のサイズのチェック ボックスの一覧) の場合は、既定値を使用することができます[:drawitem](#drawitem)チェックリスト ボックスを描画します。 それ以外の場合、オーバーライドする必要があります、 [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem)関数および[:drawitem](#drawitem)と[CCheckListBox::MeasureItem](#measureitem)関数です。  
  
 チェックリスト ボックスは、ダイアログ テンプレートから、またはコードで直接作成できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CCheckListBox`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cchecklistbox"></a>サンプル  
 `CCheckListBox` オブジェクトを構築します。  
  
```  
CCheckListBox();
```  
  
### <a name="remarks"></a>コメント  
 構築する、 `CCheckListBox`&2; つのステップ内のオブジェクト。 最初から派生するクラスを定義する`CCheckListBox`、物書き**作成**に接続を Windows チェックリスト ボックスを初期化し、`CCheckListBox`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog&#60;](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]  
  
##  <a name="create"></a>CCheckListBox::Create  
 Windows チェックリスト ボックスを作成し、それをアタッチ、`CCheckListBox`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 チェックリスト ボックスのスタイルを指定します。 スタイルである必要があります**LBS_HASSTRINGS** 、 **LBS_OWNERDRAWFIXED** (リスト内のすべての項目は同じ高さ) または**LBS_OWNERDRAWVARIABLE** (リスト内の項目は、高さが異なるは)。 このスタイルを他と組み合わせて[リスト ボックス スタイル](../../mfc/reference/list-box-styles.md)を除く**LBS_USETABSTOPS**します。  
  
 `rect`  
 チェックリスト ボックスのサイズと位置を指定します。 いずれか、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 `pParentWnd`  
 チェックリスト ボックスの親ウィンドウを指定します (通常、`CDialog`オブジェクト)。 ことはできません**NULL**します。  
  
 `nID`  
 チェックリスト ボックスのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CCheckListBox`&2; つのステップ内のオブジェクト。 派生するクラスを最初に、定義**CcheckListBox**し、呼び出す**作成**に接続を Windows チェックリスト ボックスを初期化し、`CCheckListBox`です。 参照してください[サンプル](#cchecklistbox)サンプルです。  
  
 **作成**実行されると、Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)と[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)チェックリスト ボックス コントロールへのメッセージ。  
  
 既定では、これらのメッセージが処理される、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数、`CWnd`基本クラスです。 既定のメッセージ処理を拡張するには、メッセージ マップを追加と派生クラスのメンバー関数が上記のメッセージ ハンドラーをオーバーライドします。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/window-styles.md)チェックリスト ボックス コントロールにします。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
- **WS_VSCROLL**垂直スクロール バーを追加するには  
  
- **WS_HSCROLL**水平スクロール バーを追加するには  
  
- **WS_GROUP**コントロールをグループ化  
  
- **WS_TABSTOP**コントロールのタブ オーダーを許可するには  
  
##  <a name="drawitem"></a>:Drawitem  
 オーナー描画のチェックリスト ボックスの変更のビジュアルな部分のときに、フレームワークによって呼び出されます。  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpDrawItemStruct`  
 Long ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を格納する構造体。  
  
### <a name="remarks"></a>コメント  
 **ItemAction**と**itemState**のメンバー、`DRAWITEMSTRUCT`構造体は、実行するのには、描画の動作を定義します。  
  
 既定では、この関数は、左に既定のサイズのチェック ボックスに文字列ごとのリストで構成される、既定のチェック ボックス リストを描画します。 チェック ボックスの一覧のサイズは、いずれかで指定された[作成](#create)します。  
  
 チェックリスト ボックスの文字列ではないリスト、可変サイズの項目、または左側にチェック ボックスなど、既定ではないオーナー描画チェックリスト ボックスの描画を実装するには、この関数をオーバーライドします。 アプリケーションで指定されたディスプレイ コンテキスト用に選択したすべてのグラフィック デバイス インターフェイス (GDI) オブジェクトを復元する必要があります`lpDrawItemStruct`このメンバー関数が終了する前にします。  
  
 チェックリスト ボックス スタイルのチェックリスト ボックスの項目はすべて同じ高さではない場合、(で指定されている**作成**) する必要があります**一定**をオーバーライドする必要があります、 [MeasureItem](#measureitem)関数です。  
  
##  <a name="enable"></a>CCheckListBox::Enable  
 この関数では、有効またはチェックリスト ボックス アイテムを無効にします。  
  
```  
void Enable(
    int nIndex,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 有効にするチェックリスト ボックス アイテムのインデックス。  
  
 `bEnabled`  
 項目が有効になっているかどうかを指定します。  
  
##  <a name="getcheck"></a>CCheckListBox::GetCheck  
 指定されたチェック ボックスの状態を取得します。  
  
```  
int GetCheck(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスに含まれているチェック ボックスの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定されたチェック ボックスの状態。 次の表は、指定できる値を示します。  
  
|値|説明|  
|-----------|-----------------|  
|`BST_CHECKED`|チェック ボックスをオンにするとします。|  
|`BST_UNCHECKED`|チェック ボックスをオフにするとします。|  
|`BST_INDETERMINATE`|チェック ボックスの状態は予測できません。|  
  
##  <a name="getcheckstyle"></a>CCheckListBox::GetCheckStyle  
 チェックリスト ボックスのスタイルを取得するには、この関数を呼び出します。  
  
```  
UINT GetCheckStyle();
```  
  
### <a name="return-value"></a>戻り値  
 コントロールのチェック ボックスのスタイル。  
  
### <a name="remarks"></a>コメント  
 有効なスタイルについては、次を参照してください。[有効なスタイル](#setcheckstyle)します。  
  
##  <a name="isenabled"></a>CCheckListBox::IsEnabled  
 アイテムが有効になっているかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL IsEnabled(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 項目のインデックス。  
  
### <a name="return-value"></a>戻り値  
 項目が有効な場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="measureitem"></a>CCheckListBox::MeasureItem  
 既定以外のスタイルとチェックリスト ボックスが作成されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpMeasureItemStruct`  
 Long ポインター、 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 既定では、このメンバー関数は何もしません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`構造チェックリスト ボックス アイテムのディメンションの Windows に通知します。 チェックリスト ボックスが作成された場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/list-box-styles.md)リスト ボックス内の各項目のスタイル、フレームワークと記述します。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。  
  
##  <a name="ongetcheckposition"></a>CCheckListBox::OnGetCheckPosition  
 フレームワークでは、アイテムのチェック ボックスのサイズと位置を取得するには、この関数を呼び出します。  
  
```  
virtual CRect OnGetCheckPosition(
    CRect rectItem,  
    CRect rectCheckBox);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectItem*  
 位置とリスト アイテムのサイズ。  
  
 `rectCheckBox`  
 既定の位置と項目のチェック ボックスのサイズ。  
  
### <a name="return-value"></a>戻り値  
 位置と項目のチェック ボックスのサイズ。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、既定の位置とチェック ボックスのサイズにのみを返します ( `rectCheckBox`)。 既定では、チェック ボックスをアイテムの左上隅に配置する、標準のチェック ボックスのサイズ。 場合は、右側のチェック ボックスや、拡大または縮小のチェック ボックスがある可能性があります。 このような場合は、オーバーライド`OnGetCheckPosition` チェック ボックスの位置とサイズ内に項目を変更します。  
  
##  <a name="setcheck"></a>CCheckListBox::SetCheck  
 指定されたチェック ボックスの状態を設定します。  
  
```  
void SetCheck(
    int nIndex,  
    int nCheck);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 リスト ボックスに含まれているチェック ボックスの&0; から始まるインデックス。  
  
 `nCheck`  
 指定された チェック ボックス ボタンの状態。 指定できる値については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 次の表に、可能な値、`nCheck`パラメーター。  
  
|値|説明|  
|-----------|-----------------|  
|**BST_CHECKED**|指定されたチェック ボックスを選択します。|  
|**設定されています。**|指定されたチェック ボックスをオフにします。|  
|**BST_INDETERMINATE**|不確定なに指定のチェック ボックスの状態を設定します。<br /><br /> この状態は場合のみ表示 チェック ボックスのスタイルは`BS_AUTO3STATE`または`BS_3STATE`です。 詳細については、次を参照してください。[ボタン スタイル](../../mfc/reference/button-styles.md)します。|  
  
##  <a name="setcheckstyle"></a>CCheckListBox::SetCheckStyle  
 チェックリスト ボックス内のチェック ボックスのスタイルを設定するには、この関数を呼び出します。  
  
```  
void SetCheckStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `nStyle`  
 チェックリスト ボックスのチェック ボックスのスタイルを決定します。  
  
### <a name="remarks"></a>コメント  
 有効なスタイルは次のとおりです。  
  
- **BS_CHECKBOX**  
  
- **BS_AUTOCHECKBOX**  
  
- **BS_AUTO3STATE**  
  
- **BS_3STATE**  
  
 詳細については、これらのスタイルは、次を参照してください。[ボタン スタイル](../../mfc/reference/button-styles.md)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル TSTCON](../../visual-cpp-samples.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)


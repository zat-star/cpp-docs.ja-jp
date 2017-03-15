---
title: "CReBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CReBar
dev_langs:
- C++
helpviewer_keywords:
- rebar controls, control bar
- CReBar class
- Internet Explorer 4.0 common controls
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
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
ms.openlocfilehash: 38ac4611503bec70ea9f809a4d4f9d4b5133e30e
ms.lasthandoff: 02/24/2017

---
# <a name="crebar-class"></a>CReBar クラス
Rebar コントロールのレイアウト、永続性、および状態に関する情報を提供するコントロール バーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CReBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CReBar::AddBar](#addbar)|Rebar バンドに追加します。|  
|[CReBar::Create](#create)|Rebar コントロールを作成し、それをアタッチ、`CReBar`オブジェクトです。|  
|[CReBar::GetReBarCtrl](#getrebarctrl)|基になる一般的なコントロールに直接アクセスをできます。|  
  
## <a name="remarks"></a>コメント  
 Rebar オブジェクトには、さまざまな子ウィンドウを通常他のコントロールのエディット ボックス、ツールバー、リスト ボックスなどを含めることができます。 Rebar オブジェクトは、指定したビットマップの経過と共に、その子ウィンドウを表示できます。 アプリケーションに自動的にサイズを変更できる、rebar または、手動でユーザーが rebar をクリックするかのグリッパー バーをドラッグします。  
  
 ![RebarMenu の](../../mfc/reference/media/vc4sc61.gif "vc4sc61")  
  
## <a name="rebar-control"></a>Rebar コントロール  
 Rebar オブジェクトは、ツール バー オブジェクトと同様に動作します。 Rebar では、クリックとドラッグ メカニズムを使用して、そのバンドのサイズを変更します。 Rebar コントロールでは、グリッパー バー、ビットマップ、テキスト ラベル、および子ウィンドウの任意の組み合わせを&1; つまたは複数のバンドを含めることができます。 ただし、バンドは、1 つ以上の子ウィンドウを含めることはできません。  
  
 **CReBar**を使用して、 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md)クラスの実装を提供します。 Rebar コントロールを通じてアクセスできます[GetReBarCtrl](#getrebarctrl)コントロールのカスタマイズ オプションを活用するためにします。 Rebar コントロールの詳細については、次を参照してください。`CReBarCtrl`します。 Rebar コントロールの使用に関する詳細については、次を参照してください。[を使用して CReBarCtrl](../../mfc/using-crebarctrl.md)します。  
  
> [!CAUTION]
>  Rebar と rebar コントロール オブジェクトは、MFC コントロール バーのドッキングをサポートしています。 場合**CRebar::EnableDocking**と呼ばれる、アプリケーションはアサートします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CReBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="a-nameaddbara--crebaraddbar"></a><a name="addbar"></a>CReBar::AddBar  
 このメンバー関数を呼び出して、rebar バンドを追加します。  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

 
BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBar`  
 ポインター、 `CWnd` rebar に挿入する子ウィンドウであるオブジェクト。 参照先オブジェクトには、 **WS_CHILD**します。  
  
 `lpszText`  
 Rebar に表示するテキストを含む文字列へのポインター。 **NULL**既定です。 含まれるテキスト`lpszText`子ウィンドウの一部ではない自体 rebar 上にあります。  
  
 `pbmp`  
 ポインター、 `CBitmap` rebar の背景に表示するオブジェクト。 **NULL**既定です。  
  
 `dwStyle`  
 A `DWORD` rebar に適用するスタイルを格納しています。 参照してください、**は**関数の Win32 構造の説明[REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393)バンド スタイルの完全な一覧です。  
  
 *clrFore*  
 A **COLORREF** rebar の前景色を表す値。  
  
 *clrBack*  
 A **COLORREF** rebar の背景色を表す値。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#1;](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]  
  
##  <a name="a-namecreatea--crebarcreate"></a><a name="create"></a>CReBar::Create  
 このメンバー関数を呼び出して rebar を作成します。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 ポインター、`CWnd`ウィンドウのステータス バーの親オブジェクトです。 通常、フレーム ウィンドウです。  
  
 `dwCtrlStyle`  
 Rebar コントロールのスタイル。 既定では、 **RBS_BANDBORDERS**、絞り込む rebar コントロール内の隣接するバンドの区切り線を表示します。 参照してください[Rebar コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb774377)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]スタイルの一覧です。  
  
 `dwStyle`  
 Rebar ウィンドウ スタイル。  
  
 `nID`  
 Rebar の子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CReBar::AddBar](#addbar)します。  
  
##  <a name="a-namegetrebarctrla--crebargetrebarctrl"></a><a name="getrebarctrl"></a>CReBar::GetReBarCtrl  
 このメンバー関数では、基になる一般的なコントロールに直接アクセスができます。  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照、 [CReBarCtrl](../../mfc/reference/crebarctrl-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を呼び出して、rebar をカスタマイズするには、Windows rebar コモン コントロールの機能を活用します。 呼び出すと`GetReBarCtrl`への参照オブジェクトが返されます、`CReBarCtrl`オブジェクトのいずれかのメンバー関数のセットを使用できるようにします。  
  
 使用の詳細については`CReBarCtrl`、rebar をカスタマイズするを参照してください。[を使用して CReBarCtrl](../../mfc/using-crebarctrl.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CReBarCtrl&#2;](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MFCIE](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)





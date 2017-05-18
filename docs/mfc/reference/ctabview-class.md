---
title: "CTabView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
dev_langs:
- C++
helpviewer_keywords:
- CTabView class
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
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
ms.openlocfilehash: 20f5745c3784e771d6ec95f7d4dc363142c687f8
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ctabview-class"></a>CTabView クラス
`CTabView`クラスは、タブ コントロール クラスの使用を簡略化 ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) MFC のドキュメント/ビュー アーキテクチャを使用するアプリケーションにします。  
  
## <a name="syntax"></a>構文  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|タブ コントロールに新しいビューを追加します。|  
|[CTabView::FindTab](#findtab)|タブ コントロール内には、指定されたビューのインデックスを返します。|  
|[CTabView::GetActiveView](#getactiveview)|現在アクティブなビューへのポインターを返します|  
|[CTabView::GetTabControl](#gettabcontrol)|ビューに関連付けられているタブ コントロールへの参照を返します。|  
|[CTabView::RemoveView](#removeview)|タブ コントロールから、ビューを削除します。|  
|[CTabView::SetActiveView](#setactiveview)|ビューをアクティブになります。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|タブ ビューが共有の水平スクロール バーを持つかどうかを判断するタブ ビューを作成するときに、フレームワークによって呼び出されます。|  
|[CTabView::OnActivateView](#onactivateview)|アクティブまたは非アクティブなタブの表示が行われたときに、フレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 このクラスでは、簡単にドキュメント/ビュー アプリケーションにタブ付きビューを追加します。 `CTabView``CView`の埋め込みを含むクラスを派生`CMFCTabCtrl`オブジェクトです。 `CTabView`サポートに必要なすべてのメッセージ処理、`CMFCTabCtrl`オブジェクトです。 クラスを単純に派生`CTabView`を追加し、アプリケーションに組み込む`CView`-派生クラスを使用して、`AddView`メソッドです。 タブ コントロールのタブとしてそれらのビューが表示されます。  
  
 たとえば、さまざまな方法で表すことができるドキュメントがあります。 スプレッドシート、グラフ、編集可能なフォームおよびなどとします。 これらに挿入する操作、必要に応じて、データの描画の個々 のビューを作成できます、 `CTabView`-オブジェクトを派生し、コードを追加せずにタブ付きことができます。  
  
 [TabbedView サンプル: MFC タブ付きビュー アプリケーション](../../visual-cpp-samples.md)の使用方法を示します`CTabView`します。  
  
## <a name="example"></a>例  
 例を次にどのように`CTabView`TabbedView サンプルで使用します。  
  
 [!code-cpp[NVC_MFC_TabbedView&#1;](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxTabView.h  
  
##  <a name="addview"></a>CTabView::AddView  
 タブ コントロールにビューを追加します。  
  
```  
int AddView(
    CRuntimeClass* pViewClass,  
    const CString& strViewLabel,  
    int iIndex=-1,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pViewClass`  
 挿入されたビューのランタイム クラスへのポインター。  
  
 [入力] `strViewLabel`  
 タブのテキストを指定します。  
  
 [入力] `iIndex`  
 ビューを挿入する位置を示す&0; から始まる位置を指定します。 位置が-1 の場合は、最後に新しいタブが挿入されます。  
  
 [入力] `pContext`  
 ポインター、`CCreateContext`ビューのです。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合、ビューのインデックス。 それ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数では、フレームに埋め込まれているタブ コントロールにビューを追加します。  
  
##  <a name="findtab"></a>CTabView::FindTab  
 タブ コントロール内には、指定されたビューのインデックスを返します。  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hWndView`  
 ビューのハンドル。  
  
### <a name="return-value"></a>戻り値  
 見つかった場合、ビューのインデックスそれ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 指定したハンドルを持つビューのインデックスを取得するには、この関数を呼び出します。  
  
##  <a name="getactiveview"></a>CTabView::GetActiveView  
 現在アクティブなビューへのポインターを返します。  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アクティブなビューへの有効なポインターまたは`NULL`アクティブなビューが存在しない場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettabcontrol"></a>CTabView::GetTabControl  
 ビューに関連付けられているタブ コントロールへの参照を返します。  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>戻り値  
 ビューに関連付けられているタブ コントロールへの参照。  
  
##  <a name="isscrollbar"></a>CTabView::IsScrollBar  
 タブ ビューが共有の水平スクロール バーを持つかどうかを判断するタブ ビューを作成するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合はタブ ビューは、共有のスクロール バーと共に作成する必要があります。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 フレームワークがこのメソッドを呼び出すときに、`CTabView`オブジェクトが作成されます。  
  
 オーバーライド、`IsScrollBar`メソッドで、 `CTabView`-クラスと戻り値の派生`TRUE`共有の水平スクロール バーを持つビューを作成する場合。  
  
##  <a name="onactivateview"></a>CTabView::OnActivateView  
 アクティブまたは非アクティブなタブの表示が行われたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `view`  
 ビューへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 このメソッドをオーバーライドして、 `CTabView`-この通知を処理するクラスを派生します。  
  
##  <a name="removeview"></a>CTabView::RemoveView  
 タブ コントロールから、ビューを削除します。  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTabNum`  
 削除するビューのインデックス。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合は、削除されたビューのインデックス。 それ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setactiveview"></a>CTabView::SetActiveView  
 ビューをアクティブになります。  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTabNum`  
 タブ ビューの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`指定されたビューがアクティブで行われた場合`FALSE`場合は、ビューのインデックスが無効です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)


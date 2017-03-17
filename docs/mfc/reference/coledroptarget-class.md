---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
dev_langs:
- C++
helpviewer_keywords:
- COleDropTarget class
- drag and drop, drop target
- drop commands, accepting
- drop commands
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
caps.latest.revision: 23
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
ms.openlocfilehash: 0e9429d531d6af86bc571b1f871fbcd4a8fe2532
ms.lasthandoff: 02/24/2017

---
# <a name="coledroptarget-class"></a>関数のクラス
ウィンドウと OLE ライブラリの間の通信機構を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](#coledroptarget)|`COleDropTarget` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](#ondragenter)|カーソルが最初に、ウィンドウに入ったときに呼び出されます。|  
|[COleDropTarget::OnDragLeave](#ondragleave)|カーソルがウィンドウ外にドラッグされたときに呼び出されます。|  
|[COleDropTarget::OnDragOver](#ondragover)|ウィンドウの上にカーソルをドラッグするときに繰り返し呼び出されます。|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|カーソルがウィンドウのスクロール領域にドラッグされるかどうかを判断するには、呼び出されます。|  
|[COleDropTarget::OnDrop](#ondrop)|既定のハンドラーのウィンドウにデータが削除されるときに呼び出されます。|  
|[COleDropTarget::OnDropEx](#ondropex)|最初のハンドラーのウィンドウにデータが削除されるときに呼び出されます。|  
|[COleDropTarget::Register](#register)|有効なドロップ先として、ウィンドウを登録します。|  
|[COleDropTarget::Revoke](#revoke)|によって有効なドロップ先はしないようにするウィンドウです。|  
  
## <a name="remarks"></a>コメント  
 このクラスのオブジェクトを作成すると、OLE のドラッグ アンド ドロップ メカニズムを通じてデータを受信するウィンドウことができます。  
  
 Drop コマンドをそのまま使用するウィンドウを取得するには、オブジェクトを最初に作成する必要があります、`COleDropTarget`クラスし、まず、[登録](#register)目的へのポインターを関数`CWnd`唯一のパラメーターとしてオブジェクトです。  
  
 ドラッグ アンド ドロップ操作の詳細については、OLE を使用して記事を参照して[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="coledroptarget"></a>COleDropTarget::COleDropTarget  
 クラスのオブジェクトを構築`COleDropTarget`します。  
  
```  
COleDropTarget();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す[登録](#register)ウィンドウにこのオブジェクトに関連付けることです。  
  
##  <a name="ondragenter"></a>COleDropTarget::OnDragEnter  
 カーソルが最初に、ウィンドウにドラッグされたときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ウィンドウへのポインターが、カーソルを入力します。  
  
 `pDataObject`  
 ドロップ可能なデータを含むデータ オブジェクトへのポインター。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**します。  
  
 `point`  
 クライアント座標でのカーソルの現在の場所が含まれています。  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが行われた場合に発生する影響`point`します。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_NONE`ドロップは許可されていません。  
  
- `DROPEFFECT_COPY`コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE`移動操作が実行されます。  
  
- `DROPEFFECT_LINK`ドロップされたデータから、元のデータへのリンクが確立されます。  
  
- `DROPEFFECT_SCROLL`ドラッグ スクロール操作が発生するか、ターゲットで発生しています。  
  
### <a name="remarks"></a>コメント  
 ウィンドウでドロップ操作を許可するには、この関数をオーバーライドします。 既定の実装[CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)、単に返す`DROPEFFECT_NONE`既定です。  
  
 詳細については、次を参照してください。 [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="ondragleave"></a>COleDropTarget::OnDragLeave  
 ドラッグ操作の実行中に、カーソルがウィンドウを離れたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルのまま、ウィンドウを指します。  
  
### <a name="remarks"></a>コメント  
 ドラッグ操作が指定されたウィンドウを離れると、特別な動作をする場合は、この関数をオーバーライドします。 この関数の既定の実装を呼び出す[CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)します。  
  
 詳細については、次を参照してください。 [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="ondragover"></a>COleDropTarget::OnDragOver  
 カーソルがウィンドウの上にドラッグされたときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを上にウィンドウへのポインター。  
  
 `pDataObject`  
 削除するデータを含むデータ オブジェクトへのポインター。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**します。  
  
 `point`  
 クライアント座標でのカーソルの現在の場所が含まれています。  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが行われた場合に発生する影響`point`します。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_NONE`ドロップは許可されていません。  
  
- `DROPEFFECT_COPY`コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE`移動操作が実行されます。  
  
- `DROPEFFECT_LINK`ドロップされたデータから、元のデータへのリンクが確立されます。  
  
- `DROPEFFECT_SCROLL`ドラッグ スクロール操作が発生するか、ターゲットで発生していることを示します。  
  
### <a name="remarks"></a>コメント  
 この関数は、ウィンドウにドロップ操作を許可するようにオーバーライドする必要があります。 この関数の既定の実装[直前](../../mfc/reference/cview-class.md#ondragover)、返す`DROPEFFECT_NONE`既定です。 この関数が呼び出されるため、ドラッグ アンド ドロップ操作中に頻繁に、必要があります最適化することが可能な限りです。  
  
 詳細については、次を参照してください。 [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer #&21;](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="ondragscroll"></a>COleDropTarget::OnDragScroll  
 呼び出しの前に、フレームワークによって呼び出さ[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)を判断するかどうか`point`スクロール可能な領域ができます。  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを上に現在のウィンドウへのポインター。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**します。  
  
 `point`  
 (ピクセル単位)、画面を基準と、カーソルの位置が含まれています。  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが行われた場合に発生する影響`point`します。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_NONE`ドロップは許可されていません。  
  
- `DROPEFFECT_COPY`コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE`移動操作が実行されます。  
  
- `DROPEFFECT_LINK`ドロップされたデータから、元のデータへのリンクが確立されます。  
  
- `DROPEFFECT_SCROLL`ドラッグ スクロール操作が発生するか、ターゲットで発生していることを示します。  
  
### <a name="remarks"></a>コメント  
 このイベントの特別な動作を提供する場合に、この関数をオーバーライドします。 この関数の既定の実装[CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll)、返す`DROPEFFECT_NONE`し、カーソルがウィンドウの枠線内の既定のスクロール領域にドラッグされると、ウィンドウをスクロールします。  
  
##  <a name="ondrop"></a>COleDropTarget::OnDrop  
 ドロップ操作が行われるときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを上に現在のウィンドウへのポインター。  
  
 `pDataObject`  
 削除するデータを含むデータ オブジェクトへのポインター。  
  
 `dropEffect`  
 Drop 操作のユーザーが選択した結果。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_COPY`コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE`移動操作が実行されます。  
  
- `DROPEFFECT_LINK`ドロップされたデータから、元のデータへのリンクが確立されます。  
  
 `point`  
 (ピクセル単位)、画面を基準と、カーソルの位置が含まれています。  
  
### <a name="return-value"></a>戻り値  
 ドロップが正常に終了した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Framework の最初の呼び出し[OnDropEx](#ondropex)します。 場合、`OnDropEx`関数は、削除を処理しない、フレームワークは、このメンバー関数を呼び出す`OnDrop`します。 通常、アプリケーションは[OnDropEx](../../mfc/reference/cview-class.md#ondropex)をマウスの右ボタンを処理するビュー クラスでドラッグ アンド ドロップします。 ビュー クラスでは通常、 [OnDrop](../../mfc/reference/cview-class.md#ondrop)単純なドラッグ アンド ドロップを処理するために使用します。  
  
 既定の実装`COleDropTarget::OnDrop`呼び出し[この関数](../../mfc/reference/cview-class.md#ondrop)、単に返す**FALSE**既定です。  
  
 詳細については、次を参照してください。 [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="ondropex"></a>COleDropTarget::OnDropEx  
 ドロップ操作が行われるときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを上に現在のウィンドウへのポインター。  
  
 `pDataObject`  
 削除するデータを含むデータ オブジェクトへのポインター。  
  
 `dropDefault`  
 現在のキーの状態に基づく既定のドロップ操作のユーザーが選択した結果。 できます`DROPEFFECT_NONE`します。 ドロップ効果は、「解説」セクションで説明します。  
  
 `dropList`  
 ドロップ ソースがサポートする、ドロップ効果の一覧。 ビットごとの OR を使用して、ドロップ効果の値を組み合わせることができます ( **|**) 操作です。 ドロップ効果は、「解説」セクションで説明します。  
  
 `point`  
 (ピクセル単位)、画面を基準と、カーソルの位置が含まれています。  
  
### <a name="return-value"></a>戻り値  
 指定された位置にある削除の試行から生成されるドロップ効果`point`します。 ドロップ効果は、「解説」セクションで説明します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、まず、この関数を呼び出します。 これで、削除が処理しない場合、フレームワーク[OnDrop](#ondrop)します。 通常をオーバーライド[OnDropEx](../../mfc/reference/cview-class.md#ondropex)マウスの右ボタンをサポートするためにビュー クラスにドラッグ アンド ドロップします。 ビュー クラスでは通常、 [OnDrop](../../mfc/reference/cview-class.md#ondrop)単純なドラッグ アンド ドロップのサポートのケースを処理するために使用します。  
  
 既定の実装`COleDropTarget::OnDropEx`呼び出し[CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)します。 既定では、 [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)を示すためにダミーの値を返すだけで、 [OnDrop](#ondrop)メンバー関数を呼び出す必要があります。  
  
 ドロップ効果では、ドロップ操作に関連付けられたアクションについて説明します。 次のようなドロップ効果の一覧を参照してください。  
  
- `DROPEFFECT_NONE`ドロップは許可されていません。  
  
- `DROPEFFECT_COPY`コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE`移動操作が実行されます。  
  
- `DROPEFFECT_LINK`ドロップされたデータから、元のデータへのリンクが確立されます。  
  
- `DROPEFFECT_SCROLL`ドラッグ スクロール操作が発生するか、ターゲットで発生していることを示します。  
  
 詳細については、次を参照してください。 [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="register"></a>COleDropTarget::Register  
 有効なドロップ先として OLE Dll を現在のウィンドウを登録するには、この関数を呼び出します。  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ドロップ先として登録するのには、ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 登録が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、許容されるためにドロップ操作を呼び出す必要があります。  
  
 詳細については、次を参照してください。 [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="revoke"></a>COleDropTarget::Revoke  
 この関数を呼び出すことによって、ドロップ先として登録されている任意のウィンドウを破棄する前に[登録](#register)ドロップ ターゲットの一覧から削除します。  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>コメント  
 この関数が自動的に呼び出される、 [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)のためいないこの関数を明示的に呼び出す必要は通常は、登録されているウィンドウのハンドラーです。  
  
 詳細については、次を参照してください。 [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDropSource クラス](../../mfc/reference/coledropsource-class.md)


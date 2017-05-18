---
title: "COleDropSource クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
dev_langs:
- C++
helpviewer_keywords:
- drag operations
- drop target, dragging data to
- COleDropSource class
- drag and drop, drop source
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
caps.latest.revision: 24
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
ms.openlocfilehash: f3d0e5b7184cf305459173065b8e1cc07e032aef
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="coledropsource-class"></a>COleDropSource クラス
により、データをドロップ ターゲットにドラッグできます。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](#coledropsource)|`COleDropSource` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](#givefeedback)|カーソルをドラッグ アンド ドロップ操作中に変更します。|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|ドラッグ アンド ドロップ操作中にマウスのキャプチャを処理します。|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|続行をドラッグするかどうかを確認してください。|  
  
## <a name="remarks"></a>コメント  
 [関数](../../mfc/reference/coledroptarget-class.md)クラスは、ドラッグ アンド ドロップ操作の受信側の部分を処理します。 `COleDropSource`オブジェクトがドラッグ操作の開始を決定する、ドラッグ操作中にフィードバックを提供すること、およびドラッグ操作が終了した場合の決定を担当します。  
  
 使用する、`COleDropSource`オブジェクト、コンス トラクターを呼び出すだけです。 これにより、ドラッグ操作を使用して、マウスのクリックなど、どのようなイベントの開始を決定するプロセスが簡略化[された](../../mfc/reference/coledatasource-class.md#dodragdrop)、[クラス](../../mfc/reference/coleclientitem-class.md#dodragdrop)、または[判定できます](../../mfc/reference/coleserveritem-class.md#dodragdrop)関数です。 これらの関数が作成、`COleDropSource`オブジェクトです。 既定の動作を変更することができます、`COleDropSource`オーバーライド可能な関数です。 これらのメンバー関数は、フレームワークから適切なときに呼び出されます。  
  
 ドラッグ アンド ドロップ操作の詳細については、OLE を使用して記事を参照して[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)します。  
  
 詳細については、次を参照してください。 [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="coledropsource"></a>COleDropSource::COleDropSource  
 `COleDropSource` オブジェクトを構築します。  
  
```  
COleDropSource();
```  
  
##  <a name="givefeedback"></a>COleDropSource::GiveFeedback  
 呼び出した後、フレームワークによって呼び出されます[COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover)または[COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter)します。  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 `dropEffect`  
 この時点で、選択したデータのドロップが発生した場合、ユーザーに表示するには効果が発生通常どのようなことを示します。 通常、これは、最新の呼び出しによって返される値[CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)または[直前](../../mfc/reference/cview-class.md#ondragover)します。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_NONE`ドロップは許可されていません。  
  
- `DROPEFFECT_COPY`コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE`移動操作が実行されます。  
  
- `DROPEFFECT_LINK`ドロップされたデータから、元のデータへのリンクが確立されます。  
  
- `DROPEFFECT_SCROLL`ドラッグ スクロール操作が発生するか、ターゲットで発生しています。  
  
### <a name="return-value"></a>戻り値  
 返します。**操作**場合は、ドラッグ中**NOERROR**がない場合。  
  
### <a name="remarks"></a>コメント  
 この時点で、ドロップが発生した場合は、何が起こるかについてのフィードバックを提供するには、この関数をオーバーライドします。 既定の実装では、OLE の既定のカーソルを使用します。 ドラッグ アンド ドロップ操作の詳細については、OLE を使用して記事を参照して[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)します。  
  
 詳細については、次を参照してください。 [IDropSource::GiveFeedback](http://msdn.microsoft.com/library/windows/desktop/ms693723)、 [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129)、および[IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onbegindrag"></a>COleDropSource::OnBeginDrag  
 によって呼び出される、イベントが発生したときに、フレームワークがマウスの左ボタンを押すなどのドラッグ操作を開始できます。  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 選択したデータが含まれるウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ドラッグすることが許可された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 ドラッグの処理を開始する方法を変更する場合は、この関数をオーバーライドします。 既定の実装では、マウスをキャプチャし、ユーザーが左または右マウス ボタンをクリックしたか、マウスを解放する時に、esc キーを押すまでドラッグ モードのままです。  
  
##  <a name="querycontinuedrag"></a>COleDropSource::QueryContinueDrag  
 ドラッグが始まると、この関数はドラッグ操作が取り消されたか完了するまで、framework によって繰り返し呼び出されます。  
  
```  
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed, 
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEscapePressed*  
 最後に呼び出した後、ESC キーが押されたかどうかを示す`COleDropSource::QueryContinueDrag`します。  
  
 `dwKeyState`  
 キーボードの修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**します。  
  
### <a name="return-value"></a>戻り値  
 **DRAGDROP_S_CANCEL** ESC キーまたは右のボタンが押されたか、左ボタンがドラッグを開始する前に発生します。 **DRAGDROP_S_DROP**ドロップ操作を実行する場合。 それ以外の場合`S_OK`します。  
  
### <a name="remarks"></a>コメント  
 この関数をドラッグ ポイントを変更するが取り消された上書きまたはドロップが発生します。  
  
 既定の実装では、ドロップを起動するか、次のように、ドラッグを取り消します。 ESC キーまたはマウスの右ボタンが押されたときに、ドラッグ操作をキャンセルします。 ドラッグすることが開始された後、マウスの左ボタンが発生したときに、ドロップ操作を開始します。 それ以外を返します`S_OK`あり、他の操作を実行しません。  
  
 この関数が頻繁に呼び出されるためにを最適化することが可能な限りです。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)





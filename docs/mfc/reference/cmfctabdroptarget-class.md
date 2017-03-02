---
title: "CMFCTabDropTarget クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget class
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 31f9950df5974fe1561d601d4e9c26b3e8a96a62
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget クラス
タブ コントロールと OLE ライブラリ間の通信機構を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|ユーザーがタブ ウィンドウにオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter))。|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|ユーザーは、フォーカスのあるタブ ウィンドウ以外でオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave))。|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|ユーザーは、フォーカスのあるタブ ウィンドウの上にオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover))。|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|ドラッグ操作の最後に、マウス ボタンを離したときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex))。|  
|[CMFCTabDropTarget::Register](#register)|OLE ドラッグ アンド ドロップ操作の対象にすることができますが、コントロールを登録します。|  
  
### <a name="remarks"></a>コメント  
 このクラスにドラッグ アンド ドロップのサポートを提供する、`CMFCBaseTabCtrl`クラスです。 使用して、アプリケーションが OLE ライブラリを初期化する場合、 [AfxOleInit](ole-initialization.md#afxoleinit)関数の場合、`CMFCBaseTabCtrl`オブジェクトにドラッグ アンド ドロップの操作に登録します。  
  
 `CMFCTabDropTarget`クラスがドラッグ操作が作業中に発生すると、カーソルの下にあるタブをクリックすることで、基本クラスを拡張します。 ドラッグ アンド ドロップ操作の詳細については、次を参照してください。[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)します。  
  
## <a name="example"></a>例  
 `CMFCTabDropTarget` オブジェクトを構築して、その `Register` メソッドを使用する方法を、次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp&#39;](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [関数](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxbasetabctrl.h  
  
##  <a name="a-nameondragentera--cmfctabdroptargetondragenter"></a><a name="ondragenter"></a>CMFCTabDropTarget::OnDragEnter  
 ユーザーがタブ ウィンドウにオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pWnd`|使用されません。|  
|[入力] `pDataObject`|ユーザーがドラッグしたオブジェクトへのポインター。|  
|[入力] `dwKeyState`|修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: `MK_CONTROL`、 `MK_SHIFT`、 `MK_ALT`、 `MK_LBUTTON`、 `MK_MBUTTON`、および`MK_RBUTTON`です。|  
|[入力] `point`|クライアント座標でカーソルの位置。|  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが発生した場合に発生する影響`point`します。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>コメント  
 このメソッドが戻る`DROPEFFECT_NONE`場合ツールバー フレームワークがカスタマイズ モードではないか、クリップボード データ形式は使用できません。 通話の結果が返される場合は、`CMFCBaseTabCtrl::OnDragEnter`指定されたパラメーターを使用します。  
  
 カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)します。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)します。  
  
##  <a name="a-nameondragleavea--cmfctabdroptargetondragleave"></a><a name="ondragleave"></a>CMFCTabDropTarget::OnDragLeave  
 ユーザーは、フォーカスのあるタブ ウィンドウ以外でオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pWnd`|使用されません。|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`CMFCBaseTabCtrl::OnDragLeave`ドラッグ操作を実行するメソッドです。  
  
##  <a name="a-nameondragovera--cmfctabdroptargetondragover"></a><a name="ondragover"></a>CMFCTabDropTarget::OnDragOver  
 ユーザーは、フォーカスのあるタブ ウィンドウの上にオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pWnd`|使用されません。|  
|[入力] `pDataObject`|ユーザーがドラッグしたオブジェクトへのポインター。|  
|[入力] `dwKeyState`|修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: `MK_CONTROL`、 `MK_SHIFT`、 `MK_ALT`、 `MK_LBUTTON`、 `MK_MBUTTON`、および`MK_RBUTTON`です。|  
|[入力] `point`|クライアント座標のマウス ポインターの位置。|  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが発生した場合に発生する影響`point`します。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ドラッグ操作が作業中に発生すると、カーソルの下にあるタブをクリックします。 返す`DROPEFFECT_NONE`場合ツールバー フレームワークがカスタマイズ モードではないか、クリップボード データ形式は使用できません。 通話の結果が返される場合は、`CMFCBaseTabCtrl::OnDragOver`指定されたパラメーターを使用します。  
  
 カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)します。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)します。  
  
##  <a name="a-nameondropexa--cmfctabdroptargetondropex"></a><a name="ondropex"></a>CMFCTabDropTarget::OnDropEx  
 ドラッグ操作の最後に、マウス ボタンを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pWnd`|使用されません。|  
|[入力] `pDataObject`|ユーザーがドラッグしたオブジェクトへのポインター。|  
|[入力] `dropEffect`|既定のドロップ操作します。|  
|[入力] `dropList`|使用されません。|  
|[入力] `point`|クライアント座標のマウス ポインターの位置。|  
  
### <a name="return-value"></a>戻り値  
 結果として得られるドロップ効果です。 次の&1; つ以上を指定できます。  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す`CMFCBaseTabCtrl::OnDrop`ツールバー framework は、カスタマイズ モードでは、クリップボード データ形式が利用できる場合です。 場合に呼び出し`CMFCBaseTabCtrl::OnDrop`0 以外の値、このメソッドで指定された既定のドロップ効果の取得を返します。`dropEffect`します。 それ以外の場合、このメソッドが戻る`DROPEFFECT_NONE`します。 ドロップ効果の詳細については、次を参照してください。 [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex)します。  
  
 カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)します。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)します。  
  
##  <a name="a-nameregistera--cmfctabdroptargetregister"></a><a name="register"></a>CMFCTabDropTarget::Register  
 OLE ドラッグ アンド ドロップ操作の対象にすることができますが、コントロールを登録します。  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pOwner`|ドロップ先として登録するタブ コントロールです。|  
  
### <a name="return-value"></a>戻り値  
 登録が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register)ドラッグ アンド ドロップ操作のコントロールを登録します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)





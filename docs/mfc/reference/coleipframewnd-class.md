---
title: "COleIPFrameWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
dev_langs:
- C++
helpviewer_keywords:
- COleIPFrameWnd class
- OLE, editing
- OLE, in-place activation
- in-place editing
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 85ce028bb5d72c06a0e228abba1bd08a7f6526cb
ms.lasthandoff: 02/24/2017

---
# <a name="coleipframewnd-class"></a>COleIPFrameWnd クラス
アプリケーションの埋め込み先編集ウィンドウの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleIPFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|`COleIPFrameWnd` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|アイテムは、埋め込み先編集をアクティブになったときに、フレームワークによって呼び出されます。|  
|[COleIPFrameWnd::RepositionFrame](#repositionframe)|埋め込み先編集ウィンドウの位置を変更するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 このクラスを作成し、位置がコンテナー アプリケーションのドキュメント ウィンドウ内のバーを制御します。 また、埋め込みによって生成された通知を処理[COleResizeBar](../../mfc/reference/coleresizebar-class.md)オブジェクトをユーザー、埋め込み先編集ウィンドウのサイズを変更します。  
  
 使用する方法について`COleIPFrameWnd`、記事を参照して[アクティベーション](../../mfc/activation-cpp.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `COleIPFrameWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd  
 構築、`COleIPFrameWnd`オブジェクトし、型の構造体に格納されているが、インプレース状態情報を初期化します**受け取る**します。  
  
```  
COleIPFrameWnd();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[受け取る](http://msdn.microsoft.com/library/windows/desktop/ms693737)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="oncreatecontrolbars"></a>COleIPFrameWnd::OnCreateControlBars  
 フレームワークによって、`OnCreateControlBars`で埋め込み先編集のアイテムがアクティブになったときに機能します。  
  
```  
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,  
    CWnd* pWndDoc);

 
virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,  
    CFrameWnd* pWndDoc);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndFrame*  
 コンテナー アプリケーションのフレーム ウィンドウへのポインター。  
  
 *pWndDoc*  
 コンテナーのドキュメント レベルのウィンドウへのポインター。 できる**NULL**コンテナーが SDI アプリケーションの場合。  
  
### <a name="return-value"></a>戻り値  
 成功した場合に 0 以外の値それ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 コントロール バーが作成されたときに必要な特別な処理を実行するには、この関数をオーバーライドします。  
  
##  <a name="repositionframe"></a>COleIPFrameWnd::RepositionFrame  
 フレームワークによって、`RepositionFrame`コントロール バーを配置し、すべてが表示されているため、埋め込み先編集ウィンドウの位置を変更します。  
  
```  
virtual void RepositionFrame(
    LPCRECT lpPosRect,  
    LPCRECT lpClipRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpPosRect`  
 ポインター、`RECT`構造体、または`CRect`の場所を含むオブジェクト フレーム ウィンドウの現在位置座標、(クライアント領域を基準とのピクセル単位)。  
  
 `lpClipRect`  
 ポインター、`RECT`構造体、または`CRect`オブジェクトの場所を含むフレーム ウィンドウの現在クリッピング四角形の座標を (クライアント領域を基準とのピクセル単位)。  
  
### <a name="remarks"></a>コメント  
 コンテナー ウィンドウで、コントロール バーのレイアウトが異なる非 OLE フレーム ウィンドウで実行します。 非 OLE フレーム ウィンドウには、コントロール バーやその他のオブジェクトへの呼び出しと同様に、特定のフレーム ウィンドウのサイズからの位置が計算されます[表示](../../mfc/reference/cframewnd-class.md#recalclayout)します。 クライアント領域は、残りのコントロール バーなどのオブジェクトの領域を減算します。 A`COleIPFrameWnd`ウィンドウは、特定のクライアント領域に従ってツールバーを配置する一方で、します。 つまり、`CFrameWnd::RecalcLayout`一方"外から内、"動作`COleIPFrameWnd::RepositionFrame`"内側から外側"の動作。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)


---
title: "CCtrlView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCtrlView
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- controls [MFC], common
- CCtrlView class
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
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
ms.openlocfilehash: 569044de59dc3ccd73157abc86855beef57cb558
ms.lasthandoff: 02/24/2017

---
# <a name="cctrlview-class"></a>CCtrlView クラス
Windows 98 および Windows NT Version 3.51 以降がサポートするコモン コントロールにドキュメント/ビュー アーキテクチャを適合させます。  
  
## <a name="syntax"></a>構文  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|`CCtrlView` オブジェクトを構築します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|指定したデバイス コンテキストを使用して描画するためにフレームワークによって呼び出されます。|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|`CCtrlView` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|ビュー クラスの既定のスタイルが含まれています。|  
|[CCtrlView::m_strClass](#m_strclass)|ビュー クラスの Windows のクラス名が含まれています。|  
  
## <a name="remarks"></a>コメント  
 クラス`CCtrlView`とその派生物[CEditView](../../mfc/reference/ceditview-class.md)、 [CListView](../../mfc/reference/clistview-class.md)、 [CTreeView](../../mfc/reference/ctreeview-class.md)、および[CRichEditView](../../mfc/reference/cricheditview-class.md)、Windows 95/98 および Windows NT version 3.51 以降がサポートする新しいコモン コントロールにドキュメント/ビュー アーキテクチャを調整します。 ドキュメント/ビュー アーキテクチャの詳細については、次を参照してください。[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecctrlviewa--cctrlviewcctrlview"></a><a name="cctrlview"></a>CCtrlView::CCtrlView  
 `CCtrlView` オブジェクトを構築します。  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClass`  
 ビュー クラスのウィンドウ クラス名。  
  
 `dwStyle`  
 ビュー クラスのスタイル。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、新しいフレーム ウィンドウが作成されるか、ウィンドウを分割時に、コンス トラクターを呼び出します。 オーバーライド[:oninitialupdate](../../mfc/reference/cview-class.md#oninitialupdate)ドキュメントをアタッチした後、ビューを初期化します。 呼び出す[cwnd::create](../../mfc/reference/cwnd-class.md#create)または[とき](../../mfc/reference/cwnd-class.md#createex)Windows オブジェクトを作成します。  
  
##  <a name="a-namemstrclassa--cctrlviewmstrclass"></a><a name="m_strclass"></a>CCtrlView::m_strClass  
 ビュー クラスの Windows のクラス名が含まれています。  
  
```  
CString m_strClass;  
```  
  
##  <a name="a-namemdwdefaultstylea--cctrlviewmdwdefaultstyle"></a><a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle  
 ビュー クラスの既定のスタイルが含まれています。  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウの作成時に、このスタイルが適用されます。  
  
##  <a name="a-nameondrawa--cctrlviewondraw"></a><a name="ondraw"></a>CCtrlView::OnDraw  
 内容を描画するためにフレームワークによって呼び出される、`CCtrlView`オブジェクトの指定したデバイス コンテキストを使用します。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 描画が行われるデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 `OnDraw`指定した画面デバイス コンテキストを渡して、画面の表示と呼びます通常`pDC`です。  
  
##  <a name="a-nameprecreatewindowa--cctrlviewprecreatewindow"></a><a name="precreatewindow"></a>CCtrlView::PreCreateWindow  
 `CWnd` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>パラメーター  
 *cs*  
 A [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603)構造体。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウの作成を続行する場合は 0 以外作成エラーを示すために 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を直接呼び出すことはありません。  
  
 この関数の既定の実装、 **NULL**ウィンドウ クラス名を取得し、適切な既定値を代入します。 変更するには、このメンバー関数をオーバーライドして、`CREATESTRUCT`ウィンドウが作成される前に構造化します。  
  
 各クラスから派生した`CCtrlView`のオーバーライドに独自の機能を追加`PreCreateWindow`します。 仕様上、これらの派生`PreCreateWindow`文書化されていません。 各クラスとの相互依存関係を適切なスタイルを決定するには、アプリケーションの基本クラスの MFC ソース コードを確認することができます。 オーバーライドする場合は、`PreCreateWindow`アプリケーションの基本クラスで使用されているスタイルが、MFC ソース コードから集めた情報を使用して、必要な機能を提供するかどうかを判断できます。  
  
 ウィンドウ スタイルを変更する方法の詳細については、次を参照してください。、 [MFC で作成したウィンドウのスタイルを変更する](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CView クラス](../../mfc/reference/cview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CTreeView クラス](../../mfc/reference/ctreeview-class.md)   
 [CListView クラス](../../mfc/reference/clistview-class.md)   
 [CRichEditView クラス](../../mfc/reference/cricheditview-class.md)


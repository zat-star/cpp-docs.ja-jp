---
title: "CMFCPreviewCtrlImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPreviewCtrlImpl
- afxwin/CMFCPreviewCtrlImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCPreviewCtrlImpl class
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
caps.latest.revision: 28
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
ms.openlocfilehash: b3ccd0d6e03f652798b45ac35d36f8bc2f63e048
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl クラス
このクラスは、リッチ プレビュー用に、シェルによって提供されるホスト ウィンドウに配置されるウィンドウを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCPreviewCtrlImpl : public CWnd;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl](#dtor)|プレビュー コントロール オブジェクトを破棄します。|  
|[CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|プレビュー コントロール オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::Create](#create)|オーバーロードされます。 Windows のウィンドウを作成する豊富なプレビュー ハンドラーによって呼び出されます。|  
|[CMFCPreviewCtrlImpl::Destroy](#destroy)|このコントロールを破棄する必要があるときに、豊富なプレビュー ハンドラーが呼び出されます。|  
|[CMFCPreviewCtrlImpl::Focus](#focus)|このコントロールにフォーカスが入力を設定します。|  
|[CMFCPreviewCtrlImpl::GetDocument](#getdocument)|このプレビューのコントロールに接続されているドキュメントを返します。|  
|[CMFCPreviewCtrlImpl::Redraw](#redraw)|このコントロールを再描画するように指示します。|  
|[CMFCPreviewCtrlImpl::SetDocument](#setdocument)|ドキュメントの実装と、プレビュー コントロールの間のリレーションシップを作成、プレビュー ハンドラーによって呼び出されます。|  
|[CMFCPreviewCtrlImpl::SetHost](#sethost)|このコントロールの新しい親を設定します。|  
|[CMFCPreviewCtrlImpl::SetPreviewVisuals](#setpreviewvisuals)|リッチ プレビュー ハンドラーによってコンテンツとき呼び出されます豊富なプレビュー機能のビジュアルを設定する必要があります。|  
|[CMFCPreviewCtrlImpl::SetRect](#setrect)|このコントロールの新しい外接する四角形を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::DoPaint](#dopaint)|プレビューを表示するためにフレームワークによって呼び出されます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCPreviewCtrlImpl::m_clrBackColor](#m_clrbackcolor)|プレビュー ウィンドウの背景色です。|  
|[CMFCPreviewCtrlImpl::m_clrTextColor](#m_clrtextcolor)|プレビュー ウィンドウのテキストの色。|  
|[CMFCPreviewCtrlImpl::m_font](#m_font)|プレビュー ウィンドウにテキストを表示するために使用するフォントです。|  
|[CMFCPreviewCtrlImpl::m_pDocument](#m_pdocument)|コントロールにコンテンツを持つがプレビューされているドキュメントへのポインター。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h    
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="a-namecmfcpreviewctrlimpla-cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a>CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
プレビュー コントロール オブジェクトを構築します。

### <a name="syntax"></a>構文
CMFCPreviewCtrlImpl() です。  

## <a name="a-namecreatea-cmfcpreviewctrlimplcreate"></a><a name="create"></a>CMFCPreviewCtrlImpl::Create
オーバーロードされます。 Windows のウィンドウを作成する豊富なプレビュー ハンドラーによって呼び出されます。  
  
### <a name="syntax"></a>構文  
  
```  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc  
);  
virtual BOOL Create(  
   HWND hWndParent,  
   const RECT* prc,  
   CCreateContext* pContext  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 リッチ プレビュー用に、シェルによって提供されるホスト ウィンドウへのハンドル。  
  
 `prc`  
 初期サイズとウィンドウの位置を指定します。  
  
 `pContext`  
 作成コンテキストへのポインター。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`作成が成功した場合それ以外の場合`FALSE`します。  
  
## <a name="a-namedestroya-cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a>CMFCPreviewCtrlImpl::Destroy
このコントロールを破棄する必要があるときに、豊富なプレビュー ハンドラーが呼び出されます。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void Destroy();  
```  
  
## <a name="a-namedopainta-cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a>CMFCPreviewCtrlImpl::DoPaint  
プレビューを表示するためにフレームワークによって呼び出されます。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void DoPaint(  
   CPaintDC* pDC  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 描画するためのデバイス コンテキストへのポインター。  


## <a name="a-namefocusa-cmfcpreviewctrlimplfocus"></a><a name="focus"></a>CMFCPreviewCtrlImpl::Focus  
このコントロールにフォーカスが入力を設定します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void Focus();  
```  
## <a name="a-namegetdocumenta-cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a>CMFCPreviewCtrlImpl::GetDocument
このプレビューのコントロールに接続されているドキュメントを返します。  
  
### <a name="syntax"></a>構文  
  
```  
ATL::IDocument* GetDocument();  
```  
  
### <a name="return-value"></a>戻り値  
 コントロールにコンテンツを持つがプレビューされているドキュメントへのポインター。

## <a name="a-namemclrbackcolora-cmfcpreviewctrlimplmclrbackcolor"></a><a name="m_clrbackcolor"></a>CMFCPreviewCtrlImpl::m_clrBackColor  
プレビュー ウィンドウの背景色です。  
  
### <a name="syntax"></a>構文  
  
```  
COLORREF m_clrBackColor;  
```  

## <a name="a-namemclrtextcolora-cmfcpreviewctrlimplmclrtextcolor"></a><a name="m_clrtextcolor"></a>CMFCPreviewCtrlImpl::m_clrTextColor
プレビュー ウィンドウのテキストの色。  
  
### <a name="syntax"></a>構文  
  
```  
COLORREF m_clrTextColor;  
```  
## <a name="a-namemfonta-cmfcpreviewctrlimplmfont--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a>CMFCPreviewCtrlImpl::m_font フォントがプレビュー ウィンドウにテキストを表示するために使用します。  
  
### <a name="syntax"></a>構文  
  
```  
CFont m_font;  
```  
## <a name="a-namempdocumenta-cmfcpreviewctrlimplmpdocument"></a><a name="m_pdocument"></a>CMFCPreviewCtrlImpl::m_pDocument  
コントロールにコンテンツを持つがプレビューされているドキュメントへのポインター。  
  
### <a name="syntax"></a>構文  
  
```  
ATL::IDocument* m_pDocument;  
```  

## <a name="a-nameredrawa-cmfcpreviewctrlimplredraw"></a><a name="redraw"></a>CMFCPreviewCtrlImpl::Redraw  
このコントロールを再描画するように指示します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void Redraw();  
```  
## <a name="a-namesetdocumenta-cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a>CMFCPreviewCtrlImpl::SetDocument 
ドキュメントの実装と、プレビュー コントロールの間のリレーションシップを作成、プレビュー ハンドラーによって呼び出されます。  
  
### <a name="syntax"></a>構文  
  
```  
void SetDocument(  
   IDocument* pDocument  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDocument`  
 ドキュメントの実装へのポインター。  

## <a name="a-namesethosta-cmfcpreviewctrlimplsethost"></a><a name="sethost"></a>CMFCPreviewCtrlImpl::SetHost  
このコントロールの新しい親を設定します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void SetHost(  
   HWND hWndParent  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 新しい親ウィンドウへのハンドル。  

## <a name="a-namesetpreviewvisualsa-cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a>CMFCPreviewCtrlImpl::SetPreviewVisuals  
リッチ プレビュー ハンドラーによってコンテンツとき呼び出されます豊富なプレビュー機能のビジュアルを設定する必要があります。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void SetPreviewVisuals(  
   COLORREF clrBack,  
   COLORREF clrText,  
   const LOGFONTW *plf  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `clrBack`  
 プレビュー ウィンドウの背景色です。  
  
 `clrText`  
 プレビュー ウィンドウのテキストの色。  
  
 `plf`  
 プレビュー ウィンドウにテキストを表示するために使用するフォントです。 

##  <a name="a-namesetrecta-cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a>CMFCPreviewCtrlImpl::SetRect  
このコントロールの新しい外接する四角形を設定します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual void SetRect(  
   const RECT* prc,  
   BOOL bRedraw  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `prc`  
 新しいサイズと、プレビュー コントロールの位置を指定します。  
  
 `bRedraw`  
 コントロールを再描画されるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 通常、ホスト コントロールがサイズ変更されると、新しい外接する四角形が設定されます。  

## <a name="a-namedtora-cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a>CMFCPreviewCtrlImpl:: ~ CMFCPreviewCtrlImpl  
プレビュー コントロール オブジェクトを破棄します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual ~CMFCPreviewCtrlImpl();  
```  
  


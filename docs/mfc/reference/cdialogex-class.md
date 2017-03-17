---
title: "CDialogEx クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
dev_langs:
- C++
helpviewer_keywords:
- CDialogEx class
- CDialogEx::PreTranslateMessage method
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: 27
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
ms.openlocfilehash: c12aa0152fdbf83e423b944a0100045962ddb704
ms.lasthandoff: 02/24/2017

---
# <a name="cdialogex-class"></a>CDialogEx クラス
`CDialogEx` クラスは、ダイアログ ボックスの背景色と背景イメージを指定します。   
  
## <a name="syntax"></a>構文  
  
```  
class CDialogEx : public CDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDialogEx::CDialogEx](#cdialogex)|`CDialogEx` オブジェクトを構築します。|  
|`CDialogEx::~CDialogEx`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|ダイアログ ボックスの背景色を設定します。|  
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|ダイアログ ボックスの背景イメージを設定します。|  
  
## <a name="remarks"></a>コメント  
 `CDialogEx` クラスを使用するには、ダイアログ ボックス クラスを `CDialogEx` クラスではなく `CDialog` クラスから派生させます。  
  
 ダイアログ ボックス イメージは、リソース ファイルに格納されます。 フレームワークは、リソース ファイルから読み込まれたイメージを自動的に削除します。 現在の背景イメージをプログラムで削除する、 [CDialogEx::SetBackgroundImage](#setbackgroundimage)メソッドまたは実装、`OnDestroy`イベント ハンドラーです。 呼び出すと、 [CDialogEx::SetBackgroundImage](#setbackgroundimage)メソッドでパス、`HBITMAP`イメージ ハンドルとしてパラメーター。 `CDialogEx` オブジェクトがイメージの所有権を取得し、`m_bAutoDestroyBmp` フラグが `TRUE` である場合は、そのイメージを削除します。  
  
 A`CDialogEx`オブジェクトの親になることができます、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトです。 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトの呼び出し、`CDialogEx::SetActiveMenu`メソッドと、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトが開いたします。 その後、`CDialogEx`オブジェクトが処理されるまで、あらゆるメニュー イベント、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトが閉じられています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdialogex.h  
  
##  <a name="cdialogex"></a>CDialogEx::CDialogEx  
 `CDialogEx` オブジェクトを構築します。  
  
```  
CDialogEx(
    UINT nIDTemplate,  
    CWnd* pParent=NULL);

 
CDialogEx(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIDTemplate`  
 ダイアログ ボックスのテンプレートのリソース ID。  
  
 [入力] `lpszTemplateName`  
 ダイアログ ボックスのテンプレートのリソースの名前。  
  
 [入力] `pParent`  
 親ウィンドウへのポインター。 既定値は `NULL` です。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。 既定値は `NULL` です。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setbackgroundcolor"></a>CDialogEx::SetBackgroundColor  
 ダイアログ ボックスの背景色を設定します。  
  
```  
void SetBackgroundColor(
    COLORREF color,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `color`  
 RGB 色の値。  
  
 [入力] `bRepaint`  
 `TRUE`すぐに画面を更新するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setbackgroundimage"></a>CDialogEx::SetBackgroundImage  
 ダイアログ ボックスの背景イメージを設定します。  
  
```  
void SetBackgroundImage(
    HBITMAP hBitmap,  
    BackgroundLocation location=BACKGR_TILE,  
    BOOL bAutoDestroy=TRUE,  
    BOOL bRepaint=TRUE);

 
BOOL SetBackgroundImage(
    UINT uiBmpResId,  
    BackgroundLocation location=BACKGR_TILE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hBitmap`  
 背景イメージへのハンドル。  
  
 [入力] `uiBmpResId`  
 背景イメージのリソース ID です。  
  
 [入力] `location`  
 いずれか、`CDialogEx::BackgroundLocation`イメージの場所を指定する値。 有効な値には、BACKGR_TILE、BACKGR_TOPLEFT、BACKGR_TOPRIGHT、BACKGR_BOTTOMLEFT、および BACKGR_BOTTOMRIGHT が含まれます。 既定値は、BACKGR_TILE です。  
  
 [入力] `bAutoDestroy`  
 `TRUE`背景イメージを自動的に破棄するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `bRepaint`  
 `TRUE`ダイアログ ボックスがすぐに再描画それ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 2 番目のメソッド オーバー ロード構文、`TRUE`場合は、メソッドが成功した以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 指定したイメージはダイアログ ボックスのクライアント領域に合わせて伸縮されません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)   
 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)


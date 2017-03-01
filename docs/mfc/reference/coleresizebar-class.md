---
title: "COleResizeBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleResizeBar
dev_langs:
- C++
helpviewer_keywords:
- OLE items, resizing
- in-place items
- in-place items, resizing
- resizing in-place OLE items
- control bars, resizing
- COleResizeBar class
ms.assetid: 56a708d9-28c5-4eb0-9404-77b688d91c63
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
ms.openlocfilehash: 99ba53c771d018b8c69c5951703b9d6f7b4afe9b
ms.lasthandoff: 02/24/2017

---
# <a name="coleresizebar-class"></a>COleResizeBar クラス
OLE の埋め込み先アイテムのサイズ変更をサポートするコントロール バーの一種です。  
  
## <a name="syntax"></a>構文  
  
```  
class COleResizeBar : public CControlBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleResizeBar::COleResizeBar](#coleresizebar)|`COleResizeBar` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleResizeBar::Create](#create)|作成して Windows 子ウィンドウを初期化し、それに関連付ける、`COleResizeBar`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `COleResizeBar`オブジェクトとして表示されます、 [CRectTracker](../../mfc/reference/crecttracker-class.md)斜線の外枠で、外部のハンドルのサイズを変更します。  
  
 `COleResizeBar`オブジェクトから派生するフレーム ウィンドウ オブジェクトの通常の埋め込みのメンバーである、 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)クラスです。  
  
 詳細については、記事を参照してください。[アクティベーション](../../mfc/activation-cpp.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `COleResizeBar`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-namecoleresizebara--coleresizebarcoleresizebar"></a><a name="coleresizebar"></a>COleResizeBar::COleResizeBar  
 `COleResizeBar` オブジェクトを構築します。  
  
```  
COleResizeBar();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す**作成**をサイズ変更バー オブジェクトを作成します。  
  
##  <a name="a-namecreatea--coleresizebarcreate"></a><a name="create"></a>COleResizeBar::Create  
 子ウィンドウを作成し、関連付けます、`COleResizeBar`オブジェクトです。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_RESIZE_BAR);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 サイズ変更バーの親ウィンドウへのポインター。  
  
 `dwStyle`  
 指定、[ウィンドウ スタイル](../../mfc/reference/window-styles.md)属性です。  
  
 `nID`  
 子ウィンドウのサイズ変更バーの id。  
  
### <a name="return-value"></a>戻り値  
 サイズ変更バーが作成された場合は 0 以外それ以外の場合 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル SUPERPAD](../../visual-cpp-samples.md)   
 [CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleServerDoc クラス](../../mfc/reference/coleserverdoc-class.md)


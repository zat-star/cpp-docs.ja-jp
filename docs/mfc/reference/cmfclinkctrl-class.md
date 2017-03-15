---
title: "CMFCLinkCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl class
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
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
ms.openlocfilehash: 8c926c0ef611470b137d2bb897c012a85645c90c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl クラス
`CMFCLinkCtrl`クラスのボタンをハイパーリンクとして表示し、ボタンがクリックされたときに、リンク先を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|ボタンのテキストとして指定された URL を表示します。|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|暗黙的なプロトコルを設定します (たとえば、"http:") の URL のです。|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|ボタンのテキストまたはビットマップを含むボタンのサイズを変更します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|フォーカスされたボタンの四角形が描画される前に、フレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 派生するボタンをクリックすると、`CMFCLinkCtrl`クラス、フレームワーク、ボタンの URL をパラメーターとして渡しますに、`ShellExecute`メソッドです。 続いて、`ShellExecute`メソッドは、URL のターゲットを開きます。  
  
## <a name="example"></a>例  
 次の例では、サイズを設定する方法、`CMFCLinkCtrl`オブジェクト、および url とのツールヒントを設定する方法、`CMFCLinkCtrl`オブジェクトです。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls&#9;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#10;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxlinkctrl.h  
  
##  <a name="a-nameondrawfocusrecta--cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect  
 フォーカスされたボタンの四角形が描画される前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rectClient`  
 リンク コントロールに外接する四角形。  
  
### <a name="remarks"></a>コメント  
 ボタンのフォーカスされた四角形を描画する独自のコードを使用する場合は、このメソッドをオーバーライドします。  
  
##  <a name="a-nameseturla--cmfclinkctrlseturl"></a><a name="seturl"></a>CMFCLinkCtrl::SetURL  
 ボタンのテキストとして指定された URL を表示します。  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszURL`  
 表示するボタンのテキスト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-nameseturlprefixa--cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a>CMFCLinkCtrl::SetURLPrefix  
 暗黙的なプロトコルを設定します (たとえば、"http:") の URL のです。  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszPrefix`  
 URL のプロトコルのプレフィックス。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、URL プレフィックスを設定できます。 プレフィックスは、ボタンの表面に表示されませんが、URL のターゲットへの参照を使用することができます。  
  
##  <a name="a-namesizetocontenta--cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent  
 ボタンのテキストまたはビットマップを含むボタンのサイズを変更します。  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bVCenter`  
 `TRUE`ボタンのテキストと、リンク コントロールの上下の垂直方向にビットマップを中央に配置します。それ以外の場合、`FALSE`です。 既定値は `FALSE` です。  
  
 [入力] `bHCenter`  
 `TRUE`ボタンのテキストと、リンク コントロールの左側および右側の間で水平方向にビットマップを中央に配置します。それ以外の場合、`FALSE`です。 既定値は `FALSE` です。  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)リンク コントロールの新しいサイズを格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl クラス](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)


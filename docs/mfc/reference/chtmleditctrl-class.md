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
- CHtmlEditCtrl
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrl class
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4aca52508663e94ee9a1b55843ad05613aa40b0b
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditctrl-class"></a>関数のクラス
MFC ウィンドウ内の WebBrowser ActiveX コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CHtmlEditCtrl: public CWnd,   
    public CHtmlEditCtrlBase<CHtmlEditCtrl>  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|`CHtmlEditCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CHtmlEditCtrl::Create](#create)|WebBrowser ActiveX コントロールを作成し、それにアタッチ、`CHtmlEditCtrl`オブジェクトです。 この関数は、編集モードに自動的に WebBrowser ActiveX コントロールを追加します。|  
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|取得、 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx)ドキュメント上のインターフェイスは、コンテナー内の WebBrowser コントロールに現在読み込まれています。|  
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|コンテナー内の WebBrowser コントロールでの読み込みに既定のドキュメントの URL を取得します。|  
  
## <a name="remarks"></a>コメント  
 作成した後、コントロールが自動的に組み込むホステッド WebBrowser 編集モードです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxhtml.h  
  
##  <a name="a-namechtmleditctrla--chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a>CHtmlEditCtrl::CHtmlEditCtrl  
 `CHtmlEditCtrl` オブジェクトを構築します。  
  
```  
CHtmlEditCtrl();
```  
  
##  <a name="a-namecreatea--chtmleditctrlcreate"></a><a name="create"></a>CHtmlEditCtrl::Create  
 WebBrowser ActiveX コントロールを作成し、それにアタッチ、`CHtmlEditCtrl`オブジェクトです。 この関数では編集モードを WebBrowser ActiveX コントロールが自動的に既定のドキュメントに移動し、後に配置されます。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszWindowName`  
 このパラメーターは使用されません。  
  
 `dwStyle`  
 このパラメーターは使用されません。  
  
 `rect`  
 コントロールのサイズと位置を指定します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウを指定します。 ことはできません**NULL**します。  
  
 `nID`  
 コントロールの ID を指定します  
  
 `pContext`  
 このパラメーターは使用されません。  
  
### <a name="return-value"></a>戻り値  
 返します。 **TRUE**成功した場合、 **FALSE**失敗します。  
  
##  <a name="a-namegetdhtmldocumenta--chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditCtrl::GetDHtmlDocument  
 取得、 [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx)ドキュメント上のインターフェイスは、コンテナー内の WebBrowser コントロールで現在読み込まれています。  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `ppDocument`  
 ドキュメントのインターフェイスです。  
  
##  <a name="a-namegetstartdocumenta--chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditCtrl::GetStartDocument  
 コンテナー内の WebBrowser コントロールでの読み込みに既定のドキュメントの URL を取得します。  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)



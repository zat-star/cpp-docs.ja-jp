---
title: "CMFCMenuButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::CMFCMenuButton
- AFXMENUBUTTON/CMFCMenuButton::PreTranslateMessage
- AFXMENUBUTTON/CMFCMenuButton::SizeToContent
- AFXMENUBUTTON/CMFCMenuButton::m_bOSMenu
- AFXMENUBUTTON/CMFCMenuButton::m_bRightArrow
- AFXMENUBUTTON/CMFCMenuButton::m_bStayPressed
- AFXMENUBUTTON/CMFCMenuButton::m_hMenu
- AFXMENUBUTTON/CMFCMenuButton::m_nMenuResult
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuButton class
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 65c334ce68dbbbae2b21da2c40aa9420cdeb51bd
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton クラス
ポップアップ メニューを表示してユーザーのメニュー選択を報告するボタンです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|`CMFCMenuButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|ディスパッチされる前に、ウィンドウ メッセージを変換するためにフレームワークによって呼び出されます。 (`CMFCButton::PreTranslateMessage` をオーバーライドします)。|  
|[CMFCMenuButton::SizeToContent](#sizetocontent)|そのテキストとイメージのサイズに応じてボタンのサイズを変更します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|既定のシステムのポップアップ メニューを表示するかを使用するかを示す[CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)します。|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|下にあるか、ボタンの右側に、ポップアップ メニューに表示されるかどうかを指定します。|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|メニュー ボタンがボタンを離した後に、状態を変更するかどうかを指定します。|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|関連付けられた Windows メニューへのハンドル。|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|項目を示す識別子、ユーザーは、ポップアップ メニューから選択します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCMenuButton`クラスから派生して、 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)から派生した、さらに、 [CButton クラス](../../mfc/reference/cbutton-class.md)します。 したがって、使用することができます`CMFCMenuButton`コードを使用すると同じ方法で`CButton`します。  
  
 作成するときに、 `CMFCMenuButton`、関連付けられているポップアップ メニューに、ハンドルに渡す必要があります。 次に、関数を呼び出して`CMFCMenuButton::SizeToContent`します。 `CMFCMenuButton::SizeToContent`ボタンのサイズがポップアップ ウィンドウが表示される場所の下に、または、ボタンの右側に場所を指している矢印を含められることを確認します。  
  
## <a name="example"></a>例  
 次の例では、ボタンにアタッチ メニューのハンドルを設定し、そのテキストとイメージのサイズに応じてボタンのサイズを変更して、フレームワークによって表示されるポップアップ メニューを設定する方法を示します。 このコード スニペットの一部である、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls #&38;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#39;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmenubutton.h  
  
##  <a name="cmfcmenubutton"></a>CMFCMenuButton::CMFCMenuButton  
 新しい[CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)オブジェクトです。  
  
```  
CMFCMenuButton();
```  
  
##  <a name="m_bosmenu"></a>CMFCMenuButton::m_bOSMenu  
 ポップアップ メニューを示すブール型のメンバー変数、フレームワークが表示されます。  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>コメント  
 場合`m_bOSMenu`は`TRUE`、継承したフレームワークと記述`TrackPopupMenu`このオブジェクトのメソッドです。 それ以外の場合、フレームワーク[CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu)します。  
  
##  <a name="m_brightarrow"></a>CMFCMenuButton::m_bRightArrow  
 ポップアップ メニューの場所を示すブール型のメンバー変数。  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>コメント  
 ユーザーは、メニュー ボタンを押すと、アプリケーションは、ポップアップ メニューを表示します。 フレームワークは、ボタンの下、または、ボタンの右側に、ポップアップ メニューに表示されます。 ボタンには、ポップアップ メニューが表示される場所を示す小さな矢印もあります。 場合`m_bRightArrow`は`TRUE`フレームワークは、ボタンの右側にポップアップ メニューを表示します。 それ以外の場合、ボタンの下のポップアップ メニューが表示されます。  
  
##  <a name="m_bstaypressed"></a>CMFCMenuButton::m_bStayPressed  
 メニュー ボタンが表示されるかどうかを示すブール型のメンバー変数を押した、ユーザーは、ポップアップ メニューから選択します。  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>コメント  
 場合、`m_bStayPressed`メンバーは`FALSE`、メニュー ボタンになる押されていない場合に使用 をクリックします。 この場合は、フレームワークでは、ポップアップ メニューのみが表示されます。  
  
 場合、`m_bStayPressed`メンバーは`TRUE`ユーザーがボタンをクリックしたときに、メニュー ボタンが押されるになります。 ユーザーがいずれか、選択を行ったか、取り消すことによって、ポップアップ メニューを閉じた後まで押されたままです。  
  
##  <a name="m_hmenu"></a>CMFCMenuButton::m_hMenu  
 関連付けられたメニューへのハンドル。  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>コメント  
 フレームワークには、ユーザーがメニュー ボタンをクリックすると、このメンバー変数で示されたメニューが表示されます。  
  
##  <a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult  
 どの項目を示す整数をユーザーは、ポップアップ メニューから選択します。  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>コメント  
 ユーザーが選択を行わず、メニューをキャンセルするか、エラーが発生した場合、このメンバー変数の値は&0; です。  
  
##  <a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage  
 ディスパッチされる前に、ウィンドウ メッセージを変換するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMsg`  
 指す、 [MSG](../../mfc/reference/msg-structure1.md)処理するメッセージを格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、メッセージが変換されていて、ディスパッチいない必要があります。メッセージが変換されていないと、ディスパッチする必要がある場合は 0。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="sizetocontent"></a>CMFCMenuButton::SizeToContent  
 そのテキストのサイズとイメージのサイズに応じてボタンのサイズを変更します。  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bCalcOnly`  
 このメソッド、ボタンのサイズを変更するかどうかを示すブール値パラメーターです。  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)ボタンの新しいサイズを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出す場合と`bCalcOnly`は`TRUE`、`SizeToContent`ボタンの新しいサイズのみが計算されます。  
  
 ボタンの新しいサイズは、ボタンのテキスト、イメージ、および方向に合わせて計算されます。 フレームワークは、水平方向の端に 10 ピクセルおよび垂直方向の端に 5 ピクセルの定義済みのマージンにも追加します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)


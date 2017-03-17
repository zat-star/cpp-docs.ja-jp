---
title: "CMFCRibbonMainPanel クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonMainPanel class
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3fc37a953e62e6ea90de8402b7f2912b06967e13
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel クラス
クリックしたときに表示されるリボン パネルを実装して、 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonMainPanel : public CMFCRibbonPanel  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|既定のコンストラクター|  
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonMainPanel::Add](#add)|アプリケーション ボタン パネルの左側のウィンドウにリボン要素を追加します。 (上書き[CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add))。|  
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|最近のファイルの一覧のメニューにテキスト文字列を追加します。|  
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|リボン アプリケーション パネルの下部ウィンドウにリボン要素を追加します。|  
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|アプリケーション ボタン パネルの右側のウィンドウにリボン要素を追加します。|  
|`CMFCRibbonMainPanel::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|リボンのメイン パネルの領域を表す四角形を返します。|  
|`CMFCRibbonMainPanel::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 フレームワークは、表示、`CMFCRibbonMainPanel`アプリケーション パネルを開くとします。 3 つのペインが含まれています。  
  
-   左側のウィンドウなどのファイルでは、関連付けられているコマンドが含まれています。**開く**、**保存**、**印刷**、および**閉じる**します。 このウィンドウにコマンドを追加するには、呼び出す[CMFCRibbonMainPanel::Add](#add)します。  
  
-   右側のペインには、左側のウィンドウでクリックするコマンドを変更するオプションが含まれています。 たとえばをクリックする**名前を付けて保存**左側のペインから右側のウィンドウが使用可能なファイルの種類を表示できます。 このペインにアイテムを追加するには、呼び出す[CMFCRibbonMainPanel::AddToRight](#addtoright)します。  
  
-   下のペインには、アプリケーションの設定を変更して、プログラムを終了するためのボタンが含まれています。 このペインにアイテムを追加するには、呼び出す[CMFCRibbonMainPanel::AddToBottom](#addtobottom)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
 [CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonMainPanel.h  
  
##  <a name="add"></a>CMFCRibbonMainPanel::Add  
 アプリケーション ボタン パネルの左側のウィンドウにリボン要素を追加します。  
  
```  
virtual void Add(CMFCRibbonBaseElement* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pElem`  
 メイン パネルに追加するリボン要素へのポインター。  
  
### <a name="remarks"></a>コメント  
 パネルにリボン要素を追加します。 このメソッドを使用して追加された要素は、メイン パネルの左側の列に格納されます。  
  
##  <a name="addrecentfileslist"></a>CMFCRibbonMainPanel::AddRecentFilesList  
 最近のファイルの一覧のメニューにテキスト文字列を追加します。  
  
```  
void AddRecentFilesList(
    LPCTSTR lpszLabel,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszLabel`  
 最近使ったファイルの一覧に追加する文字列を指定します。  
  
 `nWidth`  
 最近使ったファイル ボックスの一覧 パネルのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addtobottom"></a>CMFCRibbonMainPanel::AddToBottom  
 リボン アプリケーション パネルの下部ウィンドウにリボン要素を追加します。  
  
```  
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```  
  
### <a name="parameters"></a>パラメーター  
 [in][out]`pElem`  
 メイン パネルの下部に追加するリボン要素へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="addtoright"></a>CMFCRibbonMainPanel::AddToRight  
 アプリケーション ボタン パネルの右側のウィンドウにリボン要素を追加します。  
  
```  
void AddToRight(
    CMFCRibbonBaseElement* pElem,  
    int nWidth = 300);
```  
  
### <a name="parameters"></a>パラメーター  
 `pElem`  
 メイン パネルの右側に追加するリボン要素へのポインター。  
  
 `nWidth`  
 右側のパネルのピクセル単位の幅を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、右側のパネルをリボン要素を追加できます。 右側のパネルには、最近使ったファイル で、通常が表示されますが、リボンの要素を追加することができます。  
  
##  <a name="getcommandsframe"></a>CMFCRibbonMainPanel::GetCommandsFrame  
 リボンのメイン パネルの領域を表す四角形を返します。  
  
```  
CRect GetCommandsFrame() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リボンのメイン パネルの領域を表す四角形。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonPanel クラス](../../mfc/reference/cmfcribbonpanel-class.md)


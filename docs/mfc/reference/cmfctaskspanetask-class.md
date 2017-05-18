---
title: "CMFCTasksPaneTask クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
dev_langs:
- C++
helpviewer_keywords:
- CMFCTasksPaneTask class
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 20713b45c4b6aadc5cdfeaadb6ed269aaf7b337f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask クラス
`CMFCTasksPaneTask`クラスは、タスク ペイン コントロール用のタスクを表すヘルパー クラス ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md))。 タスク オブジェクトは、タスク グループ内の項目を表します ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md))。 各タスクには、ユーザーがタスク名の左側に表示されるタスクやアイコンをクリックしたときにフレームワークが実行するコマンドを設定できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|作成して初期化、`CMFCTasksPaneTask`オブジェクトです。|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|現在のタスクのユーザー補助データを決定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|タスク一覧 ウィンドウが自動的に破棄されるかどうかを決定します。|  
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|フレームワークは太字でタスクのラベルを描画するかどうかを決定します。|  
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|フレームワークのタスクが関連付けられるユーザー定義のデータが含まれています。 タスクに関連付けられているデータがあるない場合は、0 に設定します。|  
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|タスク一覧 ウィンドウへのハンドル。|  
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|フレームワークは、タスクの横に表示されるイメージのイメージ リスト内のインデックス。|  
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|タスク一覧 ウィンドウの高さ。 [タスク] ウィンドウのタスクがない場合は、この値は&0; です。|  
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|ポインター、`CMFCTasksPaneTaskGroup`がこのタスクが属しています。|  
|[CMFCTasksPaneTask::m_rect](#m_rect)|タスクの外接する四角形を指定します。|  
|[CMFCTasksPaneTask::m_strName](#m_strname)|タスクの名前。|  
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|ユーザーがタスクをクリックしたときに、フレームワークが実行されるコマンドのコマンド ID を指定します。 この値が有効なコマンド ID でない場合は、タスクが単純なラベルとして扱われます。|  
  
## <a name="remarks"></a>コメント  
 次の図は、次の&3; つのタスクが含まれるタスク グループを示しています。  
  
 ![展開されたタスク グループ](../../mfc/reference/media/nexttaskgrpexpand.png "nexttaskgrpexpand")  
  
> [!NOTE]
>  タスクが有効なコマンド ID を持たない場合は、単純なラベルとして扱われます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxTasksPane.h  
  
##  <a name="cmfctaskspanetask"></a>CMFCTasksPaneTask::CMFCTasksPaneTask  
 作成して初期化、`CMFCTasksPaneTask`オブジェクトです。  
  
```  
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,  
    LPCTSTR lpszName,  
    int nIcon,  
    UINT uiCommandID,  
    DWORD dwUserData = 0,  
    HWND hwndTask = NULL,  
    BOOL bAutoDestroyWindow = FALSE,  
    int nWindowHeight = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroup`  
 指定、 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)タスクが属しています。  
  
 `lpszName`  
 タスクの名前を指定します。  
  
 `nIcon`  
 イメージ リストには、タスクのイメージのインデックスを指定します。  
  
 `uiCommandID`  
 タスクがクリックされたときに実行されるコマンドのコマンド ID を指定します。  
  
 `dwUserData`  
 ユーザー定義データ。  
  
 `hwndTask`  
 タスク一覧 ウィンドウを識別するハンドルを指定します。  
  
 `bAutoDestroyWindow`  
 場合`TRUE`、タスク一覧 ウィンドウが自動的に破棄されます。  
  
 `nWindowHeight`  
 タスク一覧 ウィンドウの高さを指定します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_bautodestroywindow"></a>CMFCTasksPaneTask::m_bAutoDestroyWindow  
 タスク一覧 ウィンドウが自動的に破棄されるかどうかを決定します。  
  
```  
BOOL m_bAutoDestroyWindow;  
```  
  
### <a name="remarks"></a>コメント  
 設定`TRUE`ことを指定するタスク一覧 ウィンドウ ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask))、自動的に。 それ以外の場合、破棄する必要があります`FALSE`します。  
  
##  <a name="m_bisbold"></a>CMFCTasksPaneTask::m_bIsBold  
 タスクのラベルが太字で描画されるかどうかを決定します。  
  
```  
BOOL m_bIsBold;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーを設定`TRUE`太字テキスト タスク ラベルを表示します。  
  
##  <a name="m_dwuserdata"></a>CMFCTasksPaneTask::m_dwUserData  
 タスクに関連付けられているユーザー定義のデータが含まれています。 タスクに関連付けデータがない場合は、0 に設定します。  
  
```  
DWORD m_dwUserData;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_hwndtask"></a>CMFCTasksPaneTask::m_hwndTask  
 タスク一覧 ウィンドウへのハンドル。  
  
```  
HWND m_hwndTask;  
```  
  
### <a name="remarks"></a>コメント  
 タスク ウィンドウを追加するには、呼び出す[CMFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow)します。  
  
##  <a name="m_nicon"></a>CMFCTasksPaneTask::m_nIcon  
 指定したタスクの横に表示されるイメージを識別するイメージ リスト内のインデックス位置。  
  
```  
int m_nIcon;  
```  
  
### <a name="remarks"></a>コメント  
 設定されているイメージ リスト[CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist)します。  
  
 設定`m_nIcon`画像がない場合、タスクを表示する場合は-1 にします。  
  
##  <a name="m_nwindowheight"></a>CMFCTasksPaneTask::m_nWindowHeight  
 タスク一覧 ウィンドウの高さ。 [タスク] ウィンドウのタスクがない場合は、この値は&0; です。  
  
```  
int m_nWindowHeight;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_pgroup"></a>CMFCTasksPaneTask::m_pGroup  
 ポインター、 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)このタスクが属しています。  
  
```  
CMFCTasksPaneTaskGroup* m_pGroup;  
```  
  
### <a name="remarks"></a>コメント  
 すべてのタスクは、親グループに必要です。 呼び出してタスク ペインにグループを追加する[CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)します。  
  
##  <a name="m_rect"></a>CMFCTasksPaneTask::m_rect  
 タスクの外接する四角形を指定します。  
  
```  
CRect m_rect;  
```  
  
### <a name="remarks"></a>コメント  
 この値は、タスクが描画されるときにフレームワークによって計算されます。  
  
##  <a name="m_strname"></a>CMFCTasksPaneTask::m_strName  
 タスクの名前。  
  
```  
CString m_strName;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_uicommandid"></a>CMFCTasksPaneTask::m_uiCommandID  
 ユーザーがタスクをクリックしたときに実行されるコマンドのコマンド ID を指定します。 この値が有効なコマンド ID でない場合は、タスクが単純なラベルとして扱われます。  
  
```  
UINT m_uiCommandID;  
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setaccdata"></a>CMFCTasksPaneTask::SetACCData  
 現在のタスクのユーザー補助データを決定します。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParent`  
 現在のタスクの親ウィンドウを表します。  
  
 [出力] `data`  
 型のオブジェクト`CAccessibilityData`現在のタスクのユーザー補助データが格納されています。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合、`data`パラメーターが正常に現在のタスクのユーザー補助データに指定されているそれ以外の場合、`FALSE`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)


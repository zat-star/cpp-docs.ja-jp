---
title: "CMFCRibbonLabel クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLabel class
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
caps.latest.revision: 21
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
ms.openlocfilehash: b93e0f6c46818515c8d6bcd8d71b78dcaa435ea6
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonlabel-class"></a>CMFCRibbonLabel クラス
リボンのクリックできないテキスト ラベルを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonLabel : public CMFCRibbonButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|構築して初期化、`CMFCRibbonLabel`は指定されたテキスト文字列でのオブジェクト。|  
|`CMFCRibbonLabel::~CMFCRibbonLabel`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|`CMFCRibbonLabel::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CMFCRibbonLabel::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCRibbonLabel::SetACCData](#setaccdata)|現在のリボン ラベル要素のユーザー補助データを決定します。 (上書き[CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata))。|  
  
### <a name="remarks"></a>コメント  
 リボンのラベルを作成した後に追加パネルを呼び出して[CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)します。  
  
 クイック アクセス ツールバーに、リボンのラベルを追加することはできません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxRibbonLabel.h  
  
##  <a name="cmfcribbonlabel"></a>CMFCRibbonLabel::CMFCRibbonLabel  
 構築して初期化、 [CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)を指定した文字列を表示するオブジェクト。  
  
```  
CMFCRibbonLabel(
    LPCTSTR lpszText,  
    BOOL bIsMultiLine = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszText`  
 ラベルに表示されるテキストです。  
  
 [入力] `bIsMultiLine`  
 `TRUE`ラベルは、複数行のラベルを指定するにはそれ以外の場合、`FALSE`です。  
  
##  <a name="setaccdata"></a>CMFCRibbonLabel::SetACCData  
 現在のリボン ラベル要素のユーザー補助データを決定します。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParent`  
 現在のリボンのラベルの親ウィンドウを表します。  
  
 [出力] `data`  
 型のオブジェクト`CAccessibilityData`を現在のリボンのラベルのユーザー補助データが表示されます。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`場合、`data`パラメーターが正常に現在のリボンのラベルのユーザー補助データに指定されているそれ以外の場合、`FALSE`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)


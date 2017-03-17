---
title: "CMFCRibbonUndoButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CMFCRibbonUndoButton
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::AddUndoAction
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::CleanUpUndoList
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::GetActionNumber
- AFXRIBBONUNDOBUTTON/CMFCRibbonUndoButton::HasMenu
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonUndoButton class
ms.assetid: 5c42adf7-871d-4239-901e-47ae7fb816fc
caps.latest.revision: 35
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
ms.openlocfilehash: d4406e21a7e2a945965020d85a748b93d66b5682
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonundobutton-class"></a>CMFCRibbonUndoButton クラス
`CMFCRibbonUndoButton`クラスは、最新のユーザー コマンドを含むドロップダウン リスト ボタンを実装します。 ユーザーは、それらを元に戻すかやり直すにドロップダウン リストから&1; つ以上の最新のコマンドを選択できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonUndoButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::CMFCRibbonUndoButton](#cmfcribbonundobutton)|新しい`CMFCRibbonUndoButton`オブジェクトを指定するコマンド ID、テキスト ラベル、および親オブジェクトのイメージ リストのイメージを使用します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonUndoButton::AddUndoAction](#addundoaction)|アクションの一覧に新しいアクションを追加します。|  
|[CMFCRibbonUndoButton::CleanUpUndoList](#cleanupundolist)|ドロップダウン リストは、[操作] の一覧をクリアします。|  
|[CMFCRibbonUndoButton::GetActionNumber](#getactionnumber)|ユーザーがドロップダウン リストから選択した項目の数を決定します。|  
|[CMFCRibbonUndoButton::HasMenu](#hasmenu)|オブジェクトにメニューが含まれるかどうかを示します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCRibbonUndoButton`クラスはドロップダウン リストを表示するスタックを使用します。  
  
## <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCRibbonUndoButton`クラス、およびアクションの一覧に新しい動作を追加します。 このコード スニペットの一部である、[リボン ガジェット サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_RibbonGadgets&#2;](../../mfc/reference/codesnippet/cpp/cmfcribbonundobutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonUndoButton](../../mfc/reference/cmfcribbonundobutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribbonundobutton.h  
  
##  <a name="addundoaction"></a>CMFCRibbonUndoButton::AddUndoAction  
 アクションの一覧に新しいアクションを追加します。  
  
```  
void AddUndoAction(LPCTSTR lpszLabel);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszLabel`  
 ドロップダウン リストに表示されるアクション ラベルです。  
  
##  <a name="cleanupundolist"></a>CMFCRibbonUndoButton::CleanUpUndoList  
 ドロップダウン リストは、[操作] の一覧をクリアします。  
  
```  
void CleanUpUndoList();
```  
  
##  <a name="cmfcribbonundobutton"></a>CMFCRibbonUndoButton::CMFCRibbonUndoButton  
 新しい`CMFCRibbonUndoButton`オブジェクトを指定するコマンド ID、テキスト ラベル、および親オブジェクトのイメージ リストのイメージを使用します。  
  
```  
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1);

 
CMFCRibbonUndoButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 コマンドの識別子を指定します。  
  
 [入力] `lpszText`  
 ボタンのテキスト ラベルを指定します。  
  
 [入力] `nSmallImageIndex`  
 ボタンの小さいイメージの親オブジェクトのイメージ リスト内の&0; から始まるインデックス。  
  
 [入力] `nLargeImageIndex`  
 親オブジェクトのイメージ リスト内の&0; から始まるインデックス、ボタンのイメージの大規模なのです。  
  
 [入力] `hIcon`  
 ボタンのイメージとして使用できるアイコンのハンドル。  
  
##  <a name="getactionnumber"></a>CMFCRibbonUndoButton::GetActionNumber  
 ユーザーがドロップダウン リストから選択した項目の数を決定します。  
  
```  
int GetActionNumber() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが選択した項目の数。  
  
##  <a name="hasmenu"></a>CMFCRibbonUndoButton::HasMenu  
 オブジェクトにメニューが含まれるかどうかを示します。  
  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE` を返します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery クラス](../../mfc/reference/cmfcribbongallery-class.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)


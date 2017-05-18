---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
dev_langs:
- C++
helpviewer_keywords:
- drag list box [C++]
- dragging list items
- CDragListBox class
- Windows [C++], list boxes
- list boxes
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 3010fd9a363aa1ca1c946a6fe967a7ba415649d4
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdraglistbox-class"></a>関数のクラス
Windows は、リスト ボックスの機能を提供するだけでなく、`CDragListBox`クラスには、ユーザーがリスト ボックス内のファイル名など、リスト ボックス アイテムの移動ができるようにします。  
  
## <a name="syntax"></a>構文  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|`CDragListBox` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|ドラッグ操作の開始時に、フレームワークによって呼び出されます。|  
|[CDragListBox::CancelDrag](#canceldrag)|ドラッグ操作が取り消されたときに、フレームワークによって呼び出されます。|  
|[CDragListBox::Dragging](#dragging)|ドラッグ操作中に、フレームワークによって呼び出されます。|  
|[CDragListBox::DrawInsert](#drawinsert)|ドラッグのリスト ボックスの挿入ガイドを描画します。|  
|[CDragListBox::Dropped](#dropped)|項目がドロップされた後に、フレームワークによって呼び出されます。|  
|[CDragListBox::ItemFromPt](#itemfrompt)|ドラッグされている項目の位置を返します。|  
  
## <a name="remarks"></a>コメント  
 この機能を持つリスト ボックスでは、ユーザーは最も有益な方法でリスト内の項目の並べ替えをできるようにします。 既定では、リスト ボックスは、リスト内の新しい場所に項目を移動することにします。 ただし、`CDragListBox`に移動することではなく項目をコピーするオブジェクトをカスタマイズすることができます。  
  
 リスト ボックス コントロールに関連付けられている、`CDragListBox`クラスが持つことはできません、 **LBS_SORT**または**LBS_MULTIPLESELECT**スタイル。 リスト ボックスのスタイルについては、次を参照してください。[リスト ボックス スタイル](../../mfc/reference/list-box-styles.md)します。  
  
 アプリケーションの既存のダイアログ ボックスでのドラッグ リスト ボックスを使用するリスト ボックス コントロールをダイアログ エディターを使用して、ダイアログ テンプレートに追加し、メンバー変数を割り当てる (カテゴリの`Control`変数型と`CDragListBox`) ダイアログ テンプレートでリスト ボックス コントロールに対応します。  
  
 コントロールをメンバー変数に割り当てる方法に関する詳細については、次を参照してください。[ダイアログ コントロールのメンバー変数を定義するためのショートカット](../../windows/defining-member-variables-for-dialog-controls.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="begindrag"></a>CDragListBox::BeginDrag  
 によって呼び出される、イベントが発生したときに、フレームワークがマウスの左ボタンを押すなどのドラッグ操作を開始できます。  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)ドラッグされている項目の座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ドラッグすることが許可された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 ドラッグ操作が開始されるときの動作を制御する場合は、この関数をオーバーライドします。 既定の実装では、マウスをキャプチャし、左または右マウス ボタンをクリックするか、ドラッグ操作が取り消された時点で、esc キーを押すまでドラッグ モードのままです。  
  
##  <a name="canceldrag"></a>CDragListBox::CancelDrag  
 ドラッグ操作が取り消されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)ドラッグされている項目の座標を格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 リスト ボックス コントロールに対して特別な処理を処理するには、この関数をオーバーライドします。  
  
##  <a name="cdraglistbox"></a>CDragListBox::CDragListBox  
 `CDragListBox` オブジェクトを構築します。  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>CDragListBox::Dragging  
 内でリスト ボックスの項目がドラッグされている場合に、フレームワークによって呼び出され、`CDragListBox`オブジェクトです。  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) x と y を含むオブジェクト、カーソルの画面座標。  
  
### <a name="return-value"></a>戻り値  
 表示されるカーソルのリソース ID です。 次の値が考えられます。  
  
- `DL_COPYCURSOR`項目がコピーされることを示します。  
  
- `DL_MOVECURSOR`アイテムを移動することを示します。  
  
- `DL_STOPCURSOR`現在のドロップ先が許容ではないことを示します。  
  
### <a name="remarks"></a>コメント  
 既定の動作`DL_MOVECURSOR`します。 追加機能を提供する場合は、この関数をオーバーライドします。  
  
##  <a name="drawinsert"></a>CDragListBox::DrawInsert  
 指定したインデックス項目の前に挿入ガイドを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 `nItem`  
 カーソル位置の&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 値 - 1 は、挿入ガイドをクリアします。 外観や挿入ガイドの動作を変更するには、この関数をオーバーライドします。  
  
##  <a name="dropped"></a>CDragListBox::Dropped  
 内の項目が削除されるときに、フレームワークによって呼び出され、`CDragListBox`オブジェクトです。  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>パラメーター  
 *nSrcIndex*  
 破棄された文字列の&0; から始まるインデックスを指定します。  
  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)ドロップ サイトの座標を格納しているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 既定の動作は、リスト ボックスの項目とそのデータを新しい場所にコピーし、元の項目を削除します。 リスト ボックス アイテムのリスト内の他の場所にドラッグしてコピーできるようにするなど、既定の動作をカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="itemfrompt"></a>CDragListBox::ItemFromPt  
 リスト ボックスの項目の&0; から始まるインデックスを取得するには、この関数がある呼び出し`pt`します。  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)リスト ボックス内の点の座標を格納するオブジェクト。  
  
 *bAutoScroll*  
 スクロールが許可された場合、それ以外の場合 0 0 以外の値。  
  
### <a name="return-value"></a>戻り値  
 ドラッグ リスト ボックス項目の&0; から始まるインデックス。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル TSTCON](../../visual-cpp-samples.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CListBox クラス](../../mfc/reference/clistbox-class.md)


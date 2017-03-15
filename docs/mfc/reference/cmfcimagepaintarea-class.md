---
title: "CMFCImagePaintArea クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImagePaintArea
dev_langs:
- C++
helpviewer_keywords:
- CMFCImagePaintArea class
ms.assetid: c59eec22-f15a-4e58-8c4d-4a18a41f4452
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c16fd9605474e57f167646ddc9bc91d235d1cba5
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimagepaintarea-class"></a>CMFCImagePaintArea クラス
イメージ エディター ダイアログ ボックスでイメージを変更するために使用するピクチャの領域を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCImagePaintArea : public CButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCImagePaintArea::CMFCImagePaintArea](#cmfcimagepaintarea)|`CMFCImagePaintArea` オブジェクトを構築します。|  
|`CMFCImagePaintArea::~CMFCImagePaintArea`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCImagePaintArea::GetMode](#getmode)|現在の描画モードを取得します。|  
|[CMFCImagePaintArea::SetBitmap](#setbitmap)|ピクチャの領域のビットマップ イメージを設定します。|  
|[CMFCImagePaintArea::SetColor](#setcolor)|現在の描画の色を設定します。|  
|[CMFCImagePaintArea::SetMode](#setmode)|現在の描画モードを設定します。|  
  
### <a name="remarks"></a>コメント  
 このクラスは、コードから直接使用するものではありません。  
  
 フレームワークでは、このクラスを使用して、イメージ エディター ダイアログ ボックスにピクチャの領域を表示します。 イメージ エディター] ダイアログ ボックスの詳細については、次を参照してください。 [[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)します。  
  
## <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCImagePaintArea`クラス、現在の色を描画するには、現在の描画モードを設定し、ビットマップ画像画像領域の設定を設定します。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&37;](../../mfc/reference/codesnippet/cpp/cmfcimagepaintarea-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCImagePaintArea](../../mfc/reference/cmfcimagepaintarea-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afximagepaintarea.h  
  
##  <a name="a-namecmfcimagepaintareaa--cmfcimagepaintareacmfcimagepaintarea"></a><a name="cmfcimagepaintarea"></a>CMFCImagePaintArea::CMFCImagePaintArea  
 `CMFCImagePaintArea` オブジェクトを構築します。  
  
```  
CMFCImagePaintArea(CMFCImageEditorDialog* pParentDlg);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pParentDlg`|イメージ エディターの親である ダイアログ ボックスへのポインター。|  
  
##  <a name="a-namegetmodea--cmfcimagepaintareagetmode"></a><a name="getmode"></a>CMFCImagePaintArea::GetMode  
 現在の描画モードを取得します。  
  
```  
IMAGE_EDIT_MODE GetMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 [IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)現在の描画モードを指定する値。  
  
##  <a name="a-namesetbitmapa--cmfcimagepaintareasetbitmap"></a><a name="setbitmap"></a>CMFCImagePaintArea::SetBitmap  
 ピクチャの領域のビットマップ イメージを設定します。  
  
```  
void SetBitmap(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `pBitmap`|表示する新しいビットマップ イメージです。|  
  
### <a name="remarks"></a>コメント  
 場合`pBitmap`は`NULL`、このメソッドは、可変描画領域のサイズを&0; に設定します。 それ以外の場合、指定されたビットマップ イメージのサイズ変更可能な描画領域のサイズに設定します。  
  
##  <a name="a-namesetcolora--cmfcimagepaintareasetcolor"></a><a name="setcolor"></a>CMFCImagePaintArea::SetColor  
 現在の描画の色を設定します。  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `color`|新しい描画の色。|  
  
### <a name="remarks"></a>コメント  
 イメージ エディターのパレット バーから色を選択またはカラー ピッカー、フレームワークが現在の描画の色を更新するには、このメソッドを呼び出す場合。 初期の描画の色は黒 (、`COLORREF`値 0)。  
  
 イメージ エディター ダイアログ ボックスで以外のすべての描画モードの描画の色が使用される`IMAGE_EDIT_MODE_COLOR`します。 描画モードの詳細については、次を参照してください。 [cmfcimagepaintarea::image_edit_mode 列挙体](cmfcimagepaintarea-image-edit-mode-enumeration.md)します。  
  
##  <a name="a-namesetmodea--cmfcimagepaintareasetmode"></a><a name="setmode"></a>CMFCImagePaintArea::SetMode  
 現在の描画モードを設定します。  
  
```  
void SetMode(IMAGE_EDIT_MODE mode);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `mode`|[IMAGE_EDIT_MODE](cmfcimagepaintarea-image-edit-mode-enumeration.md)現在の描画モードを指定する値。|  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)


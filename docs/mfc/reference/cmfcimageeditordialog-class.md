---
title: "CMFCImageEditorDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog class
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1a629f9699aa2d6fb185737b51b36259ce574fe0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog クラス
`CMFCImageEditorDialog`クラスは、イメージ エディター ダイアログ ボックスをサポートしています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|`CMFCImageEditorDialog` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCImageEditorDialog`クラスを含むダイアログ ボックスが表示されます。  
  
-   ピクチャの領域を使用する個々 のピクセルにイメージを変更します。  
  
-   ピクチャの領域のピクセルを修正するためのツールを描画します。  
  
-   描画ツールで使用される色を指定する色パレット。  
  
-   編集する効果を表示するプレビュー領域です。  
  
 次の図は、イメージ エディター ダイアログ ボックスを示しています。  
  
 ![[CMFCImageEditorDialog] ダイアログ ボックス](../../mfc/reference/media/imageedit.png "imageedit")  
  
 使用する方法の&1; つ、`CMFCImageEditorDialog`オブジェクトを渡すことです、`CBitmap`編集しようとするイメージ。 イメージの編集領域が制限されたサイズと論理ピクセルのサイズが、領域に合わせて調整するために、大きいイメージを作成できません。 呼び出す、`DoModal`モーダル ダイアログ ボックスを起動する方法です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afximageeditordialog.h  
  
##  <a name="a-namecmfcimageeditordialoga--cmfcimageeditordialogcmfcimageeditordialog"></a><a name="cmfcimageeditordialog"></a>CMFCImageEditorDialog::CMFCImageEditorDialog  
 `CMFCImageEditorDialog` オブジェクトを構築します。  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBitmap`  
 イメージへのポインター。  
  
 `pParent`  
 現在のイメージ エディター ダイアログ ボックスの親ウィンドウへのポインター。  
  
 `nBitsPixel`  
 色深度にも呼ばれる単一のピクセルの色を表すために使用されるビット数。  場合、`nBitsPixel`パラメーターは、-1、色深度がで指定されたイメージから派生した、`pBitmap`パラメーター。 既定値は -1 です。  
  
### <a name="return-value"></a>戻り値  
 イメージを変更するにイメージ ポインターを渡す、`CMFCImageEditorDialog`コンス トラクターです。 まず、`DoModal`モーダル ダイアログ ボックスを開くにはメソッドです。 ときに、`DoModal`メソッドが戻るビットマップには、新しいイメージが含まれています。  
  
### <a name="remarks"></a>コメント  
  
### <a name="example"></a>例  
 次の例のオブジェクトを構築する方法、`CMFCImageEditorDialog`クラスです。 この例は、[新しいコントロールのサンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_NewControls&#8;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls #&40;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)


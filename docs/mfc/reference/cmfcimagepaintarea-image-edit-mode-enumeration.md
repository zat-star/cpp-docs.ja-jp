---
title: "Cmfcimagepaintarea::image_edit_mode 列挙体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
- CMFCImagePaintArea::IMAGE_EDIT_MODE Enumeration
- CMFCImagePaintArea.IMAGE_EDIT_MODE Enumeration
dev_langs:
- C++
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
caps.latest.revision: 15
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 364b33568e2a21a4649923f4478b5b2456b23747
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE 列挙体
イメージ エディター ダイアログ ボックスでイメージを変更するために使用するための描画モードを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
enum IMAGE_EDIT_MODE  
{  
    IMAGE_EDIT_MODE_PEN = 0,  
    IMAGE_EDIT_MODE_FILL, 
    IMAGE_EDIT_MODE_LINE, 
    IMAGE_EDIT_MODE_RECT, 
    IMAGE_EDIT_MODE_ELLIPSE, 
    IMAGE_EDIT_MODE_COLOR 
};  
```  
  
## <a name="members"></a>メンバー  
  
|||  
|-|-|  
|名前|説明|  
|`IMAGE_EDIT_MODE_PEN`|個々 のピクセルを描画するために使用します。|  
|`IMAGE_EDIT_MODE_FILL`|現在のカーソル位置の色を含むすべての隣接する領域を塗りつぶすために使用します。|  
|`IMAGE_EDIT_MODE_LINE`|線を描画するために使用します。|  
|`IMAGE_EDIT_MODE_RECT`|四角形を描画するために使用します。|  
|`IMAGE_EDIT_MODE_ELLIPSE`|楕円を描画するために使用します。|  
|`IMAGE_EDIT_MODE_COLOR`|現在のカーソル位置に、現在の色を色に設定するために使用します。|  
  
### <a name="remarks"></a>コメント  
 `CMFCImagePaintArea`と`CMFCImageEditorDialog`クラスでは、この列挙体を使用して、現在の描画モードを設定します。 描画モードと現在の色は、イメージ エディター ダイアログ ボックスで画像領域の変更に使用されます。 詳細については`CMFCImagePaintArea`と`CMFCImageEditorDialog`を参照してください[CMFCImagePaintArea クラス](../../mfc/reference/cmfcimagepaintarea-class.md)と[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)します。  
  
 選択すると、カラー イメージからを使用して、`IMAGE_EDIT_MODE_COLOR`描画モード、フレームワーク、現在の描画モードを設定`IMAGE_EDIT_MODE_PEN`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afximagepaintarea.h  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCImagePaintArea クラス](../../mfc/reference/cmfcimagepaintarea-class.md)   
 [CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)


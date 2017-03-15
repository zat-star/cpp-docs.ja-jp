---
title: "Variant パラメーター型の定数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VTS_YPOS_HIMETRIC
- VTS_PICTURE
- VTS_FONT
- VTS_XPOS_HIMETRIC
- VTS_XPOS_PIXELS
- VTS_XSIZE_HIMETRIC
- VTS_YPOS_PIXELS
- VTS_TRISTATE
- VTS_HANDLE
- VTS_YSIZE_HIMETRIC
- VTS_COLOR
- VTS_OPTEXCLUSIVE
- VTS_YSIZE_PIXELS
- VTS_XSIZE_PIXELS
dev_langs:
- C++
helpviewer_keywords:
- VTS_XPOS_HIMETRIC constant
- VTS_FONT constant
- VTS_XPOS_PIXELS constant
- VTS_COLOR constant
- Variants
- VTS_YPOS_PIXELS constant
- VTS_YSIZE_HIMETRIC constant
- VTS_YPOS_HIMETRIC constant
- Variants, parameter type constants
- Variant data constants
- VTS_PICTURE constant
- VTS_TRISTATE constant
- VTS_XSIZE_HIMETRIC constant
- VTS_HANDLE constant
- VTS_XSIZE_PIXELS constant
- VTS_OPTEXCLUSIVE constant
- VTS_YSIZE_PIXELS constant
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
caps.latest.revision: 14
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3b09357859b8fc87252fba704de8f2a927981873
ms.lasthandoff: 02/24/2017

---
# <a name="variant-parameter-type-constants"></a>Variant パラメーター型の定数
このトピックでは、Microsoft Foundation Class ライブラリの OLE コントロール クラスで使用するために設計されたバリアント型パラメーターの種類を指定する新しい定数を示します。  
  
 クラスの定数の一覧を次に示します。  
  
##  <a name="a-namemfcvariantdataconstantsa-variant-data-constants"></a><a name="_mfc_variant_data_constants"></a>Variant データ定数  
  
-   **VTS_COLOR** RGB 色の値を表す 32 ビット整数。  
  
-   **VTS_FONT**へのポインター、**この**OLE フォント オブジェクトのインターフェイスです。  
  
-   **VTS_HANDLE** A Windows ハンドルの値。  
  
-   **VTS_PICTURE**へのポインター、 `IPictureDisp` OLE 画像オブジェクトのインターフェイスです。  
  
-   **VTS_OPTEXCLUSIVE** 16 ビット値のラジオ ボタンなどのコントロールのグループで使用するためのものでは、コントロールを使用します。 この型は、のいずれかを制御する場合、グループをコンテナーに指示、 **TRUE**値にする必要があります他のすべて**FALSE**します。  
  
-   **VTS_TRISTATE**チェック ボックスで使用できるプロパティ (選択されている、オフになって、利用不可)、3 つの値のいずれかなどの 16 ビット符号付き整数を使用します。  
  
-   **VTS_XPOS_HIMETRIC**で x 軸に沿った位置を表す 32 ビット符号なし整数**HIMETRIC**単位です。  
  
-   **VTS_YPOS_HIMETRIC**で y 軸方向の位置を表すために使用する 32 ビット符号なし整数**HIMETRIC**単位です。  
  
-   **VTS_XPOS_PIXELS** 32 ビット符号なし整数 (ピクセル単位)、x 軸に沿った位置を表すために使用します。  
  
-   **VTS_YPOS_PIXELS** 32 ビット符号なし整数 (ピクセル単位)、y 軸に沿った位置を表すために使用します。  
  
-   **VTS_XSIZE_PIXELS** 32 ビット符号なし整数 (ピクセル単位) 画面オブジェクトの幅を表すために使用します。  
  
-   **VTS_YSIZE_PIXELS** 32 ビット符号なし整数 (ピクセル単位) 画面オブジェクトの高さを表すために使用します。  
  
-   **VTS_XSIZE_HIMETRIC**で画面オブジェクトの幅を表すために使用する 32 ビット符号なし整数**HIMETRIC**単位です。  
  
-   **VTS_YSIZE_HIMETRIC**で画面オブジェクトの高さを表すために使用する 32 ビット符号なし整数**HIMETRIC**単位です。  
  
    > [!NOTE]
    >  追加のバリアント定数は、例外として、すべてのバリアント型に対して定義されている**VTS_FONT**と**VTS_PICTURE**、variant データ定数へのポインターを提供します。 使用してこれらの定数がという名前の**付け**`constantname`規則です。 たとえば、 **VTS_PCOLOR**へのポインター、 **VTS_COLOR**定数です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)


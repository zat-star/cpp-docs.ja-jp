---
title: "灰色とディザリングされたビットマップ関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- gray and dithered bitmap functions
ms.assetid: cb139a77-b85e-4504-9d93-24156ad77a41
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: b8b6f43917dfe211f477b3dde0c94323015d18b2
ms.lasthandoff: 02/24/2017

---
# <a name="gray-and-dithered-bitmap-functions"></a>淡色表示 (灰色) ビットマップ関数とディザリングされたビットマップ関数
**灰色のビットマップ関数**  
  
 MFC には、ビットマップのコントロールが無効になっていることを示すための&2; つの関数が用意されています。  
  
 ![灰色と元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
|||  
|-|-|  
|[AfxDrawGrayBitmap](#afxdrawgraybitmap)|灰色のバージョンのビットマップを描画します。|  
|[AfxGetGrayBitmap](#afxgetgraybitmap)|灰色のバージョンのビットマップをコピーします。|  
  
 **ディザリングされたビットマップ関数**  
  
 MFC には、ビットマップの背景をディザリングされたパターンに置き換える&2; つの関数も用意されています。  
  
 ![ディザリングされたと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
|||  
|-|-|  
|[AfxDrawDitheredBitmap](#afxdrawditheredbitmap)|背景がディザリングされたビットマップを描画します。|  
|[AfxGetDitheredBitmap](#afxgetditheredbitmap)|背景がディザリングされたビットマップをコピーします。|  
  
##  <a name="a-nameafxdrawgraybitmapa--afxdrawgraybitmap"></a><a name="afxdrawgraybitmap"></a>AfxDrawGrayBitmap  
 灰色のバージョンのビットマップを描画します。  
  
```   
void AFXAPI AfxDrawGrayBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 宛先 DC を示します。  
  
 *x*  
 宛先の x 座標。  
  
 *y*  
 宛先の y 座標。  
  
 `rSrc`  
 元のビットマップ。  
  
 `crBackground`  
 新しい背景色 (通常は COLOR_MENU などの灰色)。  
  
### <a name="remarks"></a>コメント  
 `AfxDrawGrayBitmap` で描画されるビットマップの外観は、無効なコントロールになります。  
  
 ![灰色と元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&191;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_1.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  

##  <a name="a-nameafxgetgraybitmapa--afxgetgraybitmap"></a><a name="afxgetgraybitmap"></a>AfxGetGrayBitmap  
 灰色のバージョンのビットマップをコピーします。  
  
```   
void AFXAPI AfxGetGrayBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF crBackground); 
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 元のビットマップ。  
  
 `pDest`  
 コピー先のビットマップ。  
  
 `crBackground`  
 新しい背景色 (通常は COLOR_MENU などの灰色)。  
  
### <a name="remarks"></a>コメント  
 `AfxGetGrayBitmap` でコピーされるビットマップの外観は、無効なコントロールのようになります。  
  
 ![灰色と元のアイコンの比較](../../mfc/reference/media/vcgraybitmap.gif "vcgraybitmap")  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&193;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_2.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-nameafxdrawditheredbitmapa--afxdrawditheredbitmap"></a><a name="afxdrawditheredbitmap"></a>AfxDrawDitheredBitmap  
 ディザリングされた (checker) パターンで背景を置き換えます、ビットマップを描画します。  
  
```   
void AFXAPI AfxDrawDitheredBitmap(
    CDC* pDC,  
    int x,  
    int y,  
    const CBitmap& rSrc,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 宛先 DC を示します。  
  
 *x*  
 宛先の x 座標。  
  
 *y*  
 宛先の y 座標。  
  
 `rSrc`  
 元のビットマップ。  
  
 `cr1`  
 2 つのディザー カラーの&1; つは通常白です。  
  
 `cr2`  
 その他のディザー色、通常の明るい灰色 (COLOR_MENU)。  
  
### <a name="remarks"></a>コメント  
 2 色でレプリケート先 DC 上に元のビットマップを描画 (`cr1`と`cr2`) チェッカー パターン ビットマップの背景。 元のビットマップの背景は、その白いピクセルとビットマップの左上隅にあるピクセルの色と一致するすべてのピクセルとして定義されます。  
  
 ![ディザリングされたと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&190;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_3.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  


##  <a name="a-nameafxgetditheredbitmapa--afxgetditheredbitmap"></a><a name="afxgetditheredbitmap"></a>AfxGetDitheredBitmap  
 ディザリングされた (checker) パターンで背景を置き換えます、ビットマップをコピーします。  
  
```   
void AFXAPI AfxGetDitheredBitmap(
    const CBitmap& rSrc,  
    CBitmap* pDest,  
    COLORREF cr1  ,  
    COLORREF cr2); 
```  
  
### <a name="parameters"></a>パラメーター  
 `rSrc`  
 元のビットマップ。  
  
 `pDest`  
 コピー先のビットマップ。  
  
 `cr1`  
 2 つのディザー カラーの&1; つは通常白です。  
  
 `cr2`  
 その他のディザー色、通常の明るい灰色 (COLOR_MENU)。  
  
### <a name="remarks"></a>コメント  
 2 色でコピー先ビットマップにコピー元ビットマップ (`cr1`と`cr2`) 元のビットマップの背景を置き換えるチェッカー パターンです。 元のビットマップの背景は、その白いピクセルとビットマップの左上隅にあるピクセルの色と一致するすべてのピクセルとして定義されます。  
  
 ![ディザリングされたと元のアイコンの比較](../../mfc/reference/media/vcditheredbitmap.gif "vcditheredbitmap")  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&192;](../../mfc/codesnippet/cpp/gray-and-dithered-bitmap-functions_4.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)


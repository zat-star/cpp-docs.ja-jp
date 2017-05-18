---
title: "ピクセル HIMETRIC グローバル関数を作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: efb7e7da896aea4e377225f4c1e2c9948e635705
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="pixelhimetric-conversion-global-functions"></a>ピクセル/HIMETRIC 変換のグローバル関数
これらの関数は、ピクセルと HIMETRIC 単位に変換するためのサポートを提供します。  
  
> [!IMPORTANT]
>  実行するアプリケーションでは、次の表に示されている関数を使用できません、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]です。  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|HIMETRIC 単位 (各単位は 0.01 ミリメートル) をピクセル単位に変換します。|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|HIMETRIC 単位 (ピクセル) に変換します (各単位は 0.01 ミリメートル)。|  
  
##  <a name="atlhimetrictopixel"></a>AtlHiMetricToPixel  
 HIMETRIC 単位 (各単位は 0.01 mm) のオブジェクトのサイズを画面デバイス上のピクセル単位のサイズに変換します。  
  
 
```
extern void AtlHiMetricToPixel(
  const SIZEL* lpSizeInHiMetric, 
  LPSIZEL lpSizeInPix);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSizeInHiMetric`  
 [in]HIMETRIC 単位内のオブジェクトのサイズへのポインター。  
  
 `lpSizeInPix`  
 [out]オブジェクトのサイズ (ピクセル単位) が返されるへのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM 番号&49;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="atlpixeltohimetric"></a>AtlPixelToHiMetric  
 画面デバイス上のピクセル単位のオブジェクトのサイズを HIMETRIC 単位 (各単位は 0.01 mm) のサイズに変換します。  
  
```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix, 
    LPSIZEL lpSizeInHiMetric);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSizeInPix`  
 [in]オブジェクトのサイズ (ピクセル単位) へのポインター。  
  
 `lpSizeInHiMetric`  
 [out]HIMETRIC 単位のオブジェクトのサイズが返されるへのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&51;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  

## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)


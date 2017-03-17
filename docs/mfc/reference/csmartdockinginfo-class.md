---
title: "CSmartDockingInfo クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
dev_langs:
- C++
helpviewer_keywords:
- CSmartDockingInfo class
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9ae735b202299d26b98ec763f65c3f8772d9b914
ms.lasthandoff: 02/24/2017

---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo クラス
スマート ドッキング マーカーの外観を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSmartDockingInfo::CopyTo](#copyto)|現在のスマート ドッキング情報パラメーターに指定されたコピー [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)オブジェクトです。|  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|フレームワークのスマート ドッキング マーカーを表示するときに、現在のテーマの色を使用するかどうかを指定します。|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|スマート ドッキング マーカーの基本の背景色を指定します。|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|置換する色を指定する`m_clrToneSrc`スマート ドッキング マーカー ビットマップにします。|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|スマート ドッキング マーカー ビットマップの色を指定します。|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|透過的にいるときに、スマート ドッキング マーカー ビットマップの色を指定します。|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|サーバーの全体のグループの四角形の境界からスマート ドッキング マーカーの中央のグループのオフセットを指定します。|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|グループ内のすべてのスマート ドッキング マーカーの合計サイズを指定します。|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|フレームワークが強調表示されていないスマート ドッキング マーカーに使用されるビットマップのリソース Id を定義します。|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|フレームワークが強調表示されているスマート ドッキング マーカーに使用されるビットマップのリソース Id を定義します。|  
  
## <a name="remarks"></a>コメント  
 Framework のハンドルは、スマート ドッキング マーカーを内部的にします。 次の図は、標準のスマート ドッキング マーカーを示しています。  
  
 ![スマート ドッキングの標準マーカー](../../mfc/reference/media/nextsdmarkers.png "nextsdmarkers")  
  
 この図では、左側のイメージは、有効になっているタブへのドッキングを持たないサーバーの全体のグループのスマート ドッキング マーカーを示します。 中央のイメージは、右端のスマート ドッキング マーカーを示しています。 右の図は、ドッキング、タブが有効にするにが中央のグループのスマート ドッキング マーカーを示します。 中央のグループのスマート ドッキング マーカーはメインのビットマップを持ち、5 つのスマート ドッキング マーカー ビットマップ。  
  
 スマート ドッキング マーカーの次のパラメーターをカスタマイズすることができます。  
  
-   色 たとえば、ユーザー定義の任意の色と、図のマーカーの青の色を置き換えることができます。  
  
-   透明色。  
  
-   外接する四角形の枠線から中央のグループ内のスマート ドッキング マーカーのオフセットします。  
  
-   サーバーの全体のグループを表すメイン ビットマップです。  
  
-   通常、強調表示されたスマート ドッキング マーカーを表すビットマップです。  
  
 次の図は、カスタマイズされたスマート ドッキング マーカーの例を示します。  
  
 ![スマート ドッキングのカスタム マーカー](../../mfc/reference/media/nextsdmarkerscustom.png "nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxDockingManager.h  
  
##  <a name="copyto"></a>CSmartDockingInfo::CopyTo  
 現在のスマート ドッキングのパラメーターに指定されたコピー [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)オブジェクトです。  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `params`  
 型のオブジェクト`CSmartDockingInfo`を現在のスマート ドッキングのパラメーターが設定されます。  
  
##  <a name="m_busethemecolorinshading"></a>CSmartDockingInfo::m_bUseThemeColorInShading  
 フレームワークのスマート ドッキング マーカーを表示するときに、現在のテーマの色を使用するかどうかを指定します。  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>コメント  
 場合`TRUE`マーカーは、現在のテーマの色を使用して描画されます。 明るい青色でマーカーを描画するそれ以外の場合。  
  
 既定値は `FALSE` です。  
  
##  <a name="m_clrbasebackground"></a>CSmartDockingInfo::m_clrBaseBackground  
 スマート ドッキング マーカーの基本の背景色を指定します。  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>CSmartDockingInfo::m_clrToneDest  
 置換される色を指定する`m_clrToneSrc`スマート ドッキング マーカー ビットマップにします。  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>コメント  
 プログラムでマーカー ビットマップの色を変更するには、この値を設定します。 たとえば、フレームワークで提供される標準のマーカーの色を変更する場合は、目的の色にこの値を設定します。 既定では、 [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) RGB (61、123、241) に設定されている (青み色) です。  
  
 カスタム マーカーの色を変更する、両方を指定する必要があります`m_clrToneDest`と`m_clrToneSrc`です。  
  
##  <a name="m_clrtonesrc"></a>CSmartDockingInfo::m_clrToneSrc  
 スマート ドッキング マーカー ビットマップの色を指定します。  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>コメント  
 別の色と、カスタムのビットマップの色を置換する場合にのみ、この値を設定します。 標準 (フレームワークが提供) の色を変更する場合は、この値を設定する必要はありませんマーカーです。  
  
 使用`(COLORREF)-1`スマート ドッキングのグループのメンバーを空のままにします。  
  
##  <a name="m_clrtransparent"></a>CSmartDockingInfo::m_clrTransparent  
 透過的にいるときに、スマート ドッキング マーカー ビットマップの色を指定します。  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>コメント  
 ドッキングのグループにカスタム マーカーとカスタムのビットマップを表示する場合は、この値を設定する必要があります。  
  
##  <a name="m_ncentralgroupoffset"></a>CSmartDockingInfo::m_nCentralGroupOffset  
 スマート ドッキング マーカーの中央のグループとサーバーの全体のグループの四角形の境界間のオフセットを指定します。  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>コメント  
 カスタム マーカーとスマート ドッキング マーカーの中央のグループの境界間の既定オフセットを変更する場合は、この値を指定します。 既定のオフセットは、5 ピクセルです。  
  
##  <a name="m_sizetotal"></a>CSmartDockingInfo::m_sizeTotal  
 中央のグループ内のすべてのスマート ドッキング マーカーを囲む外接する四角形の合計サイズを指定します。  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>コメント  
 設定`m_sizeTotal`サーバーの全体のグループのマーカーの外接する四角形のサイズにします。 マーカーについて、カスタムのビットマップを使用している場合は、この値を指定する必要があります。  
  
##  <a name="m_uimarkerbmpresid"></a>CSmartDockingInfo::m_uiMarkerBmpResID  
 強調表示されている非カスタム スマート ドッキング マーカーに使用されるビットマップのリソース Id を定義します。  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>コメント  
 スマート ドッキング マーカーを表すビットマップのリソース Id をこの配列に格納します。 `AFX_SD_MARKERS_NUM`現在、5 と定義されます。 配列は次のように入力します。  
  
 `params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;`  
  
 `params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;`  
  
 `params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;`  
  
 `params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;`  
  
 `params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;`  
  
##  <a name="m_uimarkerlightbmpresid"></a>CSmartDockingInfo::m_uiMarkerLightBmpResID  
 強調表示されているカスタム スマート ドッキング マーカーに使用されるビットマップのリソース Id を定義します。  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>コメント  
 強調表示されたスマート ドッキング マーカーを表すビットマップのリソース Id をこの配列に格納します。 `AFX_SD_MARKERS_NUM`現在、5 と定義されます。 配列は次のように入力します。  
  
 `params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;`  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)


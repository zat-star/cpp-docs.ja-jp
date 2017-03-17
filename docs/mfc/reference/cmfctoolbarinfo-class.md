---
title: "CMFCToolBarInfo クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarInfo class
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
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
ms.openlocfilehash: a9e66ffa0b5a751a7e5711ed20927a6adcede45d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo クラス
さまざまな状態のツール バー イメージのリソース ID を含みます。 `CMFCToolBarInfo`パラメーターとして使用されるヘルパー クラスであり、 [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex)メソッドです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolBarInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|標準 (コールド) ツール バー イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|無効なツール バー イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|選択されている (ホット) ツール バー イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|通常、大規模なツール バー イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|大規模なを含むツール バー ビットマップのリソース ID には、ツール バー イメージが無効になります。|  
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|大規模な選択したツール バー イメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|無効なメニューのイメージを含むツール バー ビットマップのリソース ID です。|  
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|メニューのイメージを含むツール バー ビットマップのリソース ID です。|  
  
## <a name="remarks"></a>コメント  
 すべてのツールバーのビットマップは、固定サイズの小さいツール バー イメージ (ボタン) で構成されます。 格納されているそれぞれのリソース ID、`CMFCToolBarInfo`オブジェクトが&1; つの状態 (例では、選択されている、無効な場合、大規模なまたはメニュー画像) 用のツール バー イメージの完全なセットを含むビットマップ。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtoolbar.h  
  
##  <a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID  
 ツールバーのすべての標準ボタン イメージのリソース ID を指定します。  
  
```  
UINT m_uiColdResID;  
```  
  
##  <a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID  
 ツールバーのボタンにアクセスできないイメージのリソース ID を指定します。  
  
```  
UINT m_uiDisabledResID;  
```  
  
##  <a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID  
 ツールバーのボタンが強調表示されたイメージをすべてのリソース ID を指定します。  
  
```  
UINT m_uiHotResID  
```  
  
##  <a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID  
 ツールバーのすべての大きな標準ボタン イメージのリソース ID を指定します。  
  
```  
UINT m_uiLargeColdResID  
```  
  
##  <a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID  
 ツールバーのすべての大きな無効にされたボタン イメージのリソース ID を指定します。  
  
```  
UINT m_uiLargeDisabledResID;  
```  
  
##  <a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID  
 ツールバーの大規模な強調表示されたイメージをすべてのリソース ID を指定します。  
  
```  
UINT m_uiLargeHotResID;  
```  
  
##  <a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID  
 ツールバーのコマンドにアクセスできないイメージのリソース ID を指定します。  
  
```  
UINT m_uiMenuDisabledResID;  
```  
  
##  <a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID  
 ツールバーのすべての標準のメニュー項目のイメージのリソース ID を指定します。  
  
```  
UINT m_uiMenuResID;  
```  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)


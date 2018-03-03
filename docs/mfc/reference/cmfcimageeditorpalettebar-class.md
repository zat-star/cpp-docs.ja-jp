---
title: "CMFCImageEditorPaletteBar クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 539c24acb9b58c96324bc89cdeca6c0d03c6dfdf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar クラス
イメージ エディター ダイアログ ボックスにパレット バー機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|ツール バー ボタンの高さを返します。 (上書き[CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight))。|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|罫線を拡張したボタンをツールバーが表示できるかどうかを判断します。 (上書き[CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable))。|  
  
### <a name="remarks"></a>コメント  
 このクラスは、コードから直接使用するものではありません。  
  
 フレームワークでは、このクラスを使用して、イメージ エディター ダイアログ ボックスでパレット バーを表示します。 イメージ エディター] ダイアログ ボックスの詳細については、次を参照してください。 [[CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afximageeditordialog.h  
  
##  <a name="getrowheight"></a>CMFCImageEditorPaletteBar::GetRowHeight  
 ツール バー ボタンの高さを返します。  
  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツールバーの各ボタンの高さ。  
  
##  <a name="isbuttonextrasizeavailable"></a>CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable  
 罫線を拡張したボタンをツールバーが表示できるかどうかを判断します。  
  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドは `FALSE` を返します。  
  
## <a name="see-also"></a>参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog クラス](../../mfc/reference/cmfcimageeditordialog-class.md)

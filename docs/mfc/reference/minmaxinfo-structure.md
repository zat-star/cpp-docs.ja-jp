---
title: "MINMAXINFO 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 772416bdac3c72f55644fa31aef23ba76a14e606
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="minmaxinfo-structure"></a>MINMAXINFO 構造体
`MINMAXINFO`構造体には、ウィンドウの最大サイズと位置、および追跡の最小値と最大サイズに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagMINMAXINFO {  
    POINT ptReserved;  
    POINT ptMaxSize;  
    POINT ptMaxPosition;  
    POINT ptMinTrackSize;  
    POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ptReserved*  
 内部使用のために予約されています。  
  
 *ptMaxSize*  
 最大の幅 (point.x) と、ウィンドウの最大の高さ (point.y) を指定します。  
  
 `ptMaxPosition`  
 (Point.x) の最大化ウィンドウの左側の位置と (point.y) の最大化ウィンドウの上端の位置を指定します。  
  
 *ptMinTrackSize*  
 最小のトラッキングの幅 (point.x) と、最小のトラッキング ウィンドウの高さ (point.y) を指定します。  
  
 *ptMaxTrackSize*  
 トラッキングの幅 (point.x) の最大値、およびウィンドウの高さ (point.y) を追跡する最大値を指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)



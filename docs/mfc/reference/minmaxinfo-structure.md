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
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2c799299ef9058648d6b056dcd02fe580f06148
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 最大の幅 (point.x) と、最大化 (point.y) ウィンドウの高さを指定します。  
  
 `ptMaxPosition`  
 最大化されたウィンドウ (point.x) の左側の位置と (point.y) の最大化ウィンドウの上端の位置を指定します。  
  
 *ptMinTrackSize*  
 最小のトラッキングの幅 (point.x) と最小のトラッキング ウィンドウの高さ (point.y) を指定します。  
  
 *ptMaxTrackSize*  
 トラッキングの幅 (point.x) の最大値、およびウィンドウの高さ (point.y) を追跡、最大値を指定します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)


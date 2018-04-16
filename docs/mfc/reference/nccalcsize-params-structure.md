---
title: "NCCALCSIZE_PARAMS 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76a0a16ff0a2c90c6dd6060badc2c79dde1af231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS 構造体
`NCCALCSIZE_PARAMS`構造体には、アプリケーションが処理中に使用できる情報が含まれています、`WM_NCCALCSIZE`サイズ、位置、およびウィンドウのクライアント領域の有効な内容を計算するメッセージ。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rgrc*  
 四角形の配列を指定します。 最初には、移動またはサイズが変更されたウィンドウの新しい座標が含まれています。 2 つ目には、これが移動またはサイズを変更する前に、ウィンドウの座標が含まれています。 3 番目には、これが移動またはサイズを変更する前に、ウィンドウのクライアント領域の座標が含まれています。 子ウィンドウをウィンドウには、座標は、親ウィンドウのクライアント領域と相対的はします。 ウィンドウがトップレベル ウィンドウの場合は、座標は、画面に対して相対的です。  
  
 *lppos*  
 指す、 [WINDOWPOS](../../mfc/reference/windowpos-structure1.md)ウィンドウを移動またはサイズ変更の原因となった操作で指定されたサイズと位置の値を格納する構造体。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)


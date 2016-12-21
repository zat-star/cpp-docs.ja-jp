---
title: "NCCALCSIZE_PARAMS 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NCCALCSIZE_PARAMS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NCCALCSIZE_PARAMS 構造体"
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# NCCALCSIZE_PARAMS 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `NCCALCSIZE_PARAMS` 構造体には、アプリケーションが処理中に使用できる情報が含まれています。、 `WM_NCCALCSIZE` メッセージ サイズ、位置、およびウィンドウのクライアント領域の有効な内容を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
 
    typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rgrc*  
 四角形の配列を指定します。 1 つ目には、移動またはサイズが変更されているウィンドウの新しい座標が含まれています。 2 つ目が移動またはサイズを変更する前に、ウィンドウの座標が含まれています。 3 番目が移動またはサイズを変更する前に、ウィンドウのクライアント領域の座標が含まれています。 ウィンドウが子ウィンドウの場合は、座標は、親ウィンドウのクライアント領域を基準とは。 ウィンドウがトップレベル ウィンドウの場合は、座標は、画面を基準とは。  
  
 *lppos*  
 指す、 [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) 、ウィンドウを移動またはサイズ変更の原因となった操作で指定されたサイズと位置の値を格納する構造体。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../Topic/CWnd%20Class.md#OnNcCalcSize)


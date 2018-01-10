---
title: "PAINTSTRUCT 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PAINTSTRUCT
dev_langs: C++
helpviewer_keywords: PAINTSTRUCT structure [MFC]
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92583bba3dca60caa2895966a87571dc60805475
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="paintstruct-structure"></a>PAINTSTRUCT 構造体
`PAINTSTRUCT`構造体には、ウィンドウのクライアント領域の描画に使用できる情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagPAINTSTRUCT {  
    HDC hdc;  
    BOOL fErase;  
    RECT rcPaint;  
    BOOL fRestore;  
    BOOL fIncUpdate;  
    BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hdc*  
 描画に使用するディスプレイ コンテキストを識別します。  
  
 *fErase*  
 バック グラウンドを再描画する必要があるかどうかを指定します。 アプリケーションは、バック グラウンドを再描画する場合は 0 です。 背景のブラシせずに Windows のウィンドウ クラスを作成する場合に、背景を描画するため、アプリケーションは、(の説明を参照して、 **hbrBackground**のメンバー、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造体windows SDK)。  
  
 *rcPaint*  
 左上隅を指定して、描画が要求された四角形の右下です。  
  
 *fRestore*  
 予約済みのメンバーです。 Windows によって内部的に使用されます。  
  
 *fIncUpdate*  
 予約済みのメンバーです。 Windows によって内部的に使用されます。  
  
 *rgbReserved [16]*  
 予約済みのメンバーです。 Windows によって内部的に使用されるメモリの予約されたブロックします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m_ps](../../mfc/reference/cpaintdc-class.md#m_ps)


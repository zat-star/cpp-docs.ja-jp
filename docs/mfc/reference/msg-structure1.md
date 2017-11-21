---
title: "MSG Structure1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MSG
dev_langs: C++
helpviewer_keywords: MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b856ea17e4542bee68d55b22069e559592199939
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="msg-structure1"></a>MSG Structure1
`MSG`構造体には、スレッドのメッセージ キューからメッセージの情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagMSG {     // msg    
    HWND hwnd;  
    UINT message;  
    WPARAM wParam;  
    LPARAM lParam;  
    DWORD time;  
    POINT pt;  
} MSG;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hwnd*  
 ウィンドウ プロシージャがメッセージを受け取るウィンドウを識別します。  
  
 `message`  
 メッセージ番号を指定します。  
  
 `wParam`  
 メッセージに関する追加情報を指定します。 厳密な意味は、の値によって異なります、**メッセージ**メンバー。  
  
 `lParam`  
 メッセージに関する追加情報を指定します。 厳密な意味は、の値によって異なります、**メッセージ**メンバー。  
  
 `time`  
 メッセージがポストされた時間を指定します。  
  
 `pt`  
 メッセージがポストされたときに、カーソルの位置を画面座標を指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)


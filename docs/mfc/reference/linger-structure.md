---
title: "LINGER 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LINGER
dev_langs: C++
helpviewer_keywords: LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 747a793e64e7f3ec1e76f383a807f15c67417a83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linger-structure"></a>LINGER 構造体
`LINGER`構造が操作に使用される、 **SO_LINGER**と**SO_DONTLINGER**のオプション`CAsyncSocket::GetSockOpt`です。  
  
## <a name="syntax"></a>構文  
  
```  
struct linger {  
    u_short l_onoff;            // option on/off  
    u_short l_linger;           // linger time  
};  
```  
  
## <a name="remarks"></a>コメント  
 設定、 **SO_DONTLINGER**オプションを使用するメンバー関数でのブロッキング**閉じる**未送信のデータを送信するを待っているときにします。 設定は、このオプションを設定**SO_LINGER**で**こと**を 0 に設定します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winsock2.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)   
 [CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)


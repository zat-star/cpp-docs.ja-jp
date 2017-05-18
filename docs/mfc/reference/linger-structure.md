---
title: "LINGER 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LINGER
dev_langs:
- C++
helpviewer_keywords:
- LINGER structure
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: 11
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
ms.openlocfilehash: ed880c29f43c074ba61f52b11f812a79eece0416
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="linger-structure"></a>LINGER 構造体
`LINGER`構造が操作に使用される、 **SO_LINGER**と**SO_DONTLINGER**のオプション`CAsyncSocket::GetSockOpt`します。  
  
## <a name="syntax"></a>構文  
  
```  
struct linger {  
    u_short l_onoff;            // option on/off  
    u_short l_linger;           // linger time  
};  
```  
  
## <a name="remarks"></a>コメント  
 設定、 **SO_DONTLINGER**オプションを使用するメンバー関数でのブロッキング**閉じる**未送信のデータを送信するを待機中にします。 同じことには、このオプションを設定**SO_LINGER**と**こと**を 0 に設定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winsock2.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)   
 [CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)



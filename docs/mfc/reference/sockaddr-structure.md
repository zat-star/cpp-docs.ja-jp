---
title: "SOCKADDR 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SOCKADDR
dev_langs: C++
helpviewer_keywords: SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3ce8207ea1e8f82b635029861493262a5f6237f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="sockaddr-structure"></a>SOCKADDR 構造体
`SOCKADDR` 構造体は Windows Socket 通信に参加するコンピューターのインターネット プロトコル (IP) アドレスを格納するために使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
struct sockaddr {  
    unsigned short sa_family;  
    char sa_data[14];  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *sa_family*  
 ソケット アドレス ファミリ。  
  
 *sa_data*  
 さまざまなソケット アドレス構造体すべてのうち最大のサイズ。  
  
## <a name="remarks"></a>コメント  
 Microsoft TCP/IP Sockets Developer's Kit では、インターネット アドレス ドメインのみをサポートします。 アドレスの各部分の値を実際に入力するために、`SOCKADDR_IN` データ構造体を使用します。この構造体は、このアドレス形式専用です。 `SOCKADDR` と `SOCKADDR_IN` の各データ構造体は同じサイズです。 2 つの構造体の種類の間で切り替えを行うには、単純に割り当てを行います。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winsock2.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR_IN 構造体](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)


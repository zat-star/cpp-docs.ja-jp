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
ms.workload: cplusplus
ms.openlocfilehash: 55b310ec83aae35c7386d61849663752811651d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winsock2.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR_IN 構造体](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)


---
title: "SOCKADDR 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR structure
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 28984fcc5614a5f901a01ffdeff4ea5f360f63fc
ms.lasthandoff: 02/24/2017

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



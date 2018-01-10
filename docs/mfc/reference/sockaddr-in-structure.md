---
title: "SOCKADDR_IN 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SOCKADDR_IN
dev_langs: C++
helpviewer_keywords: SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e5350e48570a564361328e7b666a1cbb976221a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="sockaddrin-structure"></a>SOCKADDR_IN 構造体
インターネット アドレス ファミリでは、ソケットを接続するローカルまたはリモート エンドポイント アドレスを指定するために、Windows ソケットによって `SOCKADDR_IN` の構造体が使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
struct sockaddr_in{  
    short sin_family;  
    unsigned short sin_port;  
struct in_addr sin_addr;  
    char sin_zero[8];  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *これは必須*  
 アドレス ファミリ (する必要があります**AF_INET**)。  
  
 *いった*  
 IP ポート。  
  
 *いった*  
 IP アドレス。  
  
 *sin_zero*  
 `SOCKADDR` と同じサイズに構造体を変更する埋め込み。  
  
## <a name="remarks"></a>コメント  
 これはインターネット アドレス ファミリに特有の `SOCKADDR` 構造体の形態であり、`SOCKADDR` にキャストできます。  
  
 この構造体の IP アドレスのコンポーネントのタイプは**IN_ADDR**です。 **IN_ADDR** Windows ソケットのヘッダー ファイル WINSOCK で構造体を定義します。次のように H:  
  
```  
struct in_addr {
    union {
        struct {  
            unsigned char s_b1, s_b2, s_b3, s_b4;  
        } S_un_b;  
        struct {  
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;  
};  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winsock2.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR 構造体](../../mfc/reference/sockaddr-structure.md)

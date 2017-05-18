---
title: "SOCKADDR_IN 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: 13
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 77ed806bc6afc7ba02663a19a724541bbe0dae42
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

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
  
 この構造体の IP アドレスのコンポーネントのタイプは**IN_ADDR**します。 **IN_ADDR** WINSOCK Windows ソケットのヘッダー ファイルの構造を定義します。次のように H:  
  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winsock2.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR 構造体](../../mfc/reference/sockaddr-structure.md)


---
title: "CSocketAddr クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocketAddr"
  - "ATL.CSocketAddr"
  - "ATL::CSocketAddr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocketAddr クラス"
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSocketAddr クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、ホスト、IPv4 アドレスのサポートと IPV6 形式の両方にホスト名を変換するためのメソッドを提供します。  
  
## 構文  
  
```  
  
class CSocketAddr  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSocketAddr::CSocketAddr](../Topic/CSocketAddr::CSocketAddr.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSocketAddr::FindAddr](../Topic/CSocketAddr::FindAddr.md)|ホスト アドレスに用意されたホスト名を変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::FindINET4Addr](../Topic/CSocketAddr::FindINET4Addr.md)|ホストに IPv4 アドレスのホスト名を変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::FindINET6Addr](../Topic/CSocketAddr::FindINET6Addr.md)|ホストに IPv6 アドレスのホスト名を変換するには、このメソッドを呼び出します。|  
|[CSocketAddr::GetAddrInfo](../Topic/CSocketAddr::GetAddrInfo.md)|**addrinfo** の一覧内の特定の要素へのポインターを返すには、このメソッドを呼び出します。|  
|[CSocketAddr::GetAddrInfoList](../Topic/CSocketAddr::GetAddrInfoList.md)|**addrinfo** リストへのポインターを返すには、このメソッドを呼び出します。|  
  
## 解説  
 このクラスは、ライブラリの Windows ソケット API の関数およびソケット ラッパーを使用をネットワーク アドレスを確認するために、IP のバージョンの柔軟な方法を提供します。  
  
 ネットワーク アドレスを検索するために使用されるこのクラスのメンバーは、Win32 API の関数 [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520)を使用します。  
  
 このクラスは、両方の IPv4 andIPv6 のネットワーク アドレスをサポートします。  
  
## 必要条件  
 **Header:** atlsocket.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)
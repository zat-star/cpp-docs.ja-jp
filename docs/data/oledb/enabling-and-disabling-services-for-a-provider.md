---
title: "有効にして、プロバイダーのサービスを無効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 3deac1bb-f660-407a-92ef-95e139e280c0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dc6b3d7cc8e80eaa24c2e2dd9b4e23e79dfb09f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="enabling-and-disabling-services-for-a-provider"></a>プロバイダーのサービスの有効化と無効化
各 OLE DB サービスを有効になっているまたは 1 つのプロバイダーにアクセスするすべてのアプリケーションに対して既定で無効になっていることができます。 これは、追加することで、 **OLEDB_SERVICES**プロバイダーは、下にレジストリ エントリで、CLSID の`DWORD`次の表に示すように、有効または無効にすると、サービスを指定する値。  
  
|既定のサービスを有効になっています。|キーワードの値|  
|------------------------------|-------------------|  
|すべてのサービス (既定値)|0 xffffffff|  
|以外のすべてのプールと自動確保|0xfffffffe|  
|以外のすべてのクライアント カーソル|0xfffffffb|  
|プールが、自動確保、およびクライアント カーソルを除くすべて|0xfffffff0|  
|サービスはありません。|0x00000000|  
|集約なし、すべてのサービスを無効化|\<キーがありません >|  
  
## <a name="see-also"></a>参照  
 [OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)
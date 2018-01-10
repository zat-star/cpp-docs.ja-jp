---
title: "END_ACCESSOR |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: END_ACCESSOR
dev_langs: C++
helpviewer_keywords: END_ACCESSOR macro
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f0dceb1fe648a67d10fb18b353a5de54fa39caee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="endaccessor"></a>END_ACCESSOR
アクセサーのエントリの終了を示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
END_ACCESSOR( )  
  
```  
  
## <a name="remarks"></a>コメント  
 行セットで複数のアクセサーを指定する必要があります。`BEGIN_ACCESSOR_MAP`を使用して、`BEGIN_ACCESSOR`個々 のアクセサーに対してマクロです。 `BEGIN_ACCESSOR` マクロは `END_ACCESSOR` マクロで終了します。 `BEGIN_ACCESSOR_MAP`マクロが正常に完了しません、`END_ACCESSOR_MAP`マクロです。  
  
## <a name="example"></a>例  
 参照してください[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)
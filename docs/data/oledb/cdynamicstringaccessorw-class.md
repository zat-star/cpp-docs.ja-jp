---
title: "CDynamicStringAccessorW クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDynamicStringAccessorW
dev_langs: C++
helpviewer_keywords: CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 90c97da001d6c8cfb10ddff2a61069adeccc8112
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW クラス
データベース スキーマ (構造体の基になる) の知識があるない場合にデータ ソースにアクセスできます。  
  
## <a name="syntax"></a>構文  
  
```  
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;  
```  
  
## <a name="remarks"></a>コメント  
 どちらも要求プロバイダーが、文字列データとしてデータ ストアからアクセスされるすべてのデータをフェッチするが、 `CDynamicStringAccessor` Unicode 文字列データを要求します。  
  
 `CDynamicStringAccessorW`継承**GetString**と`SetString`から`CDynamicStringAccessor`です。 これらのメソッドを使用すると、`CDynamicStringAccessorW`オブジェクト、 ***BaseType***は**WCHAR**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー**: atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor クラス](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)
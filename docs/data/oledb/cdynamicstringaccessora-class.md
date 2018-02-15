---
title: "CDynamicStringAccessorA クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0514dd3cd87788a6512b18d0aa3f2a5b7a842317
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA クラス
データベース スキーマ (構造体の基になる) の知識があるない場合にデータ ソースにアクセスできます。  
  
## <a name="syntax"></a>構文

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>コメント  
 どちらも要求プロバイダーが、文字列データとしてデータ ストアからアクセスされるすべてのデータをフェッチするが、`CDynamicStringAccessor`要求 ANSI 文字列データです。  
  
 `CDynamicStringAccessorA` 継承**GetString**と`SetString`から`CDynamicStringAccessor`です。 これらのメソッドを使用すると、`CDynamicStringAccessorA`オブジェクト、 ***BaseType***は**CHAR**です。  
  
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
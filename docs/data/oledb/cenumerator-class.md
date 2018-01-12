---
title: "CEnumerator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CEnumerator
dev_langs: C++
helpviewer_keywords: CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a64ac02e7b16bfab70966ffaf2a1897ae955f8c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cenumerator-class"></a>CEnumerator クラス
公開する OLE DB 列挙子オブジェクトを使用して、 [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx)インターフェイスをすべてのデータ ソースと列挙子を記述する行セットを返します。  
  
## <a name="syntax"></a>構文  
  
```  
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[検索](../../data/oledb/cenumerator-find.md)|指定した名前のいずれかを探して使用可能なプロバイダー (データ ソース) で検索します。|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|取得、`IMoniker`現在のレコードのインターフェイスです。|  
|[開く](../../data/oledb/cenumerator-open.md)|列挙子を開きます。|  
  
## <a name="remarks"></a>コメント  
 取得することができます、 **ISourcesRowset**このクラスから間接的にデータ。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:**atldbcli.h  
  
## <a name="see-also"></a>参照  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
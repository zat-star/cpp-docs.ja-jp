---
title: "CSession クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
dev_langs: C++
helpviewer_keywords: CSession class
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d8b6bb75d12b4ab96c3a44c74f4487eb8a70efc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="csession-class"></a>CSession クラス
1 つのデータベース アクセスのセッションを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSession  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[中止](../../data/oledb/csession-abort.md)|キャンセル (終了) トランザクション。|  
|[閉じる](../../data/oledb/csession-close.md)|セッションを閉じます。|  
|[コミット](../../data/oledb/csession-commit.md)|トランザクションをコミットします。|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|トランザクションに関する情報を返します。|  
|[開く](../../data/oledb/csession-open.md)|データ ソース オブジェクトの新しいセッションを開きます。|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|このセッション用の新しいトランザクションを開始します。|  
  
## <a name="remarks"></a>コメント  
 各プロバイダー接続 (データ ソース) で表される 1 つまたは複数のセッションを関連付けることができます、 [CDataSource](../../data/oledb/cdatasource-class.md)オブジェクト。 新しい`CSession`の`CDataSource`、呼び出す[csession::open](../../data/oledb/csession-open.md)です。 データベース トランザクションを開始する`CSession`提供、`StartTransaction`メソッドです。 トランザクションが開始されるを使用してコミットすることができます、**コミット**メソッド、またはキャンセルを使用して、**中止**メソッドです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CatDB](../../visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
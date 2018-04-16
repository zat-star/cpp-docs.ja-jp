---
title: "CDataConnection クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2c8e405b95543d170a4e94e39626e9b9793791c7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnection-class"></a>CDataConnection クラス
データ ソースとの接続を管理します。  
  
## <a name="syntax"></a>構文

```cpp
class CDataConnection  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|コンストラクターです。 インスタンスを作成し、初期化、`CDataConnection`オブジェクト。|  
|[コピー](../../data/oledb/cdataconnection-copy.md)|既存のデータ接続のコピーを作成します。|  
|[開く](../../data/oledb/cdataconnection-open.md)|初期化文字列を使用してデータ ソースへの接続を開きます。|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|現在の接続で新しいセッションを開きます。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator BOOL](../../data/oledb/cdataconnection-operator-bool.md)|か、現在のセッションが開いているかどうかを判断します。|  
|[operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|か、現在のセッションが開いているかどうかを判断します。|  
|[CDataSource 演算子 (& a)](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|格納されている参照を返します`CDataSource`オブジェクト。|  
|[operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)|格納されているポインターを返します`CDataSource`オブジェクト。|  
|[演算子 CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)|格納されている参照を返します`CSession`オブジェクト。|  
|[演算子 CSession *](../../data/oledb/cdataconnection-operator-csession-star.md)|格納されているポインターを返します`CSession`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CDataConnection` クラスは、必要なオブジェクト (データ ソースとセッション) とデータ ソースに接続する場合に行う必要がある作業の一部をカプセル化するためにクライアントを作成するには  
  
 せず`CDataConnection`、作成する必要が、`CDataSource`オブジェクトを呼び出すその[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)メソッドのインスタンスを作成、 [CSession](../../data/oledb/csession-class.md)オブジェクトを呼び出してその[開いている](../../data/oledb/csession-open.md)メソッド、作成し、 [CCommand](../../data/oledb/ccommand-class.md)オブジェクトと呼び出しその**開く*** メソッドです。  
  
 `CDataConnection`、のみ、接続オブジェクトを作成し、初期化文字列を渡す、コマンドを開く、その接続を使用する必要があります。 接続を開き、維持することをお勧めは、データベースへの接続を繰り返し使用する場合と`CDataConnection`を行うには便利な方法を提供します。  
  
> [!NOTE]
>  複数のセッションを処理する必要があるデータベース アプリケーションを作成する場合は、使用する必要があります[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
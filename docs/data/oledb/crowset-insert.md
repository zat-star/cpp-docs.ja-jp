---
title: "Crowset::insert |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.Insert
- CRowset.Insert
- CRowset<TAccessor>.Insert
- CRowset<TAccessor>::Insert
- ATL::CRowset<TAccessor>::Insert
- ATL.CRowset.Insert
- CRowset::Insert
- ATL::CRowset::Insert
dev_langs: C++
helpviewer_keywords: Insert method
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75dfe26fa04f8e639b3d391a9dc703a9a98c70c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetinsert"></a>CRowset::Insert
作成して、データ アクセサーを使用して新しい行を初期化します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT Insert(   
   int nAccessor = 0,   
   bool bGetHRow = false    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nAccessor`  
 [in]データを挿入するために使用するアクセサーの数。  
  
 *bGetHRow*  
 [in]挿入された行のハンドルを取得するかどうかを示します。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetChange`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetChange**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
 挿入は、1 つまたは複数の列が書き込み可能な場合に失敗する可能性があります。 これを修正するにはカーソル マップを変更します。  
  
## <a name="example"></a>例  
 次の例では、行セットからデータ ソースにアクセスし、その行セットのテーブルを使用して文字列を挿入する方法を示します。  
  
 最初に、プロジェクトに新しい ATL オブジェクトを挿入することでテーブル クラスを作成します。 たとえば、ワークスペース] ウィンドウで、プロジェクトを右クリックし [ **ATL オブジェクトの新しい**です。 **データ アクセス**カテゴリで、**コンシューマー**です。 型のコンシューマー オブジェクトを作成する**テーブル**です。 (選択**テーブル**テーブルから直接、行セットを作成 を選択すると;**コマンド**SQL コマンドを使って行セットを作成します)。そのデータ ソースへのアクセスに使用するテーブルを指定して、データ ソースを選択します。 コンシューマー オブジェクトを呼び出せる場合**CCustomerTable**、挿入コードを次のように、実装は。  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/cpp/crowset-insert_1.cpp)]  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CRowset クラス](../../data/oledb/crowset-class.md)
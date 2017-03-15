---
title: "CRowset::Insert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>.Insert"
  - "CRowset.Insert"
  - "CRowset<TAccessor>.Insert"
  - "CRowset<TAccessor>::Insert"
  - "ATL::CRowset<TAccessor>::Insert"
  - "ATL.CRowset.Insert"
  - "CRowset::Insert"
  - "ATL::CRowset::Insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Insert メソッド"
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::Insert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アクセサーのデータを使用して新しい行を作成し、初期化します。  
  
## 構文  
  
```  
  
      HRESULT Insert(   
   int nAccessor = 0,   
   bool bGetHRow = false    
) throw( );  
```  
  
#### パラメーター  
 `nAccessor`  
 \[\]データを挿入するために使用するアクセサーの数。  
  
 *bGetHRow*  
 \[\]挿入された行のハンドルが取得されるかどうかを示します。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは、すべてのプロバイダーでサポートされない省略可能なインターフェイス `IRowsetChange`が必要ですが、; この場合、メソッドの戻り **E\_NOINTERFACE**。  また `VARIANT_TRUE` にテーブルの **開く** を呼び出す前に **DBPROP\_IRowsetChange** を設定または命じなければ、行セットが含まれます。  
  
 Insert は一つ以上の列が書き込み可能でない場合に失敗する場合があります。  これを修正するにはカーソル マップを変更します。  
  
## 使用例  
 次の例では、行セット内のデータ ソースに行セットにアクセスし、テーブルを使用して文字列を挿入する方法を示しています。  
  
 まず、新しいプロジェクトに ATL オブジェクトを挿入することによって、テーブルのクラスを作成します。  たとえば、ワークスペースのペインで、プロジェクトを右クリックし、**New ATL Object**を選択します。  **データ アクセス** のカテゴリで、**コンシューマ**を選択します。  型 **テーブル**コンシューマー オブジェクトを作成します。\(**テーブル** を選択すると、テーブルの行セットを直接作成します; **コマンド** を選択することは、SQL コマンドによって行セットを作成します。データ ソースにアクセスするために指定したデータ ソースが、テーブルを選択します。  Consumer オブジェクト **CCustomerTable**を呼び出すと、次のように挿入コードを実装します:  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/CPP/crowset-insert_1.cpp)]  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CRowset クラス](../Topic/CRowset%20Class.md)
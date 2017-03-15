---
title: "レコードセット: クエリの再実行 (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC レコードセット, 再クエリ"
  - "レコードセット, 再クエリ"
  - "更新 (レコードセットの)"
  - "Requery メソッド"
  - "再クエリ (レコードセットを)"
ms.assetid: 4ebc3b5b-5b91-4f51-a967-245223c6b8e1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコードセット: クエリの再実行 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、[Requery](../Topic/CRecordset::Requery.md) メンバー関数を使用してデータベースに対するクエリを再実行する \(レコードセットを再表示する\) 方法について説明します。  
  
 通常、以下の場合にレコードセットのクエリを再実行します。  
  
-   自分またはほかのユーザーが追加したレコード、またはほかのユーザーが削除したレコードをレコードセットに反映させる場合。自分が削除したレコードは既にレコードセットから取り除かれています。  
  
-   パラメーター値を変更したときに、レコードセットを最新表示する場合。  
  
##  <a name="_core_bringing_the_recordset_up_to_date"></a> データ ソースの最新の状態のレコードセットへの反映  
 通常、クエリの再実行が必要になるのは、データ ソースの最新状態をレコードセットに反映させる場合です。  マルチユーザー データベース環境では、レコードセットの存続中にほかのユーザーがデータを変更することがあります。  他のユーザーによる変更をレコードセットに反映するしくみについては、「[レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」と「[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。  
  
##  <a name="_core_requerying_based_on_new_parameters"></a> 新しいパラメーター値に基づくクエリの再実行  
 パラメーター値を変更して新しいレコードを選択する場合も、[Requery](../Topic/CRecordset::Requery.md) を使用します。  
  
> [!TIP]
>  **Open** を再度呼び出す場合よりもパラメーター値を変更して **Requery** を呼び出す場合の方が、クエリの処理速度が上がる場合があります。  
  
##  <a name="_core_requerying_dynasets_vs.._snapshots"></a> ダイナセットとスナップショットの再実行  
 ダイナセットは、レコードの最新のデータを動的に表示するための手段なので、クエリを頻繁に再実行して、他のユーザーによる追加を反映させる必要があります。  これに対して、スナップショットの内容は、データの表示や集計計算などを安定して行うことができるように固定されています。  ただし、スナップショットでもクエリの再実行が必要な場合があります。  マルチユーザー環境では、他のユーザーによるデータベースの変更がスナップショット データに反映されないからです。  
  
#### レコードセット オブジェクトのクエリを再実行するには  
  
1.  オブジェクトのメンバー関数 [Requery](../Topic/CRecordset::Requery.md) を呼び出します。  
  
 レコードセットをいったん閉じてから再び開いても、Requery と同じ結果になります。  どちらの場合も、新しいレコードセットにはデータ ソースの最新の状態が反映されています。  
  
 例については、「[セカンド レコードセットを利用してリスト ボックスを表示する方法](../../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)」を参照してください。  
  
> [!TIP]
>  **Requery** のパフォーマンスを最適化するには、レコードセットの[フィルター](../../data/odbc/recordset-filtering-records-odbc.md)や[並べ替え](../../data/odbc/recordset-sorting-records-odbc.md)を変更しないようにします。  **Requery** を呼び出す前に、パラメーターの値だけを変更します。  
  
 **Requery** の呼び出しに失敗した場合は、呼び出しを再試行します。それ以外の場合は、適切な方法でアプリケーションを終了します。  **Requery** または **Open** の呼び出しは、さまざまな理由から失敗することがあります。  たとえば、ネットワーク エラーが発生した、既存のデータが破棄されてから新しいデータが得られるまでの間にほかのユーザーが排他的なアクセスを行った、レコードセットが結び付けられているテーブルが削除された、というような理由が考えられます。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: データ列を動的に結びつける方法 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [レコードセット: レコードセットの生成と破棄 \(ODBC\)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)
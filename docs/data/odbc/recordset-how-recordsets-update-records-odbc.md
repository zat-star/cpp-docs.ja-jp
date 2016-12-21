---
title: "レコードセット: レコード更新のしくみ (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC レコードセット, 更新"
  - "レコード, 更新"
  - "レコードセット, 編集 (レコードを)"
  - "レコードセット, 更新"
  - "更新 (レコードセットを)"
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコードセット: レコード更新のしくみ (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 レコードセットでは、データ ソースからレコードを選択するほか、レコードを更新、削除、追加することもできます。  レコードセットを更新できるかどうかは、データ ソースが更新可能かどうか、レコードセット オブジェクトを生成したときの設定内容、および生成した SQL の内容の 3 点によって決定されます。  
  
> [!NOTE]
>  `CRecordset` オブジェクトの SQL は、レコードセットを更新できるかどうかに影響します。  SQL が結合または **GROUP BY** 句を含んでいる場合は、MFC は更新可能性を **FALSE** に設定します。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。  バルク行フェッチを使用する場合は、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 このトピックでは、次の内容について説明します。  
  
-   [レコードセットを更新するために必要な操作](#_core_your_role_in_recordset_updating)とフレームワークの動作  
  
-   [レコードセットが編集バッファーとして機能するしくみ](#_core_the_edit_buffer)と、[ダイナセットとスナップショットの違い](#_core_dynasets_and_snapshots)  
  
 「[レコードセット : AddNew、Edit、Delete の動作のしくみ \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)」では、レコードセットから見た各関数の動作について説明します。  
  
 「[レコードセット : 更新処理の詳細 \(ODBC\)](../../data/odbc/recordset-more-about-updates-odbc.md)」では、レコードセットの更新に関して詳しく説明しています。内容は、トランザクションが更新に及ぼす影響、レコードセットを閉じたときまたはスクロールしたときの現在処理中の更新に及ぼす影響、自分の更新処理と他のユーザーによる更新処理の関係などです。  
  
##  <a name="_core_your_role_in_recordset_updating"></a> レコードセット更新に必要な操作  
 レコードセットを使ってレコードの追加、編集、削除を行うために必要な操作と、それに対するフレームワークの動作を次の表に示します。  
  
### 必要な操作とフレームワークの動作  
  
|プログラマの役割|フレームワークの役割|  
|--------------|----------------|  
|データ ソースが更新可能 \(または追加可能\) かどうかを確認します。|データ ソースの更新または追加の可能性を調べる [CDatabase](../../mfc/reference/cdatabase-class.md) メンバー関数を提供します。|  
|更新可能なレコードセットを開きます。||  
|レコードセットが `CRecordset` 更新関数 \(`CanUpdate` または `CanAppend`\) の呼び出しで更新可能かどうかを調べます。||  
|レコードセットのメンバー関数を呼び出してレコードの追加、編集、削除を行います。|レコードセット オブジェクトとデータ ソースとの間のデータ交換を管理します。|  
|必要ならば、トランザクションで更新処理を制御します。|トランザクションを行うためのメンバー関数 `CDatabase` を提供します。|  
  
 トランザクションの詳細については、「[トランザクション \(ODBC\)](../../data/odbc/transaction-odbc.md)」を参照してください。  
  
##  <a name="_core_the_edit_buffer"></a> エディット バッファー  
 レコードセットのフィールド データ メンバーは、全体でエディット バッファーを構成します。エディット バッファーには、現在のレコードの内容が保存されます。  レコードの更新処理では、このエディット バッファーを使って現在のレコードを操作します。  
  
-   レコードを追加するときは、エディット バッファーを使って新しいレコードを作成します。  レコードの追加が終了すると、レコードを追加する前に現在のレコードであったレコードが再び現在のレコードになります。  
  
-   レコードを更新 \(編集\) するときは、エディット バッファーを使ってレコードセットのフィールド データ メンバーに新しい値を設定します。  更新が終了すると、更新したレコードがそのまま現在のレコードになります。  
  
 [AddNew](../Topic/CRecordset::AddNew.md) または [Edit](../Topic/CRecordset::Edit.md) を呼び出すと、後で復元できるように現在のレコードが待避されます。  [Delete](../Topic/CRecordset::Delete.md) を呼び出すと、現在のレコードは待避されず、削除したことを示す印が付けられます。また、この場合は、別のレコードにスクロールする必要があります。  
  
> [!NOTE]
>  レコードを削除する場合、エディット バッファーは使用されません。  現在のレコードを削除すると、レコードに削除したことを示す印が付けられます。別のレコードに移動 \(スクロール\) するまでは、レコードセットはどのレコードも示していません。  
  
##  <a name="_core_dynasets_and_snapshots"></a> ダイナセットとスナップショット  
 [ダイナセット](../../data/odbc/dynaset.md)では、レコードをスクロールすると、レコードの内容が最新表示されます。  [スナップショット](../Topic/Snapshot.md)は、静的なレコードの状態なので、[Requery](../Topic/CRecordset::Requery.md) を呼び出さない限り再表示されません。  ダイナセットの全機能を利用するには、ODBC API 準拠レベルが合致した ODBC ドライバーを使う必要があります。  詳細については、「[ODBC の基礎](../../data/odbc/odbc-basics.md)」と「[ダイナセット](../../data/odbc/dynaset.md)」を参照してください。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: AddNew、Edit、Delete の動作のしくみ \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)
---
title: "レコードセット: レコードの追加、更新、削除 (ODBC) | Microsoft Docs"
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
  - "AddNew メソッド"
  - "データ (レコードセットの) [C++]"
  - "ODBC レコードセット [C++], 追加 (レコードを)"
  - "ODBC レコードセット [C++], 削除 (レコードを)"
  - "ODBC レコードセット [C++], 編集 (レコードを)"
  - "レコード編集 [C++]"
  - "レコード編集 [C++], レコードセットで"
  - "レコード [C++], 追加"
  - "レコード [C++], 削除"
  - "レコード [C++], 編集"
  - "レコード [C++], 更新"
  - "レコードセット [C++], 追加 (レコードを)"
  - "レコードセット [C++], 削除 (レコードを)"
  - "レコードセット [C++], 編集 (レコードを)"
  - "レコードセット [C++], 更新"
ms.assetid: 760c8889-bec4-482b-a8f2-319792a6af98
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# レコードセット: レコードの追加、更新、削除 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
> [!NOTE]
>  大量のレコードをより効率的に追加する方法もあります。  詳細については、「[レコードセット : レコードを大量に追加する方法 \(ODBC\)](../../data/odbc/recordset-adding-records-in-bulk-odbc.md)」を参照してください。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。  バルク行フェッチを使用する場合は、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 更新できるスナップショットとダイナセットでは、レコードを追加、編集 \(更新\)、削除できます。  このトピックでは、次の内容について説明します。  
  
-   [レコードセットが更新可能かどうかを調べる方法](#_core_determining_whether_your_recordset_is_updatable)  
  
-   [新しいレコードを追加する方法](#_core_adding_a_record_to_a_recordset)  
  
-   [既存のレコードを編集する方法](#_core_editing_a_record_in_a_recordset)  
  
-   [レコードを削除する方法](#_core_deleting_a_record_from_a_recordset)  
  
 更新が行われるしくみや更新結果が他のユーザーに及ぼす影響の詳細については、「[レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。  通常は、レコードを追加、編集、または削除すると、すぐにレコードセットによってデータ ソースが更新されます。  また、一連の更新処理をトランザクションにまとめることもできます。  トランザクションを開始すると、そのトランザクションをコミットするまで、更新処理は終了しません。  したがって、更新をやり直すことができます。  トランザクションについては、「[トランザクション \(ODBC\)](../../data/odbc/transaction-odbc.md)」を参照してください。  
  
 レコードセットの更新方法と更新設定の関係を次の表に示します。  
  
### レコードセットの読み出し\/更新用の選択肢  
  
|型|Read|レコードの編集|レコードの削除|新規作成 \(追加\)|  
|-------|----------|-------------|-------------|-----------------|  
|読み取り専用|Y|N|N|N|  
|追加のみ可能 \(Append\-only\)|Y|N|N|Y|  
|すべて更新可能|Y|Y|Y|Y|  
  
##  <a name="_core_determining_whether_your_recordset_is_updatable"></a> レコードセットの更新可能性を調べる方法  
 レコードセット オブジェクトは、データ ソースが更新可能であり、レコードセットが更新できるという設定で開かれている場合に更新できます。  また、使用する SQL ステートメント、ODBC ドライバーの機能、ODBC カーソル ライブラリがメモリ内にあるかどうかなどに応じて更新できるかどうかが決まります。  レコードセットかデータ ソースが読み取り専用のときは、更新できません。  
  
#### レコードセットが更新可能かどうかを調べるには  
  
1.  レコードセット オブジェクトのメンバー関数 [CanUpdate](../Topic/CRecordset::CanUpdate.md) を呼び出します。  
  
     `CanUpdate` は、レコードセットが更新可能なときは 0 以外の値を返します。  
  
 既定では、レコードセットはすべて更新可能です \(`AddNew`、**Edit**、**Delete** をすべて使用できます\)。  更新可能なレコードセットは、[appendOnly](../Topic/CRecordset::Open.md) オプションを指定して開くこともできます。  この方法で開いたレコードセットでは、`AddNew` を使用して新しいレコードを追加することだけができます。  既存のレコードを編集または削除することはできません。  [CanAppend](../Topic/CRecordset::CanAppend.md) メンバー関数を呼び出して、レコードセットが追加のためだけに開かれているかどうかを確認できます。  レコードセットがすべて更新できる場合、または追加のためだけに開かれている場合は、`CanAppend` が 0 以外の値を返します。  
  
 次の例では、レコードセット オブジェクト `rsStudentSet` に対して `CanUpdate` を使用しています。  
  
```  
if( !rsStudentSet.Open( ) )  
    return FALSE;  
if( !rsStudentSet.CanUpdate( ) )  
{  
    AfxMessageBox( "Unable to update the Student recordset." );  
    return;  
}  
```  
  
> [!CAUTION]
>  **Update** を呼び出してレコードセットを更新する前に、テーブルの主キーを構成するすべての列 \(または、テーブルで一意のインデックスを構成するすべての列\) がレコードセットに含まれていることに注意してください。  場合によっては、フレームワークは、レコードセット内で選択されている列だけに基づいてテーブル内の更新するレコードを特定します。  選択されている列数が不足していると、テーブル内の複数のレコードが更新されることがあり、場合によっては、テーブルの参照整合性が損なわれます。  この場合は、**Update** を呼び出した結果として例外がスローされます。  
  
##  <a name="_core_adding_a_record_to_a_recordset"></a> レコードセットへのレコードの新規追加  
 メンバー関数 [CanAppend](../Topic/CRecordset::CanAppend.md) が 0 以外の値を返したときは、レコードセットに新しいレコードを追加できます。  
  
#### 新しいレコードをレコードセットに追加するには  
  
1.  レコードセットがレコード追加可能レコードセットであることを確認します。  
  
2.  レコードセット オブジェクトのメンバー関数 [AddNew](../Topic/CRecordset::AddNew.md) を呼び出します。  
  
     `AddNew` は、レコードセットをエディット バッファーとして利用できるようにします。  すべてのフィールド データ メンバーは特殊な Null 値に設定され、未変更の印が付けられます。そのため、[Update](../Topic/CRecordset::Update.md) を呼び出すと、変更された値だけがデータ ソースに書き出されます。  
  
3.  新しいレコードのフィールド データ メンバーの値を設定します。  
  
     フィールド データ メンバーに値を代入します。  代入しなかったフィールドはデータ ソースに書き出されません。  
  
4.  レコードセット オブジェクトのメンバー関数 **Update** を呼び出します。  
  
     **Update** は、新しいレコードをデータ ソースに実際に書き出します。  **Update** の呼び出しに失敗したときの処理方法については、「[レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。  
  
 レコードを追加するしくみ、および追加したレコードがレコードセット内に表示される時期については、「[レコードセット : AddNew、Edit、Delete の動作のしくみ \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)」を参照してください。  
  
 次に、新しいレコードを追加する例を示します。  
  
```  
if( !rsStudent.Open( ) )  
    return FALSE;  
if( !rsStudent.CanAppend( ) )  
    return FALSE;                      // no field values were set  
rsStudent.AddNew( );  
rsStudent.m_strName = strName;  
rsStudent.m_strCity = strCity;  
rsStudent.m_strStreet = strStreet;  
if( !rsStudent.Update( ) )  
{  
    AfxMessageBox( "Record not added; no field values were set." );  
    return FALSE;  
}  
```  
  
> [!TIP]
>  `AddNew` または **Edit** の呼び出しを取り消すには、もう 1 回 `AddNew` または **Edit** を呼び出すか、**AFX\_MOVE\_REFRESH** パラメーターを指定して **Move** を呼び出します。  データ メンバーは前回の値にリセットされ、**Edit** モードまたは **Add** モードが継続します。  
  
##  <a name="_core_editing_a_record_in_a_recordset"></a> レコードセットの既存のレコードの編集  
 メンバー関数 [CanUpdate](../Topic/CRecordset::CanUpdate.md) が 0 以外の値を返したときは、レコードセットの既存のレコードを編集できます。  
  
#### レコードセット内の既存のレコードを編集するには  
  
1.  レコードセットが更新可能であることを確認します。  
  
2.  更新するレコードに移動 \(スクロール\) します。  
  
3.  レコードセット オブジェクトのメンバー関数 [Edit](../Topic/CRecordset::Edit.md) を呼び出します。  
  
     **Edit** は、レコードセットをエディット バッファーとして利用できるようにします。  すべてのフィールド データ メンバーに未変更の印が付けられます。  [Update](../Topic/CRecordset::Update.md) を呼び出すと、変更されたフィールド データ メンバーの値だけをデータ ソースに書き出します。  
  
4.  新しいレコードのフィールド データ メンバーの値を設定します。  
  
     フィールド データ メンバーに値を代入します。  値を代入しなかったフィールドには変更前の値が残ります。  
  
5.  レコードセット オブジェクトのメンバー関数 **Update** を呼び出します。  
  
     **Update** は、変更されたレコードをデータ ソースに実際に書き出します。  **Update** の呼び出しに失敗したときの処理方法については、「[レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。  
  
 編集終了後は、編集されたレコードが現在のレコードになります。  
  
 次に、**Edit** 処理の例を示します。  ここでは、編集するレコードに既に移動しているものと想定しています。  
  
```  
rsStudent.Edit( );  
rsStudent.m_strStreet = strNewStreet;  
rsStudent.m_strCity = strNewCity;  
rsStudent.m_strState = strNewState;  
rsStudent.m_strPostalCode = strNewPostalCode;  
if( !rsStudent.Update( ) )  
{  
    AfxMessageBox( "Record not updated; no field values were set." );  
    return FALSE;  
}  
```  
  
> [!TIP]
>  `AddNew` または **Edit** の呼び出しを取り消すには、もう 1 回 `AddNew` または **Edit** を呼び出すか、**AFX\_MOVE\_REFRESH** パラメーターを指定して **Move** を呼び出します。  データ メンバーは前回の値にリセットされ、**Edit** モードまたは **Add** モードが継続します。  
  
##  <a name="_core_deleting_a_record_from_a_recordset"></a> レコードセットのレコードの削除  
 メンバー関数 [CanUpdate](../Topic/CRecordset::CanUpdate.md) が 0 以外の値を返したときは、レコードセットのレコードを削除できます。  
  
#### レコードを削除するには  
  
1.  レコードセットが更新可能であることを確認します。  
  
2.  更新するレコードに移動 \(スクロール\) します。  
  
3.  レコードセット オブジェクトのメンバー関数 [Delete](../Topic/CRecordset::Delete.md) を呼び出します。  
  
     **Delete** は、すぐにレコードセット内とデータ ソース上のレコードに削除の印を付けます。  
  
     `AddNew` および **Edit** とは異なり、**Delete** には **Update** 呼び出しはありません。  
  
4.  別のレコードに移動 \(スクロール\) します。  
  
    > [!NOTE]
    >  レコードセット内を移動する場合、削除したレコードがスキップされないことがあります。  詳細については、[IsDeleted](../Topic/CRecordset::IsDeleted.md) メンバー関数に関するトピックを参照してください。  
  
 次に、**Delete** 処理の例を示します。  ここでは、削除するレコードに既に移動しているものと想定しています。  **Delete** の呼び出し終了後は、必ず別のレコードに移動してください。  
  
```  
rsStudent.Delete( );  
rsStudent.MoveNext( );  
```  
  
 `AddNew`、**Edit**、および **Delete** の各メンバー関数の動作の詳細については、「[レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」を参照してください。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: レコードのロック \(ODBC\)](../../data/odbc/recordset-locking-records-odbc.md)
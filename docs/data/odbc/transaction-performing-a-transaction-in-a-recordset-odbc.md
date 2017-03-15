---
title: "トランザクション: レコードセットからのトランザクション実行 (ODBC) | Microsoft Docs"
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
  - "トランザクション, 更新 (レコードセットを)"
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# トランザクション: レコードセットからのトランザクション実行 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、レコードセット内でトランザクションを実行する方法について説明します。  
  
> [!NOTE]
>  トランザクションは 1 レベルでしか利用できません。つまり、入れ子にすることはできません。  
  
#### レコードセット中でトランザクションを実行するには  
  
1.  `CDatabase` オブジェクトのメンバー関数 **BeginTrans** を呼び出します。  
  
2.  バルク行フェッチを実装していない場合は、同一のデータベースに結び付けられた 1 つ以上のレコードセットの中で、メンバー関数 **AddNew\/Update**、**Edit\/Update**、および **Delete** を必要な回数だけ呼び出してレコードを更新します。  詳細については、「[レコードセット : レコードの追加、更新、削除 \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)」を参照してください。  バルク行フェッチを実装している場合は、データ ソースを更新するための関数を独自に記述する必要があります。  
  
3.  最後に `CDatabase` オブジェクトのメンバー関数 **CommitTrans** を呼び出します。  更新処理中にエラーが発生した場合、または変更をキャンセルする場合は、**Rollback** メンバー関数を呼び出します。  
  
 次の例では、2 つのレコードセットを使って、1 人の学生の履修登録を登録データベースから削除します。つまり、学生が履修登録したすべてのクラスからこの学生の登録を削除します。  両方のレコードセットで **Delete** の呼び出しを連続して実行する必要があるので、トランザクションが必要です。  この例は、`CDatabase` 型のメンバー変数 `m_dbStudentReg` が存在し、既にデータ ソースに接続されており、レコードセット クラス `CEnrollmentSet` と `CStudentSet` が存在することを想定しています。  変数 `strStudentID` には、ユーザーが指定した値が格納されています。  
  
```  
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )  
{  
    // remove student from all the classes  
    // the student is enrolled in  
  
    if ( !m_dbStudentReg.BeginTrans( ) )  
        return FALSE;  
  
    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);  
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    CStudentSet rsStudentSet(&m_dbStudentReg);  
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsStudentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    TRY  
    {  
        while ( !rsEnrollmentSet.IsEOF( ) )  
        {  
            rsEnrollmentSet.Delete( );  
            rsEnrollmentSet.MoveNext( );  
        }  
  
        // delete the student record  
        rsStudentSet.Delete( );  
  
        m_dbStudentReg.CommitTrans( );  
    }  
  
    CATCH_ALL(e)  
    {  
        m_dbStudentReg.Rollback( );  
        return FALSE;  
    }  
    END_CATCH_ALL  
  
    rsEnrollmentSet.Close( );  
    rsStudentSet.Close( );  
  
    return TRUE;  
  
}  
```  
  
> [!NOTE]
>  **CommitTrans** または **Rollback** を呼び出さずに **BeginTrans** を再度呼び出すと、エラーが発生します。  
  
## 参照  
 [トランザクション \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [トランザクション: トランザクションが更新処理に与える影響 \(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)
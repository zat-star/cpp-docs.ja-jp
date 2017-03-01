---
title: "データベースのマクロとグローバル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- global database functions [C++]
- database macros [C++]
- database globals [C++]
- global functions [C++], database functions
- macros [C++], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 9706c47d9bd5996c28873da6a15a687bf9b5e038
ms.lasthandoff: 02/24/2017

---
# <a name="database-macros-and-globals"></a>データベース マクロとデータベース グローバル関数
マクロとグローバル変数を次に示す ODBC ベースのデータベース アプリケーションに適用されます。 DAO ベースのアプリケーションでは使用されません。  
  
 MFC 4.2 は、マクロの前に`AFX_SQL_ASYNC`と`AFX_SQL_SYNC`の非同期操作を他のプロセスに時間を得ることができました。 MFC 4.2 は、これらのマクロ、MFC ODBC クラスには同期操作のみが使用されるため、変更の実装を開始します。 マクロ`AFX_ODBC_CALL`MFC 4.2 を新たに導入されました。  
  
### <a name="database-macros"></a>データベースのマクロ  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|ODBC API 関数を表すオブジェクトを呼び出す`SQL_STILL_EXECUTING`します。 `AFX_ODBC_CALL`繰り返し関数を呼び出すまで、不要になったを返します。`SQL_STILL_EXECUTING`します。|  
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|  
|[AFX_SQL_SYNC](#afx_sql_sync)|返さない ODBC API 関数を呼び出す`SQL_STILL_EXECUTING`します。|  
  
### <a name="database-globals"></a>データベースのグローバル関数  
  
|||  
|-|-|  
|[AfxGetHENV](#afxgethenv)|MFC で使用されている ODBC 環境ハンドルを取得します。 このハンドルは、ODBC の直接の呼び出しで使用できます。|  
  
##  <a name="a-nameafxodbccalla--afxodbccall"></a><a name="afx_odbc_call"></a>AFX_ODBC_CALL  
 返す可能性のある任意の ODBC API 関数を呼び出すこのマクロを使用して`SQL_STILL_EXECUTING`します。  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>パラメーター  
 `SQLFunc`  
 ODBC API 関数の場合。 ODBC API 関数の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 `AFX_ODBC_CALL`繰り返しの関数を呼び出すまで不要になった返します`SQL_STILL_EXECUTING`します。  
  
 呼び出す前に`AFX_ODBC_CALL`、変数を宣言する必要があります`nRetCode`、型の**へ**します。  
  
 MFC ODBC クラスの唯一の同期処理を今すぐ使用ことに注意してください。 非同期操作を実行するのには、ODBC API 関数を呼び出す必要があります**SQLSetConnectOption**します。 詳細については、「関数の非同期実行」のトピックを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  

  
### <a name="example"></a>例  
 この例では`AFX_ODBC_CALL`を呼び出して、 **SQLColumns**によってという名前のテーブルで列の一覧を返す ODBC API 関数`strTableName`します。 宣言することに注意してください`nRetCode`と関数にパラメーターを渡すレコード セットのデータ メンバーを使用します。 呼び出しの結果を確認して、例にも示す**チェック**、クラスのメンバー関数`CRecordset`します。 変数`prs`へのポインター、`CRecordset`他の場所で宣言されたオブジェクト。  
  
 [!code-cpp[NVC_MFCDatabase&#39;](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

##  <a name="a-nameafxsqlasynca--afxsqlasync"></a><a name="afx_sql_async"></a>AFX_SQL_ASYNC  
 このマクロを MFC 4.2 で変更の実装です。  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>パラメーター  
 `prs`  
 ポインター、`CRecordset`オブジェクトまたは`CDatabase`オブジェクトです。 MFC 4.2 以降では、このパラメーターの値は無視されます。  
  
 `SQLFunc`  
 ODBC API 関数の場合。 ODBC API 関数の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 `AFX_SQL_ASYNC`マクロを呼び出すだけ[AFX_ODBC_CALL](#afx_odbc_call)を無視し、`prs`パラメーター。 MFC の 4.2 は、以前のバージョンで`AFX_SQL_ASYNC`返す可能性のある ODBC API 関数の呼び出しに使用された`SQL_STILL_EXECUTING`します。 ODBC API 関数が返さ場合`SQL_STILL_EXECUTING`、し`AFX_SQL_ASYNC`を呼び出します。`prs->OnWaitForDataSource`します。  
  
> [!NOTE]
>  MFC ODBC クラスは、ここで唯一の同期処理を使用します。 非同期操作を実行するのには、ODBC API 関数を呼び出す必要があります**SQLSetConnectOption**します。 詳細については、「関数の非同期実行」のトピックを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdb.h  
  
##  <a name="a-nameafxsqlsynca--afxsqlsync"></a><a name="afx_sql_sync"></a>AFX_SQL_SYNC  
 `AFX_SQL_SYNC`マクロは、関数を呼び出すだけ`SQLFunc`します。  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>パラメーター  
 `SQLFunc`  
 ODBC API 関数の場合。 これらの関数の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このマクロは返されません ODBC API 関数を呼び出すを使用して`SQL_STILL_EXECUTING`します。  
  
 呼び出しの前に`AFX_SQL_SYNC`、変数を宣言する必要があります`nRetCode`、型の**へ**します。 値をチェックする`nRetCode`マクロ呼び出しの後です。  
  
 なおの実装`AFX_SQL_SYNC`MFC 4.2 以降に変更します。 必要ななくなっていたサーバーの状態を確認するため`AFX_SQL_SYNC`単に値を割り当てます`nRetCode`します。 たとえば、通話を行う代わりに  
  
 [!code-cpp[NVC_MFCDatabase #&40;](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 割り当てを行うだけで  
  
 [!code-cpp[NVC_MFCDatabase #&41;](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdb.h  
  
##  <a name="a-nameafxgethenva--afxgethenv"></a><a name="afxgethenv"></a>AfxGetHENV  
 ODBC の直接の呼び出しで返されたハンドルを使用することができますには、いないハンドルを終了するか、ハンドルが有効であり、使用可能なすべての既存の後にあると`CDatabase`- または`CRecordset`-派生オブジェクトが破棄されました。  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>戻り値  
 MFC で使用されている ODBC 環境ハンドルです。 指定できます`SQL_HENV_NULL`がある場合ない[CDatabase](../../mfc/reference/cdatabase-class.md)オブジェクトと no [CRecordset](../../mfc/reference/crecordset-class.md)使用中のオブジェクト。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdb.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)


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
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: ddf13f6458df387d6686a18ecd459938ef2ebafd
ms.lasthandoff: 04/04/2017

---
# <a name="database-macros-and-globals"></a>データベース マクロとデータベース グローバル関数
マクロとグローバル変数を以下に示す ODBC ベースのデータベース アプリケーションに適用されます。 DAO ベースのアプリケーションでは使用されません。  
  
 MFC 4.2、マクロの前に`AFX_SQL_ASYNC`と`AFX_SQL_SYNC`他のプロセスに時間を生成する機会を非同期操作に指定します。 MFC 4.2 以降、これらのマクロ、MFC ODBC クラスには同期操作のみが使用されるため、変更の実装で開始します。 マクロ`AFX_ODBC_CALL`MFC 4.2 を初めて有効になりました。  
  
### <a name="database-macros"></a>データベースのマクロ  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|返す ODBC API 関数を呼び出す`SQL_STILL_EXECUTING`です。 `AFX_ODBC_CALL`繰り返し関数を呼び出すまで不要になった返します`SQL_STILL_EXECUTING`です。|  
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`.|  
|[AFX_SQL_SYNC](#afx_sql_sync)|返されない ODBC API 関数を呼び出す`SQL_STILL_EXECUTING`です。|  
  
### <a name="database-globals"></a>データベースのグローバル関数  
  
|||  
|-|-| 
|[AfxDbInitModule](#afxdbinitmodule)|データベースは、MFC と動的にリンクされるレギュラー DLL のサポートを追加します。| 
|[AfxGetHENV](#afxgethenv)|MFC で使用されている ODBC 環境ハンドルを取得します。 このハンドルは、ODBC の直接の呼び出しで使用できます。|  


## <a name="afxdbinitmodule"></a>AfxDbInitModule
MFC データベース (または DAO) は、MFC と動的にリンクされるレギュラー DLL からサポートは、この関数に対する呼び出しを追加、レギュラー DLL で**場合は**MFC を初期化する関数を DLL のデータベースです。  
   
### <a name="syntax"></a>構文    
```
void AFXAPI AfxDbInitModule( );    
```  
   
### <a name="remarks"></a>コメント  
 この呼び出しは、基底クラスを呼び出す前に発生または追加の MFC DLL をデータベースにアクセスするコードを確認してください。 MFC データベース DLL は拡張 DLL です。拡張 DLL にワイヤード (有線) を取得するため、 **CDynLinkLibrary**チェーンを作成する必要があります、 **CDynLinkLibrary**を利用することのすべてのモジュールのコンテキスト内のオブジェクト。 `AfxDbInitModule`作成、 **CDynLinkLibrary**にワイヤード (有線) を取得するためのコンテキスト内のオブジェクト、 **CDynLinkLibrary**レギュラー DLL のチェーンのオブジェクトします。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:**<afxdll_.h></afxdll_.h>  
   
### <a name="see-also"></a>関連項目  
 [マクロとグローバル](mfc-macros-and-globals.md)
 
  

##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL  
 このマクロが返される任意の ODBC API 関数の呼び出しを使用して`SQL_STILL_EXECUTING`です。  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>パラメーター  
 `SQLFunc`  
 ODBC API 関数。 ODBC API 関数の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 `AFX_ODBC_CALL`繰り返し関数を呼び出すまで不要になった返します`SQL_STILL_EXECUTING`です。  
  
 呼び出す前に`AFX_ODBC_CALL`、変数を宣言する必要があります`nRetCode`、型の**RETCODE**です。  
  
 MFC ODBC クラスのみ同期処理を今すぐ使用のことに注意してください。 非同期操作を実行するのには、ODBC API 関数を呼び出す必要があります**SQLSetConnectOption**です。 詳細についてを参照してください「関数の非同期実行」、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  

  
### <a name="example"></a>例  
 この例では`AFX_ODBC_CALL`を呼び出して、 **SQLColumns** ODBC API 関数は、によってという名前のテーブルの列の一覧を返します`strTableName`です。 宣言することに注意してください`nRetCode`と関数にパラメーターを渡すレコード セットのデータ メンバーを使用します。 例に示すもの呼び出しの結果を確認**確認**、クラスのメンバー関数`CRecordset`です。 変数`prs`へのポインター、`CRecordset`オブジェクト、他の場所を宣言します。  
  
 [!code-cpp[NVC_MFCDatabase #39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC  
 このマクロを MFC 4.2 で変更の実装です。  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>パラメーター  
 `prs`  
 ポインター、`CRecordset`オブジェクトまたは`CDatabase`オブジェクト。 MFC 4.2 以降では、このパラメーター値は無視されます。  
  
 `SQLFunc`  
 ODBC API 関数。 ODBC API 関数の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 `AFX_SQL_ASYNC`マクロを呼び出すだけ[AFX_ODBC_CALL](#afx_odbc_call)を無視し、`prs`パラメーター。 MFC の 4.2、以前のバージョンで`AFX_SQL_ASYNC`返す可能性のある ODBC API 関数の呼び出しに使用された`SQL_STILL_EXECUTING`です。 ODBC API 関数が返さ場合`SQL_STILL_EXECUTING`、し、`AFX_SQL_ASYNC`呼び出して`prs->OnWaitForDataSource`です。  
  
> [!NOTE]
>  MFC ODBC クラスは、唯一の同期処理を使用するようになりました。 非同期操作を実行するのには、ODBC API 関数を呼び出す必要があります**SQLSetConnectOption**です。 詳細についてを参照してください「関数の非同期実行」、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdb.h  
  
##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC  
 `AFX_SQL_SYNC`マクロ、関数を呼び出すだけ`SQLFunc`です。  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>パラメーター  
 `SQLFunc`  
 ODBC API 関数。 これらの関数の詳細については、次を参照してください。、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 このマクロは返されません ODBC API 関数の呼び出しを使用して`SQL_STILL_EXECUTING`です。  
  
 呼び出しの前に`AFX_SQL_SYNC`、変数を宣言する必要があります`nRetCode`、型の**RETCODE**です。 値をチェックする`nRetCode`マクロの呼び出し後にします。  
  
 なおの実装`AFX_SQL_SYNC`MFC 4.2 に変更します。 サーバーの状態をチェックは必要ですが不要になったため`AFX_SQL_SYNC`に値を単に割り当てます`nRetCode`です。 呼び出すのではなく、たとえば、  
  
 [!code-cpp[NVC_MFCDatabase #40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 割り当てを行うことができます単に  
  
 [!code-cpp[NVC_MFCDatabase #41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdb.h  
  
##  <a name="afxgethenv"></a>AfxGetHENV  
 ODBC の直接の呼び出しで返されるハンドルを使用することができますが、ハンドルを終了またはハンドルが有効であり、使用可能な既存のすべての後にあるとする必要がありますしない`CDatabase`- または`CRecordset`-派生オブジェクトが破棄されました。  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>戻り値  
 MFC で使用されている ODBC 環境ハンドルです。 指定できます`SQL_HENV_NULL`場合があるない[CDatabase](../../mfc/reference/cdatabase-class.md)オブジェクトと no [CRecordset](../../mfc/reference/crecordset-class.md)使用中のオブジェクト。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdb.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)


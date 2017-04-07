---
title: "CDBVariant クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
dev_langs:
- C++
helpviewer_keywords:
- CDBVariant class
- Variant data types, ODBC
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
caps.latest.revision: 21
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 930115ce4fe673e82a447ab1d90c260fe2b941d6
ms.lasthandoff: 02/24/2017

---
# <a name="cdbvariant-class"></a>CDBVariant クラス
MFC ODBC クラスのバリアント型を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDBVariant  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDBVariant::CDBVariant](#cdbvariant)|`CDBVariant` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDBVariant::Clear](#clear)|消去、`CDBVariant`オブジェクトです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDBVariant::m_dwType](#m_dwtype)|現在格納されている値のデータ型が含まれています。 「`DWORD`」と入力します。|  
  
### <a name="public-union-members"></a>共用体のパブリック メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDBVariant::m_boolVal](#m_boolval)|型の値を含む**BOOL**します。|  
|[CDBVariant::m_chVal](#m_chval)|型の値を含む`unsigned char`します。|  
|[CDBVariant::m_dblVal](#m_dblval)|型の値を含む**二重**します。|  
|[CDBVariant::m_fltVal](#m_fltval)|型の値を含む**float**します。|  
|[CDBVariant::m_iVal](#m_ival)|型の値が含まれる**短い**します。|  
|[CDBVariant::m_lVal](#m_lval)|型の値を含む**長い**します。|  
|[CDBVariant::m_pbinary](#m_pbinary)|型のオブジェクトへのポインターを含む`CLongBinary`します。|  
|[CDBVariant::m_pdate](#m_pdate)|型のオブジェクトへのポインターを含む**TIMESTAMP_STRUCT**します。|  
|[CDBVariant::m_pstring](#m_pstring)|型のオブジェクトへのポインターを含む`CString`します。|  
|[CDBVariant::m_pstringA](#m_pstringa)|ASCII へのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトです。|  
|[CDBVariant::m_pstringW](#m_pstringw)|幅広いへのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 `CDBVariant`基本クラスはありません。  
  
 `CDBVariant`ような[COleVariant](../../mfc/reference/colevariant-class.md)。 ただし、 `CDBVariant` OLE を使用しません。 `CDBVariant`値のデータ型について心配する値を格納できます。 `CDBVariant`共用体に格納されている現在の値のデータ型を追跡します。  
  
 クラス[CRecordset](../../mfc/reference/crecordset-class.md)利用`CDBVariant`3 つのメンバー関数内のオブジェクト: `GetFieldValue`、 `GetBookmark`、および`SetBookmark`です。 たとえば、`GetFieldValue`列のデータを動的に取得することができます。 列のデータ型が、実行時に認識されていない可能性がありますので`GetFieldValue`を使用して、`CDBVariant`列のデータを格納するオブジェクト。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDBVariant`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
##  <a name="cdbvariant"></a>CDBVariant::CDBVariant  
 Null 値を作成`CDBVariant`オブジェクトです。  
  
```  
CDBVariant();
```  
  
### <a name="remarks"></a>コメント  
 セット、 [m_dwType](#m_dwtype)データ メンバーを**DBVT_NULL**します。  
  
##  <a name="clear"></a>CDBVariant::Clear  
 オフにするには、このメンバー関数を呼び出す、`CDBVariant`オブジェクトです。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>コメント  
 場合の値、 [m_dwType](#m_dwtype)データ メンバーは**DBVT_DATE**、 **DBVT_STRING**、または**DBVT_BINARY**、**クリア**共用体ポインター メンバーに関連付けられているメモリを解放します。 **クリア**設定`m_dwType`に**DBVT_NULL**します。  
  
 `CDBVariant`デストラクター呼び出し**クリア**します。  
  
##  <a name="m_boolval"></a>CDBVariant::m_boolVal  
 型の値が格納**BOOL**します。  
  
### <a name="remarks"></a>コメント  
 **M_boolVal**共用体データ メンバーが所属します。 アクセスする前に**m_boolVal**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_BOOL**、し**m_boolVal**有効な値が含まれます。 それ以外の場合、にアクセスする**m_boolVal**信頼できない結果が生成されます。  
  
##  <a name="m_chval"></a>CDBVariant::m_chVal  
 型の値が格納`unsigned char`します。  
  
### <a name="remarks"></a>コメント  
 **M_chVal**共用体データ メンバーが所属します。 アクセスする前に**m_chVal**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_UCHAR**、し**m_chVal**有効な値が含まれています。 それ以外の場合、にアクセスする**m_chVal**信頼できない結果が生成されます。  
  
##  <a name="m_dblval"></a>CDBVariant::m_dblVal  
 型の値が格納**二重**します。  
  
### <a name="remarks"></a>コメント  
 **M_dblVal**共用体データ メンバーが所属します。 アクセスする前に**m_dblVal**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_DOUBLE**、し**m_dblVal**有効な値が含まれています。 それ以外の場合、にアクセスする**m_dblVal**信頼できない結果が生成されます。  
  
##  <a name="m_dwtype"></a>CDBVariant::m_dwType  
 このデータ メンバーに現在格納されている値のデータ型を格納する、`CDBVariant`オブジェクトの共用体データ メンバーです。  
  
### <a name="remarks"></a>コメント  
 共用体にアクセスする前に、の値を確認する必要があります`m_dwType`にアクセスするには、どの共用体データ メンバーを判断するためです。 次の表に、可能な値`m_dwType`と、対応する共用体データ メンバーです。  
  
|m_dwType|共用体データ メンバー|  
|---------------|-----------------------|  
|**DBVT_NULL**|共用体メンバーのアクセスに対して有効ではありません。|  
|**DBVT_BOOL**|[m_boolVal](#m_boolval)|  
|**DBVT_UCHAR**|[m_chVal](#m_chval)|  
|**DBVT_SHORT**|[m_iVal](#m_ival)|  
|**DBVT_LONG**|[m_lVal](#m_lval)|  
|**DBVT_SINGLE**|[m_fltVal](#m_fltval)|  
|**DBVT_DOUBLE**|[m_dblVal](#m_dblval)|  
|**DBVT_DATE**|[m_pdate](#m_pdate)|  
|**DBVT_STRING**|[m_pstring](#m_pstring)|  
|**DBVT_BINARY**|[m_pbinary](#m_pbinary)|  
|**DBVT_ASTRING**|[m_pstringA](#m_pstringa)|  
|**DBVT_WSTRING**|[m_pstringW](#m_pstringw)|  
  
##  <a name="m_fltval"></a>CDBVariant::m_fltVal  
 型の値が格納**float**します。  
  
### <a name="remarks"></a>コメント  
 **M_fltVal**共用体データ メンバーが所属します。 アクセスする前に**m_fltVal**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_SINGLE**、し**m_fltVal**有効な値が含まれています。 それ以外の場合、にアクセスする**m_fltVal**信頼できない結果が生成されます。  
  
##  <a name="m_ival"></a>CDBVariant::m_iVal  
 型の値が格納**短い**します。  
  
### <a name="remarks"></a>コメント  
 **M_iVal**共用体データ メンバーが所属します。 アクセスする前に**m_iVal**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_SHORT**、し**m_iVal**有効な値が含まれています。 それ以外の場合、にアクセスする**m_iVal**信頼できない結果が生成されます。  
  
##  <a name="m_lval"></a>CDBVariant::m_lVal  
 型の値が格納**長い**します。  
  
### <a name="remarks"></a>コメント  
 **M_lVal**共用体データ メンバーが所属します。 アクセスする前に**m_lVal**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_LONG**、し**m_lVal**有効な値が含まれています。 それ以外の場合、にアクセスする**m_lVal**信頼できない結果が生成されます。  
  
##  <a name="m_pbinary"></a>CDBVariant::m_pbinary  
 型のオブジェクトへのポインターを格納[CLongBinary](../../mfc/reference/clongbinary-class.md)します。  
  
### <a name="remarks"></a>コメント  
 **M_pbinary**共用体データ メンバーが所属します。 アクセスする前に**m_pbinary**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_BINARY**、し**m_pbinary**の有効なポインターが含まれています。 それ以外の場合、にアクセスする**m_pbinary**信頼できない結果が生成されます。  
  
##  <a name="m_pdate"></a>CDBVariant::m_pdate  
 型のオブジェクトへのポインターを格納**TIMESTAMP_STRUCT**します。  
  
### <a name="remarks"></a>コメント  
 **M_pdate**共用体データ メンバーが所属します。 アクセスする前に**m_pdate**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_DATE**、し**m_pdate**の有効なポインターが含まれています。 それ以外の場合、にアクセスする**m_pdate**信頼できない結果が生成されます。  
  
 詳細については、 **TIMESTAMP_STRUCT**トピックを参照してデータ型、 [C データ型](https://msdn.microsoft.com/library/ms714556.aspx)の付録 D に、 *ODBC プログラマ リファレンス*で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="m_pstring"></a>CDBVariant::m_pstring  
 型のオブジェクトへのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)します。  
  
### <a name="remarks"></a>コメント  
 **M_pstring**共用体データ メンバーが所属します。 アクセスする前に**m_pstring**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_STRING**、し**m_pstring**の有効なポインターが含まれています。 それ以外の場合、にアクセスする**m_pstring**信頼できない結果が生成されます。  
  
##  <a name="m_pstringa"></a>CDBVariant::m_pstringA  
 ASCII へのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 **M_pstringA**共用体データ メンバーが所属します。 アクセスする前に**m_pstringA**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_ASTRING**、し**m_pstringA**の有効なポインターが含まれています。 それ以外の場合、にアクセスする**m_pstringA**信頼できない結果が生成されます。  
  
##  <a name="m_pstringw"></a>CDBVariant::m_pstringW  
 幅広いへのポインターを格納[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 **M_pstringW**共用体データ メンバーが所属します。 アクセスする前に**m_pstringW**、最初の値をチェック[CDBVariant::m_dwType](#m_dwtype)します。 場合`m_dwType`に設定されている**DBVT_WSTRING**、し**m_pstringW**の有効なポインターが含まれています。 それ以外の場合、にアクセスする**m_pstringW**信頼できない結果が生成されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)


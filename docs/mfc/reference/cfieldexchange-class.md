---
title: "CFieldExchange クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFieldExchange
dev_langs:
- C++
helpviewer_keywords:
- enum FieldType, CFieldExchange
- RFX (record field exchange) [C++]
- RFX (record field exchange) [C++], classes for
- CFieldExchange class
- FieldType enumeration
- data types [C++], custom
- enum FieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
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
ms.openlocfilehash: 948f13dc54fcd83941bab8e63b2ab2704d84cb87
ms.lasthandoff: 02/24/2017

---
# <a name="cfieldexchange-class"></a>CFieldExchange クラス
データベース クラスで使うレコード フィールド エクスチェンジ (RFX) ルーチンとバルク レコード フィールド エクスチェンジ (Bulk RFX) ルーチンをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CFieldExchange  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFieldExchange::IsFieldType](#isfieldtype)|更新されるフィールドの型の場合は、現在の操作は、0 以外を返しますが適切なします。|  
|[つ](#setfieldtype)|レコード セットのデータ メンバーの種類を指定します: 列またはパラメーター-次の呼び出しまで RFX 関数に以下のすべての呼び出しによって表される`SetFieldType`です。|  
  
## <a name="remarks"></a>コメント  
 `CFieldExchange`基本クラスはありません。  
  
 バルク行フェッチを実装するカスタム データ型のデータ エクス チェンジ ルーチンを記述する場合は、このクラスを使用してください。それ以外の場合はない直接使用するこのクラス。 RFX と Bulk rfx 関数は、データ ソースの現在のレコードの対応するフィールドとレコード セット オブジェクトのフィールド データ メンバーの間でデータを交換します。  
  
> [!NOTE]
>  オープン データベース コネクティビティ (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスで作業している場合は、クラスを使用して[CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md)代わりにします。 詳細については、記事を参照してください。[データ アクセス プログラミング](../../data/data-access-programming-mfc-atl.md)します。  
  
 A`CFieldExchange`オブジェクトがコンテキスト情報に必要なレコード フィールド エクス チェンジまたはをバルク レコード フィールド エクス チェンジ配置を提供します。 `CFieldExchange`オブジェクトは、バインディング パラメーターのフィールド データ メンバーなど、現在のレコードのフィールドでさまざまなフラグを設定するときに、操作の数をサポートします。 RFX と Bulk rfx 関数の操作によって定義された型のレコード セット クラスのデータ メンバーに対して実行され、 `enum` **FieldType**で`CFieldExchange`します。 考えられる**FieldType**値します。  
  
- **CFieldExchange::outputColumn**フィールド データ メンバーにします。  
  
- **CFieldExchange::inputParam**または**CFieldExchange::param**の入力パラメーターのデータ メンバーです。  
  
- **CFieldExchange::outputParam**出力パラメーター データ メンバーにします。  
  
- **CFieldExchange::inoutParam**入力/出力パラメーター データ メンバーにします。  
  
 クラスのメンバー関数とデータ メンバーの多くは、独自のカスタム RFX ルーチンを記述するために提供されます。 使用する`SetFieldType`頻繁にします。 詳細については、記事を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)と[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)します。 バルク行フェッチの詳細については、記事を参照して[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。 RFX と Bulk rfx 関数のグローバル関数に関する詳細については、「[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)」MFC マクロとグローバルのこの参照します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CFieldExchange`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
##  <a name="a-nameisfieldtypea--cfieldexchangeisfieldtype"></a><a name="isfieldtype"></a>CFieldExchange::IsFieldType  
 RFX 関数を記述する場合に呼び出す`IsFieldType`特定フィールドまたはパラメーターのデータ メンバー型に現在の操作を実行できるかどうかを判断するための関数の先頭にある (、 **CFieldExchange::outputColumn**、 **CFieldExchange::inputParam**、 **CFieldExchange::param**、 **CFieldExchange::outputParam**、または**CFieldExchange::inoutParam**)。  
  
```  
BOOL IsFieldType(UINT* pnField);
```  
  
### <a name="parameters"></a>パラメーター  
 *pnField*  
 このパラメーターには、フィールドまたはパラメーターのデータ メンバーの通し番号が返されます。 この数は、データ メンバーの順序に対応、 [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)関数です。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、現在のフィールドまたはパラメーターの種類で現在の操作を実行することができます。  
  
### <a name="remarks"></a>コメント  
 既存の RFX 関数のモデルに従います。  
  
##  <a name="a-namesetfieldtypea--cfieldexchangesetfieldtype"></a><a name="setfieldtype"></a>つ  
 呼び出す必要があります`SetFieldType`でレコード セット クラスの[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)または[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)をオーバーライドします。  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFieldType`  
 値、 **enum FieldType**で宣言された`CFieldExchange`次のいずれかを指定することができます。  
  
- **CFieldExchange::outputColumn**  
  
- **CFieldExchange::inputParam**  
  
- **CFieldExchange::param**  
  
- **CFieldExchange::outputParam**  
  
- **CFieldExchange::inoutParam**  
  
### <a name="remarks"></a>コメント  
 フィールド データ メンバーを呼び出す必要があります`SetFieldType`のパラメーターを持つ**CFieldExchange::outputColumn**rfx 関数または Bulk RFX 関数の呼び出しと、その後です。 バルク行フェッチを実装していないかどうかは、これは、ClassWizard`SetFieldType`のフィールド マップのセクションでの呼び出し`DoFieldExchange`します。  
  
 レコード セット クラスをパラメーター化する場合を呼び出す必要があります`SetFieldType`、フィールド マップのセクションの外側が続く rfx 関数呼び出しのすべてのパラメーター データ メンバーのです。 パラメーター データ メンバーの種類ごとにいる必要があります独自`SetFieldType`呼び出します。 次の表は、別の値を渡すことができますを区別`SetFieldType`をクラスのパラメーターのデータ メンバーを表します。  
  
|SetFieldType パラメーター値|パラメーター データ メンバーの型|  
|----------------------------------|-----------------------------------|  
|**CFieldExchange::inputParam**|入力パラメーターです。 レコード セットのクエリまたはストアド プロシージャに渡される値。|  
|**CFieldExchange::param**|同じ**CFieldExchange::inputParam**します。|  
|**CFieldExchange::outputParam**|出力パラメーターです。 レコード セットのストアド プロシージャの戻り値。|  
|**CFieldExchange::inoutParam**|入力/出力パラメーターです。 渡され、レコード セットのストアド プロシージャから返されるする値。|  
  
 一般に、フィールド データ メンバーまたはパラメーター データ メンバーに関連付けられた RFX 関数の呼び出しの各グループの前への呼び出し`SetFieldType`します。 `nFieldType`の各パラメーター`SetFieldType`呼び出しは、以下の RFX 関数の呼び出しによって表されるデータ メンバーの種類を識別、`SetFieldType`呼び出します。  
  
 出力パラメーターと入出力パラメーターの処理の詳細については、次を参照してください。、`CRecordset`メンバー関数[FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset)します。 RFX と Bulk RFX 関数の詳細については、トピックを参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)します。 バルク行フェッチの関連情報については、記事を参照して[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
### <a name="example"></a>例  
 この例の RFX 関数の呼び出しを伴うを数回呼び出します`SetFieldType`します。 なお`SetFieldType`経由で呼び出され、`pFX`へのポインター、`CFieldExchange`オブジェクトです。  
  
 [!code-cpp[NVC_MFCDatabase #&33;](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)


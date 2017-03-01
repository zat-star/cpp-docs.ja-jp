---
title: "CDaoFieldExchange クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoFieldExchange
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), record field exchange (DFX)
- field exchange
- DFX (DAO record field exchange)
- RFX (record field exchange), DAO classes
- field exchange, record for DAO classes
- exchanging data between databases and recordsets
- DFX (DAO record field exchange), DAO Record Field Exchange
- RFX (record field exchange)
- CDaoFieldExchange class
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
caps.latest.revision: 23
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
ms.openlocfilehash: 31b7121f8e93f85ed73b5d095ac0995f3ddee721
ms.lasthandoff: 02/24/2017

---
# <a name="cdaofieldexchange-class"></a>CDaoFieldExchange クラス
DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ (DFX: DAO Record Field eXchange) ルーチンをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoFieldExchange  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|更新されるフィールドの型の場合は、現在の操作は、0 以外を返しますが適切なします。|  
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|レコード セットのデータ メンバーの種類を指定します: 列またはパラメーター-次の呼び出しまで DFX 関数へのすべての後続の呼び出しによって表される`SetFieldType`です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoFieldExchange::m_nOperation](#m_noperation)|レコード セットの現在の呼び出しによって実行される DFX 操作`DoFieldExchange`メンバー関数。|  
|[CDaoFieldExchange::m_prs](#m_prs)|操作が実行されて dfx レコード セットへのポインター。|  
  
## <a name="remarks"></a>コメント  
 `CDaoFieldExchange`基本クラスはありません。  
  
 カスタム データ型のデータ エクス チェンジ ルーチンを記述する場合は、このクラスを使用してください。それ以外の場合はない直接使用するこのクラス。 DFX のフィールド データ メンバーの間でデータを交換する、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトとデータ ソースの現在のレコードの対応するフィールドです。 DFX は、データ ソースから、データ ソースに、双方向で exchange を管理します。 参照してください[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)用カスタム DFX ルーチンを記述する方法についてです。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC Open Database Connectivity () を基 MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"というプレフィックスが付いています。 DAO クラスで ODBC データ ソースにアクセスできます。 一般に、DAO に基づいて MFC クラスは、ODBC に基づいて MFC クラスよりもより高機能なです。 DAO ベースのクラスは、独自のデータベース エンジンを使用して、ODBC ドライバーを含むデータにアクセスできます。 DAO を呼び出すのではなくクラスを使用してテーブルの追加などのデータ定義言語 (DDL) 操作もサポートします。  
  
> [!NOTE]
>  DAO レコード フィールド エクス (チェンジ DFX) は、ODBC ベースの MFC データベース クラスではレコード フィールド エクス (チェンジ RFX) によく似ています ( `CDatabase`、 `CRecordset`)。 RFX を理解している場合は、使いやすい DFX を検索されます。  
  
 A`CDaoFieldExchange`オブジェクトは、コンテキスト情報に必要な dao レコード フィールド エクスを実行します。 `CDaoFieldExchange`オブジェクトは、バインディング パラメーターのフィールド データ メンバーなど、現在のレコードのフィールドでさまざまなフラグを設定するときに、操作の数をサポートします。 DFX 操作によって定義された型のレコード セット クラスのデータ メンバーに対して実行され、 `enum` **FieldType**で`CDaoFieldExchange`します。 考えられる**FieldType**値します。  
  
- **CDaoFieldExchange::outputColumn**フィールド データ メンバーにします。  
  
- **CDaoFieldExchange::param**パラメーター データ メンバーにします。  
  
 [IsValidOperation](#isvalidoperation)メンバー関数が、独自のカスタム DFX ルーチンを記述するために用意されています。 使用する[SetFieldType](#setfieldtype)で頻繁に、 [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange)関数です。 DFX のグローバル関数に関する詳細については、「[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)します。 データ型のカスタム DFX ルーチンを記述については、次を参照してください。[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDaoFieldExchange`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="a-nameisvalidoperationa--cdaofieldexchangeisvalidoperation"></a><a name="isvalidoperation"></a>CDaoFieldExchange::IsValidOperation  
 DFX 関数を記述する場合に呼び出す`IsValidOperation`特定のフィールド データ メンバーの種類の現在の操作を実行できるかどうかを判断するための関数の先頭にある (、 **CDaoFieldExchange::outputColumn**または**CDaoFieldExchange::param**)。  
  
```  
BOOL IsValidOperation();
```  
  
### <a name="return-value"></a>戻り値  
 現在の操作が更新されるフィールドの種類に適した場合&0; 以外の値。  
  
### <a name="remarks"></a>コメント  
 DFX メカニズムによって実行された操作の一部は、使用できるフィールドの型のいずれかにのみ適用されます。 DFX 関数を既存のモデルに従います。  
  
 カスタム DFX ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)します。  
  
##  <a name="a-namemnoperationa--cdaofieldexchangemnoperation"></a><a name="m_noperation"></a>CDaoFieldExchange::m_nOperation  
 実行する操作を識別、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) field exchange オブジェクトに関連付けられているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CDaoFieldExchange`オブジェクトは、レコード セットで別の DFX 操作の数のコンテキストを提供します。  
  
> [!NOTE]
>  **PSEUDONULL** MarkForAddNew とな操作を以下で説明されている値は、の値を Null フィールドをマークするために使用します。 DAO レコード フィールド エクス機構 (エクス チェンジ DFX) では、この値を使用して、どのフィールド マークされている明示的に Null を調べます。 **PSEUDONULL**は必要ありません[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)と[COleCurrency](../../mfc/reference/colecurrency-class.md)フィールドです。  
  
 使用できる値**m_nOperation**は。  
  
|操作|説明|  
|---------------|-----------------|  
|**AddToParameterList**|ビルド、**パラメーター** SQL ステートメントの句。|  
|**AddToSelectList**|ビルド、**選択**SQL ステートメントの句。|  
|**BindField**|データベースのフィールドをアプリケーションでメモリ位置にバインドします。|  
|**BindParam**|レコード セットのクエリのパラメーター値を設定します。|  
|**修正**|フィールドに Null 状態を設定します。|  
|**AllocCache**|レコード セット内の「ダーティ」フィールドを確認するためのキャッシュが割り当てられます。|  
|**StoreField**|現在のレコードをキャッシュに保存します。|  
|**LoadField**|レコード セット内のキャッシュされたデータ メンバー変数を復元します。|  
|**FreeCache**|レコード セット内の「ダーティ」フィールドを確認するためのキャッシュを解放します。|  
|`SetFieldNull`|フィールドのステータスに設定し、Null 値を**PSEUDONULL**します。|  
|**MarkForAddNew**|マークされていない場合、フィールドの「ダーティ」 **PSEUDONULL**します。|  
|**MarkForEdit**|マークのフィールド「ダーティ」キャッシュと一致しない場合。|  
|**SetDirtyField**|「ダーティ」としてマークされている値のフィールドを設定|  
|**DumpField**|フィールドの内容 (デバッグのみ) にダンプします。|  
|**MaxDFXOperation**|入力チェックに使用されます。|  
  
##  <a name="a-namemprsa--cdaofieldexchangemprs"></a><a name="m_prs"></a>CDaoFieldExchange::m_prs  
 ポインターを含む、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトに関連付けられている、`CDaoFieldExchange`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetfieldtypea--cdaofieldexchangesetfieldtype"></a><a name="setfieldtype"></a>CDaoFieldExchange::SetFieldType  
 呼び出す`SetFieldType`で、`CDaoRecordset`クラスの`DoFieldExchange`をオーバーライドします。  
  
```  
void SetFieldType(UINT nFieldType);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFieldType`  
 値、 **enum FieldType**で宣言された`CDaoFieldExchange`次のいずれかができます。  
  
- **CDaoFieldExchange::outputColumn**  
  
- **CDaoFieldExchange::param**  
  
### <a name="remarks"></a>コメント  
 通常、ClassWizard 派生をこの呼び出しを作成します。 独自の関数を作成して書き込む、ウィザードを使用しているかどうか、`DoFieldExchange`関数の呼び出しをフィールド マップの外部関数に追加します。 ウィザードを使用しない場合はながないフィールドのマップ。 呼び出しは、クラスの各フィールドのデータ メンバーのいずれかの DFX 関数への呼び出しの前に、フィールドの型を識別する**CDaoFieldExchange::outputColumn**します。  
  
 レコード セット クラスをパラメーター化する場合は、すべてのパラメーター データ メンバー (フィールド マップの) 外の DFX 呼び出しを追加しを呼び出してこれらの呼び出しの前にする必要があります`SetFieldType`します。 値を渡す**CDaoFieldExchange::param**します。 (代わりに、使用すること、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)し、そのパラメーターの値を設定します)。  
  
 一般に、フィールド データ メンバーまたはパラメーター データ メンバーに関連付けられた DFX 関数呼び出しの各グループの前への呼び出し`SetFieldType`します。 `nFieldType`の各パラメーター`SetFieldType`呼び出しに続く DFX 関数呼び出しによって表されるデータ メンバーの種類を識別する、`SetFieldType`呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)


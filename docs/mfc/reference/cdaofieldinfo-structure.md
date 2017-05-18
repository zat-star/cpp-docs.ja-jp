---
title: "CDaoFieldInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 15db0c56480dfefb9fc8806c08596e37c7d38eb2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo 構造体
`CDaoFieldInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているフィールド オブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoFieldInfo  
{  
    CString m_strName;           // Primary  
    short m_nType;               // Primary  
    long m_lSize;                // Primary  
    long m_lAttributes;          // Primary  
    short m_nOrdinalPosition;    // Secondary  
    BOOL m_bRequired;            // Secondary  
    BOOL m_bAllowZeroLength;     // Secondary  
    long m_lCollatingOrder;      // Secondary  
    CString m_strForeignName;    // Secondary  
    CString m_strSourceField;    // Secondary  
    CString m_strSourceTable;    // Secondary  
    CString m_strValidationRule; // All  
    CString m_strValidationText; // All  
    CString m_strDefaultValue;   // All  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 Field オブジェクトの一意名します。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 `m_nType`  
 フィールドのデータ型を示す値です。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。 このプロパティの値は、次のいずれかになります。  
  
- **dbBoolean**はい/いいえと同じ**TRUE**/**FALSE**  
  
- **dbByte**バイト  
  
- **dbInteger**短い  
  
- **dbLong**長  
  
- **dbCurrency**通貨; を参照してください MFC クラス[COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **dbSingle**単一  
  
- **dbDouble**二重  
  
- **dbDate**日付/時刻; を参照してください MFC クラス[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **dbText**テキスト MFC クラスを参照してください[CString。](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **dbLongBinary**長いバイナリ (OLE オブジェクト) です。 MFC クラスを使用することができます[CByteArray](../../mfc/reference/cbytearray-class.md)クラスではなく`CLongBinary`として`CByteArray`が豊富になり簡単に使用します。  
  
- **dbMemo**メモ; を参照してください MFC クラス`CString`  
  
- **データと**グローバルに一意の識別子/ユニバーサル一意の識別子のリモート プロシージャ コールで使用されます。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。  
  
> [!NOTE]
>  バイナリ データの文字列データ型を使わないでください。 これにより、オーバーヘッドが増加し、予期しない変換時にその結果、UNICODE/ANSI 変換レイヤーを通過するデータ。  
  
 *m_lSize*  
 DAO フィールド オブジェクトを含むテキストまたはテキストまたは数値の値を含むフィールド オブジェクトの固定サイズのバイト単位の最大サイズを示す値です。 詳細については、DAO ヘルプの「サイズ プロパティ」を参照してください。 サイズは、次の値のいずれかになります。  
  
|型|サイズ (バイト)|説明|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 バイト|はい/いいえ (True または False と同じ)|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|整数型|  
|**dbLong**|4|Long|  
|**dbCurrency**|9|通貨 ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Single|  
|**dbDouble**|9|倍精度浮動小数点型|  
|**dbDate**|9|日付/時刻 ([時刻](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|テキスト ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|長いバイナリ (OLE オブジェクトです。[CByteArray](../../mfc/reference/cbytearray-class.md); の代わりに使用`CLongBinary`)|  
|**dbMemo**|0|メモ ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**データと**|16|グローバルに一意の識別子/対象として汎用的一意の識別子のリモート プロシージャ コールで使用されます。|  
  
 `m_lAttributes`  
 テーブル定義、レコード セット、クエリ定義、またはインデックスのオブジェクトに含まれるフィールド オブジェクトの特性を指定します。 返される値がビットごとの OR、C++ で作成されたこれらの定数を加えた値を指定できます (**|**) 演算子。  
  
- **dbFixedField**フィールド サイズは固定 (数値フィールドの既定値)。  
  
- **dbVariableField**フィールド サイズは、変数 (テキスト フィールドのみ)。  
  
- **dbAutoIncrField**新しいレコードのフィールドの値が変更できない一意の long 整数を自動的に増分されます。 Microsoft Jet データベースのテーブルのみサポートされます。  
  
- **dbUpdatableField**フィールドの値を変更できます。  
  
- **dbDescending**フィールドが降順で並べ替えられます (Z、A または 100 0) (インデックス オブジェクトのフィールド コレクションでは MFC では、オブジェクトが自身テーブル定義オブジェクトに含まれているインデックスのフィールド オブジェクトにのみ適用) の順序。 この定数を省略した場合に昇順に並べ替えられます (A ~ Z、0 - 100) 順 (既定値)。  
  
 このプロパティの設定を確認するときに C 使用すると、ビットごとのおよび演算子 (**&**) 特定の属性をテストします。 複数の属性を設定するときに一緒にビットごとの OR と適切な定数を組み合わせることによって (**|**) 演算子。 詳細については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
 *m_nOrdinalPosition*  
 その他のフィールドとして表示される DAO フィールド オブジェクトによって表されるフィールドを入力する数値の順序を指定する値。 このプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。 詳細については、DAO ヘルプの「OrdinalPosition プロパティ」を参照してください。  
  
 `m_bRequired`  
 DAO field オブジェクトに Null 以外の値が必要かどうかを示します。 このプロパティは、する場合**TRUE**フィールドが Null 値を許可しません。 セット必要な場合は**FALSE**、AllowZeroLength および ValidationRule プロパティの設定で指定された条件を満たす値だけでなく、Null 値、フィールドを含めることができます。 詳細については、DAO のヘルプ「プロパティのために必要な」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。  
  
 *m_bAllowZeroLength*  
 示すかどうか、空の文字列 ("") テキストまたはメモ型のデータ型を持つ DAO フィールド オブジェクトの有効な値です。 このプロパティは、する場合**TRUE**、空の文字列が有効な値です。 このプロパティを設定できます**FALSE**フィールドの値を設定する空の文字列を使用できないことを確認します。 詳細については、DAO ヘルプの「AllowZeroLength プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。  
  
 `m_lCollatingOrder`  
 文字列の比較または並べ替え用のテキストでの並べ替え順序を指定します。 詳細については、「をカスタマイズする Windows レジストリ設定のデータ アクセス」DAO ヘルプのトピックを参照してください。 返される値の一覧は、次を参照してください。、**返さ**のメンバー、 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)構造体。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。  
  
 `m_strForeignName`  
 リレーションで主テーブル内のフィールドに対応する外部キー テーブル内の DAO フィールド オブジェクトの名前を指定する値。 詳細については、DAO ヘルプの「ForeignName プロパティ」を参照してください。  
  
 *m_strSourceField*  
 テーブル定義、レコード セット、またはクエリ定義オブジェクトに含まれる DAO フィールド オブジェクトのデータの元のソースであるフィールドの名前を示します。 このプロパティは、field オブジェクトに関連付けられている元のフィールド名を示します。 たとえば、このプロパティを使用して、基になるテーブル内のフィールドの名前に関連するな名前を持つクエリ フィールド内のデータの元のソースを決定する可能性があります。 詳細については、DAO のヘルプ トピック「SourceField、SourceTable プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。  
  
 *m_strSourceTable*  
 テーブル定義、レコード セット、またはクエリ定義オブジェクトに含まれる DAO フィールド オブジェクトのデータの元のソース テーブルの名前を示します。 このプロパティは、field オブジェクトに関連付けられている元のテーブル名を示します。 たとえば、このプロパティを使用して、基になるテーブル内のフィールドの名前に関連するな名前を持つクエリ フィールド内のデータの元のソースを決定する可能性があります。 詳細については、DAO のヘルプ トピック「SourceField、SourceTable プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。  
  
 `m_strValidationRule`  
 フィールドのデータを検証する値が変更またはテーブルに追加します。 詳細については、DAO ヘルプの「ValidationRule プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。  
  
 テーブル定義の関連情報については、次を参照してください。、 **m_strValidationRule**のメンバー、 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)構造体。  
  
 `m_strValidationText`  
 DAO フィールド オブジェクトの値が ValidationRule プロパティの設定で指定された検証規則を満たしていない場合、アプリケーションで表示されるメッセージのテキストを指定する値。 詳細については、「プロパティ」DAO ヘルプのトピックを参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。  
  
 *m_strDefaultValue*  
 DAO フィールド オブジェクトの既定値。 新しいレコードが作成されると、DefaultValue プロパティの設定は自動的に入力値フィールドになります。 詳細については、DAO ヘルプの「DefaultValue プロパティ」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。  
  
## <a name="remarks"></a>コメント  
 プライマリ、セカンダリ データベースを上記のすべての参照がによって情報が返される方法を示す、`GetFieldInfo`クラスのメンバー関数[どちら](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)、および[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)します。  
  
 Field オブジェクトは、MFC クラスでは表されません。 次のクラスの MFC オブジェクトを基になる DAO オブジェクトがフィールド オブジェクトのコレクションを格納する代わりに、:[どちら](../../mfc/reference/cdaotabledef-class.md)、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)、および[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)します。 これらのクラスを指定のフィールドについては、各アイテムにアクセスするメンバー関数またはで一度にすべてにアクセスすることができます、`CDaoFieldInfo`オブジェクトを呼び出して、`GetFieldInfo`親オブジェクトのメンバー関数。  
  
 オブジェクトのプロパティを調べる際のほか、使用することも`CDaoFieldInfo`テーブル定義内の新しいフィールドを作成するための入力パラメーターを作成します。 簡単なオプションは、このタスクの使用をより細かく制御する場合は、バージョンを使用することが[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)を受け取り、`CDaoFieldInfo`パラメーター。  
  
 によって取得される情報、 `GetFieldInfo` (フィールドを格納するクラス) のメンバー関数は、`CDaoFieldInfo`構造体。 呼び出す、 `GetFieldInfo` Fields コレクションを持つ field オブジェクトが格納されている親オブジェクトのメンバー関数。 `CDaoFieldInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoFieldInfo`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)



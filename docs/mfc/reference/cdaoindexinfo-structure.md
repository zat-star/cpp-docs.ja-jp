---
title: "CDaoIndexInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
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
ms.openlocfilehash: 92206d8d8f9b2315fb859e2712a83d32a4c293ad
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo 構造体
`CDaoIndexInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているインデックス オブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoIndexInfo {  
    CDaoIndexInfo();
*// Constructor  
    CString m_strName;  // Primary  
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary  
    short m_nFields;    // Primary  
    BOOL m_bPrimary;    // Secondary  
    BOOL m_bUnique;     // Secondary  
    BOOL m_bClustered;  // Secondary  
    BOOL m_bIgnoreNulls;                // Secondary  
    BOOL m_bRequired;   // Secondary  
    BOOL m_bForeign;    // Secondary  
    long m_lDistinctCount;              // All  
 *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};   
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 Field オブジェクトの一意名します。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 `m_pFieldInfos`  
 配列へのポインター [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) tabledef またはレコード セット フィールドがインデックス内のキー フィールドを示すオブジェクト。 各オブジェクトは、インデックス内の&1; つのフィールドを識別します。 既定のインデックス順序は昇順です。 Index オブジェクトには、1 つ以上のフィールドがレコードごとにインデックス キーを表すことができます。 これらは、降順、または機能を組み合わせた、昇順ことができます。  
  
 `m_nFields`  
 格納されているフィールド数`m_pFieldInfos`します。  
  
 *m_bPrimary*  
 主なプロパティがの場合**TRUE**、index オブジェクトは、プライマリ インデックスを表します。 プライマリ インデックスは、定義済みの順序で、テーブルのすべてのレコードを一意に識別する&1; つ以上のフィールドで構成されます。 インデックス オブジェクトの一意のプロパティに設定もインデックスのフィールドは一意でなければならないので**TRUE** DAO にします。 プライマリ インデックスは、複数のフィールドで構成され場合、は、各フィールドは、重複する値を含めることができますが、すべてのインデックス付きフィールドの値の組み合わせは一意である必要があります。 プライマリ インデックスは、テーブルのキーで構成され、通常、プライマリ キーと同じフィールドが含まれます。  
  
 テーブルの主キーを設定すると、テーブルの主インデックスとして主キーが自動的に定義します。 詳細については、"プライマリ Property"および「一意のプロパティ」DAO ヘルプ トピックを参照してください。  
  
> [!NOTE]
>  あります、多くても、テーブルの&1; つのプライマリ インデックス。  
  
 *m_bUnique*  
 Index オブジェクトがテーブルの一意のインデックスを表すかどうかを示します。 場合は、このプロパティは**TRUE**、index オブジェクトは、一意のインデックスを表します。 一意のインデックスは一意で、定義済みの順序で、テーブルのすべてのレコードを論理的に整列する&1; つ以上のフィールドで構成されます。 インデックスは、1 つのフィールドで構成され、そのフィールドに値がテーブル全体に対して一意でする必要があります。 インデックスは、複数のフィールドで構成され場合、は、各フィールドは、重複する値を含めることができますが、すべてのインデックス付きフィールドの値の組み合わせは一意である必要があります。  
  
 インデックス オブジェクトの Unique とプライマリの両方のプロパティが設定されている場合**TRUE**インデックスが一意でプライマリ: 定義済みの論理的な順序でテーブル内のすべてのレコードを一意に識別します。 主なプロパティ設定されている場合**FALSE**インデックスは、セカンダリ インデックス。 (キーと非キーの両方) のセカンダリ インデックスは、論理的にテーブル内のレコードの識別子としては機能せず、定義済みの順序でレコードを配置します。  
  
 詳細については、"プライマリ Property"および「一意のプロパティ」DAO ヘルプ トピックを参照してください。  
  
 *m_bClustered*  
 Index オブジェクトがテーブルのクラスター化インデックスを表すかどうかを示します。 このプロパティは、する場合**TRUE**、index オブジェクトは、クラスター化インデックスを表します。 それ以外の場合、そうでないです。 クラスター化インデックスから成る&1; つまたは複数の非キー フィールドで、まとめると、定義済みの順序で、テーブルのすべてのレコードを配置します。 クラスター化インデックス、テーブル内のデータは文字どおり、クラスター化インデックスで指定された順序で格納されています。 クラスター化インデックスは、テーブル内のレコードに効率的にアクセスを提供します。 詳細については、「クラスター化されたプロパティ」DAO ヘルプのトピックを参照してください。  
  
> [!NOTE]
>  Clustered プロパティには、Jet データベース エンジンがクラスター化インデックスをサポートしていないために、Microsoft Jet データベース エンジンを使用するデータベースは無視されます。  
  
 *m_bIgnoreNulls*  
 インデックス フィールドに Null 値を持つレコードのインデックス エントリがあるかどうかを示します。 場合は、このプロパティは**TRUE**Null 値を持つフィールドには、インデックス エントリはありません。 フィールドを高速化を使用してレコードを検索するためには、フィールドのインデックスを定義できます。 インデックス付きフィールドが Null エントリを許可していて、Null であるエントリの多くと場合、は、インデックス オブジェクトの IgnoreNulls プロパティを設定できます**TRUE**インデックスによって使用されるストレージ領域の量を削減します。 IgnoreNulls プロパティの設定と、必要なプロパティの設定は、まとめて Null インデックス値を持つレコードが次の表に示すようにインデックス エントリを持つかどうかを決定します。  
  
|IgnoreNulls|必須|インデックスのフィールド内の null 値します。|  
|-----------------|--------------|-------------------------|  
|True|False|Null 値を許可します。インデックス エントリを追加します。|  
|False|False|Null 値を許可します。インデックス エントリが追加されました。|  
|True または False|True|Null 値が許可されていません。インデックス エントリを追加します。|  
  
 詳細については、DAO ヘルプの「IgnoreNulls プロパティ」を参照してください。  
  
 `m_bRequired`  
 DAO インデックス オブジェクトに Null 以外の値が必要かどうかを示します。 このプロパティは、する場合**TRUE**、index オブジェクトが Null 値を許可しません。 詳細については、DAO のヘルプ「プロパティのために必要な」を参照してください。  
  
> [!TIP]
>  DAO インデックス オブジェクトまたは field オブジェクト (テーブル、レコード セット、またはクエリ定義オブジェクトに含まれる) のいずれかに対してこのプロパティを設定すると、フィールド オブジェクトの設定します。 Field オブジェクトのプロパティの設定の有効性はそのインデックス オブジェクトの前にチェックされます。  
  
 *m_bForeign*  
 Index オブジェクトが、テーブルの外部キーを表すかどうかを示します。 このプロパティは、する場合**TRUE**インデックスは、テーブルの外部キーを表します。 外部キーは、主テーブル内の行を一意に識別する外部キー テーブルの&1; つまたは複数のフィールドで構成されます。 Microsoft Jet データベース エンジンでは、外部テーブルのインデックス オブジェクトを作成し、参照整合性を適用するリレーションシップを作成するときに、外部のプロパティを設定します。 詳細については、DAO ヘルプの「外部プロパティ」を参照してください。  
  
 *m_lDistinctCount*  
 関連付けられているテーブルに含まれているインデックス オブジェクトの一意の値の数を示します。 一意の値や、インデックス内のキーの数を調べて、DistinctCount プロパティを確認します。 任意のキーは&1; 回だけカウントされる場合でも、インデックスが重複する値を許可している場合、その値を複数設定にすることがあります。 この情報は、インデックスの情報を評価することによってデータ アクセスを最適化しようとするアプリケーションで役立ちます。 一意の値の数は、インデックス オブジェクトの基数とも呼ばれます。 DistinctCount プロパティが、特定の時点でキーの実際の数を常に反映していないされます。 たとえば、トランザクションのロールバックによって発生する変更は反映されませんすぐに DistinctCount プロパティに。 詳細については、DAO ヘルプの「DistinctCount プロパティ」を参照してください。  
  
## <a name="remarks"></a>コメント  
 プライマリ、セカンダリ データベースを上記のすべての参照がによって情報が返される方法を示す、`GetIndexInfo`クラスのメンバー関数[どちら](../../mfc/reference/cdaotabledef-class.md#getindexinfo)と[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)します。  
  
 Index オブジェクトは、MFC クラスでは表されません。 DAO オブジェクト クラスの基になる MFC オブジェクトの代わりに、[どちら](../../mfc/reference/cdaotabledef-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)インデックス コレクションと呼ばれるインデックス オブジェクトのコレクションが含まれています。 これらのクラスを指定のインデックスについては、個々 の項目にアクセスするメンバー関数またはで一度にすべてにアクセスすることができます、`CDaoIndexInfo`オブジェクトを呼び出して、`GetIndexInfo`親オブジェクトのメンバー関数。  
  
 `CDaoIndexInfo`コンス トラクターとデストラクターが正しく割り当ておよび割り当て解除のインデックスのフィールド情報は、するために`m_pFieldInfos`します。  
  
 によって取得される情報、`GetIndexInfo`テーブル定義オブジェクトのメンバー関数は、`CDaoIndexInfo`構造体。 呼び出す、 `GetIndexInfo` index オブジェクトが格納されているコレクションのインデックスを持つ親テーブル定義オブジェクトのメンバー関数。 `CDaoIndexInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoIndexInfo`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)



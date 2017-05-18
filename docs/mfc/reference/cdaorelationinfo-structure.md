---
title: "CDaoRelationInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
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
ms.openlocfilehash: 7c3a8195aed2c3b3fe5c78c98afcc6e72a83cc21
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo 構造体
`CDaoRelationInfo`構造体には、2 つのテーブルのフィールドの間で定義された関係に関する情報が含まれています。、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoRelationInfo  
{  
    CDaoRelationInfo();
*// Constructor  
    CString m_strName;      // Primary  
    CString m_strTable;     // Primary  
    CString m_strForeignTable;              // Primary  
    long m_lAttributes;     // Secondary  
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
    short m_nFields;        // Secondary *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 Relation オブジェクトの一意名します。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *m_strTable*  
 リレーションシップの主なテーブルを名します。  
  
 *m_strForeignTable*  
 リレーションシップの外部テーブルを名前します。 外部テーブルは、外部キーの格納に使用されるテーブルです。 一般に、外部テーブルを使用して、確立するか、参照整合性を適用します。 外部テーブルは、一対多リレーションシップの多の側に通常です。 外部テーブルの例には、アメリカの州またはカナダや顧客の注文のコードを含むテーブルが含まれます。  
  
 `m_lAttributes`  
 リレーションシップの種類についての情報が含まれています。 このメンバーの値は、次のいずれかを指定できます。  
  
- **dbRelationUnique**リレーションシップが一対一です。  
  
- **dbRelationDontEnforce**関係はありません (参照整合性がありません) が適用されます。  
  
- **dbRelationInherited**リレーションシップが&2; つの接続されているテーブルを含む固定データベースに存在します。  
  
- **dbRelationLeft**関係は、左結合します。 左外部結合には、すべての最初のレコードが含まれています (左側) の&2; つのテーブル値が一致する&2; つ目の (右側) のテーブル内のレコードがない場合でもです。  
  
- **dbRelationRight**関係は、右外部結合します。 右外部結合には、すべての&2; 番目のレコードが含まれています (右側) の&2; つのテーブル値が一致する最初の (左側) のテーブルにレコードがない場合でもです。  
  
- **これら**が連鎖的に更新します。  
  
- **dbRelationDeleteCascade**が連鎖的に削除します。  
  
 `m_pFieldInfos`  
 配列へのポインター [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)構造体。 配列には、1 つのオブジェクト リレーションシップ内の各フィールドが含まれています。 `m_nFields`データ メンバーが配列要素の数を示します。  
  
 `m_nFields`  
 数`CDaoRelationFieldInfo`内のオブジェクト、`m_pFieldInfos`データ メンバーです。  
  
## <a name="remarks"></a>コメント  
 プライマリとセカンダリの上への参照によって情報が返される方法を示す、 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)クラスのメンバー関数`CDaoDatabase`します。  
  
 リレーションシップ オブジェクトは、MFC クラスでは表されません。 代わりに、MFC オブジェクトの基になる DAO オブジェクトを使用して、`CDaoDatabase`クラスはリレーションシップ オブジェクトのコレクションを保持:`CDaoDatabase`関係情報の各アイテムにアクセスするメンバー関数を提供がすべて同時にアクセスできる、`CDaoRelationInfo`を呼び出してオブジェクト、`GetRelationInfo`親データベース オブジェクトのメンバー関数。  
  
 によって取得される情報、 [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)メンバー関数は、`CDaoRelationInfo`構造体。 `CDaoRelationInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoRelationInfo`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [CDaoRelationFieldInfo 構造体](../../mfc/reference/cdaorelationfieldinfo-structure.md)


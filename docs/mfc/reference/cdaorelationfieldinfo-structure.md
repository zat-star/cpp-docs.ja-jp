---
title: "CDaoRelationFieldInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 23d7497502f611cf2311e574556186dc5f7c7d3d
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo 構造体
`CDaoRelationFieldInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているリレーションシップのフィールドに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoRelationFieldInfo  
{  
    CString m_strName;           // Primary  
    CString m_strForeignName;    // Primary  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 リレーションシップの主テーブルのフィールドの名前。  
  
 `m_strForeignName`  
 リレーションシップの外部キー テーブル内のフィールドの名前。  
  
## <a name="remarks"></a>コメント  
 DAO リレーションシップ オブジェクトでは、主テーブルと外部テーブル内のリレーションシップを定義したフィールドで、フィールドを指定します。 上記の構造体の定義でプライマリへの参照で情報を返す方法を示す、`m_pFieldInfos`のメンバー、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)を呼び出して取得したオブジェクト、 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)クラスのメンバー関数`CDaoDatabase`します。  
  
 リレーションシップ オブジェクトとリレーションシップ フィールド オブジェクトは、MFC クラスでは表されません。 DAO オブジェクト クラスの基になる MFC オブジェクトの代わりに、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Relations コレクションと呼ばれるリレーションシップ オブジェクトのコレクションが含まれています。 さらに、各リレーションシップ オブジェクトには、リレーションシップ フィールド オブジェクトのコレクションが含まれています。 各リレーションシップ フィールド オブジェクトは、主テーブル内のフィールドを外部テーブルのフィールドと相関します。 まとめると、リレーションシップ フィールド オブジェクト グループを定義、フィールドの各テーブルのリレーションシップを定義します。 `CDaoDatabase`オブジェクトの関係を表示する、`CDaoRelationInfo`オブジェクトを呼び出して、`GetRelationInfo`メンバー関数。 `CDaoRelationInfo`オブジェクト、その後、データ メンバーを持つ`m_pFieldInfos`の配列を指す`CDaoRelationFieldInfo`オブジェクトです。  
  
 呼び出す、 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)メンバー関数を含むの`CDaoDatabase`の関係のコレクションが格納されている興味のあるリレーションシップ オブジェクト内のオブジェクトします。 アクセスし、`m_pFieldInfos`のメンバー、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)オブジェクトです。 `CDaoRelationFieldInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoRelationFieldInfo`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo 構造体](../../mfc/reference/cdaorelationinfo-structure.md)


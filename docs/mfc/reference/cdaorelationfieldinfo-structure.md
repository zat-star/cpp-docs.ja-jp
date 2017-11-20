---
title: "CDaoRelationFieldInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoRelationFieldInfo
dev_langs: C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f0de5f712d6b4413c4cfd21da1d22e0f1ff22dcd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
 リレーションシップの主テーブル内のフィールドの名前です。  
  
 `m_strForeignName`  
 リレーションシップの外部テーブル内のフィールドの名前です。  
  
## <a name="remarks"></a>コメント  
 DAO リレーションシップ オブジェクトでは、主テーブルとリレーションシップを定義した外部キー テーブル内のフィールドのフィールドを指定します。 上記の構造体の定義でプライマリへの参照で情報を返す方法を示すため、`m_pFieldInfos`のメンバー、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)呼び出すことによって取得したオブジェクト、 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)クラスのメンバー関数`CDaoDatabase`です。  
  
 リレーションシップ オブジェクトとリレーションシップ フィールド オブジェクトは、MFC クラスによって表されません。 DAO オブジェクト クラスの基になる MFC オブジェクトの代わりに、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Relations コレクションと呼ばれるリレーションシップ オブジェクトのコレクションを格納します。 さらに、各リレーションシップ オブジェクトには、リレーションシップ フィールド オブジェクトのコレクションが含まれています。 各リレーションシップのフィールド オブジェクトは、外部テーブル内のフィールドに、主テーブル内のフィールドを関連付けます。 まとめると、リレーションシップのフィールド オブジェクトをグループ定義のフィールドの各テーブルに一緒にリレーションシップを定義します。 `CDaoDatabase`関連オブジェクトにアクセスすることができます、`CDaoRelationInfo`オブジェクトを呼び出して、`GetRelationInfo`メンバー関数。 `CDaoRelationInfo`オブジェクトを持つデータ メンバー、`m_pFieldInfos`の配列を指す`CDaoRelationFieldInfo`オブジェクト。  
  
 呼び出す、 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)メンバー関数を含むの`CDaoDatabase`のリレーションのコレクションが格納されている興味のあるリレーションシップ オブジェクト内のオブジェクトします。 その後アクセス、`m_pFieldInfos`のメンバー、 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)オブジェクト。 `CDaoRelationFieldInfo`定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoRelationFieldInfo`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo 構造体](../../mfc/reference/cdaorelationinfo-structure.md)

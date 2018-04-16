---
title: "CDaoParameterInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3aabdb1dd59e1039f81d2ffe75c0d9e0770e43db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 構造体
`CDaoParameterInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているパラメーターのオブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoParameterInfo  
{  
    CString m_strName;       // Primary  
    short m_nType;           // Primary  
    ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 パラメーター オブジェクトの一意名です。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 `m_nType`  
 パラメーター オブジェクトのデータ型を示す値です。 有効な値の一覧は、次を参照してください。、`m_nType`のメンバー、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。  
  
 *m_varValue*  
 格納され、パラメーターの値、 [COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト。  
  
## <a name="remarks"></a>コメント  
 プライマリとセカンダリ上への参照は、情報がによって返される方法を示すため、 [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)クラスのメンバー関数`CDaoQueryDef`です。  
  
 MFC は、DAO クラスでオブジェクトのパラメーターをカプセル化しません。 クエリ定義オブジェクトを基になる MFC`CDaoQueryDef`オブジェクトが、パラメーター コレクションにパラメーターを格納します。 パラメーター オブジェクトにアクセスする、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクトをクエリ定義オブジェクトの`GetParameterInfo`メンバー関数の特定のパラメーター名またはパラメーターのコレクションへのインデックス。 使用することができます、 [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount)メンバー関数と組み合わせて`GetParameterInfo`パラメーター コレクションをループします。  
  
 によって取得される情報、 [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)メンバー関数は、`CDaoParameterInfo`構造体。 呼び出す`GetParameterInfo`クエリ定義オブジェクトをパラメーター コレクションを持つパラメーター オブジェクトが格納されています。  
  
> [!NOTE]
>  取得または設定パラメーターの値のみ、使用する場合、 [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue)と[パラメータ](../../mfc/reference/cdaorecordset-class.md#setparamvalue)クラスのメンバー関数`CDaoRecordset`です。  
  
 `CDaoParameterInfo`定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoParameterInfo`オブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)

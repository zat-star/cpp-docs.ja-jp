---
title: "CDaoParameterInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
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
ms.openlocfilehash: b41d26b736ea9f84c53f71dbd71949f74fb8ae52
ms.lasthandoff: 02/24/2017

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
 パラメーター オブジェクトの一意名します。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 `m_nType`  
 パラメーター オブジェクトのデータ型を示す値です。 使用可能な値の一覧は、次を参照してください。、`m_nType`のメンバー、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。  
  
 *m_varValue*  
 格納されているパラメーターの値、 [COleVariant](../../mfc/reference/colevariant-class.md)オブジェクトです。  
  
## <a name="remarks"></a>コメント  
 プライマリとセカンダリの上への参照によって情報が返される方法を示す、 [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)クラスのメンバー関数`CDaoQueryDef`します。  
  
 MFC は、DAO クラスでオブジェクトのパラメーターをカプセル化しません。 クエリ定義オブジェクトを基になる MFC`CDaoQueryDef`オブジェクトは、パラメーターをパラメーターのコレクションに格納します。 パラメーター オブジェクトにアクセスする[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクトをクエリ定義オブジェクトの`GetParameterInfo`メンバー関数の特定のパラメーター名またはパラメーターのコレクションへのインデックス。 使用することができます、 [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount)メンバー関数と併用`GetParameterInfo`パラメーター コレクションをループします。  
  
 によって取得される情報、 [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)メンバー関数は、`CDaoParameterInfo`構造体。 呼び出す`GetParameterInfo`クエリ定義オブジェクトがパラメーター コレクションを持つパラメーター オブジェクトが格納されています。  
  
> [!NOTE]
>  取得または設定パラメーターの値のみを使用する場合、 [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue)と[パラメータ](../../mfc/reference/cdaorecordset-class.md#setparamvalue)クラスのメンバー関数`CDaoRecordset`します。  
  
 `CDaoParameterInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoParameterInfo`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)


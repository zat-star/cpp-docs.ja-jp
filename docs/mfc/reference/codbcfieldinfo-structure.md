---
title: "CODBCFieldInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC, data source information
- CODBCFieldInfo structure
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 12
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
ms.openlocfilehash: 1080eb323c599014d84acab94aee4622795fdb96
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo 構造体
`CODBCFieldInfo`構造体には、ODBC データ ソース内のフィールドに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CODBCFieldInfo  
{  
    CString m_strName;  
    SWORD m_nSQLType;  
    UDWORD m_nPrecision;  
    SWORD m_nScale;  
    SWORD m_nNullability;  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 フィールドの名前。  
  
 *m_nSQLType*  
 フィールドの SQL データ型です。 これには、ODBC SQL データ型またはドライバー固有の SQL データ型を指定できます。 有効な ODBC SQL データ型については、「SQL データ型」を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 ドライバー固有の SQL データ型については、ドライバーのドキュメントを参照してください。  
  
 *m_nPrecision*  
 フィールドの最大有効桁数です。 詳細についてを参照してください「精度、スケール、長さ、および表示サイズ」、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 *m_nScale*  
 フィールドの小数点以下桁数。 詳細についてを参照してください「精度、スケール、長さ、および表示サイズ」、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 *m_nNullability*  
 かどうか、フィールドは、Null 値を受け入れます。 2 つの値のいずれか: **SQL_NULLABLE**フィールドが Null 値を受け入れる場合、または**SQL_NO_NULLS**フィールドが Null 値を受け付けない場合。  
  
## <a name="remarks"></a>コメント  
 この情報を取得する[に](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [に](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)




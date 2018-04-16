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
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b2b5d707b9915aa0d5e3fd1362746fe30a99a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 フィールドの SQL データ型です。 これには、ODBC SQL データ型またはドライバー固有の SQL データ型を指定できます。 有効な ODBC SQL データ型の一覧は、Windows SDK の「SQL データ型」を参照してください。 ドライバー固有の SQL データ型については、ドライバーのドキュメントを参照してください。  
  
 *m_nPrecision*  
 フィールドの最大有効桁数です。 詳細については、Windows SDK の「有効桁数、小数点以下桁数、長さ、および表示サイズ」を参照してください。  
  
 *m_nScale*  
 フィールドの小数点以下桁数。 詳細については、Windows SDK の「有効桁数、小数点以下桁数、長さ、および表示サイズ」を参照してください。  
  
 *m_nNullability*  
 かどうか、フィールドは、Null 値を受け入れます。 2 つの値のいずれかです: **SQL_NULLABLE**フィールドが Null 値を受け入れる場合、または**SQL_NO_NULLS**フィールドが Null 値を受け付けない場合。  
  
## <a name="remarks"></a>コメント  
 この情報を取得する[に](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdb.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [に](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)



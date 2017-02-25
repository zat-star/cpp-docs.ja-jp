---
title: "CODBCFieldInfo 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CODBCFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CODBCFieldInfo 構造体"
  - "ODBC, データ ソース情報"
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# CODBCFieldInfo 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CODBCFieldInfo` 構造体は ODBC データ ソース フィールドについての情報が格納されます。  
  
## 構文  
  
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
  
#### パラメーター  
 `m_strName`  
 フィールドの名前。  
  
 *m\_nSQLType*  
 フィールドの SQL データ型。  これは ODBC SQL データ型またはドライバー固有の SQL データ型に使用できます。  有効な ODBC SQL データ型の一覧については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]「の" SQL データ型」を参照してください。  ドライバー固有の SQL データ型については、ドライバーのドキュメントを参照してください。  
  
 *m\_nPrecision*  
 フィールドの最大の精度。  詳細については、「 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]、長さ、精度、スケール表示サイズ」を参照してください。  
  
 *m\_nScale*  
 フィールドのスケールです。  詳細については、「 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]、長さ、精度、スケール表示サイズ」を参照してください。  
  
 *m\_nNullability*  
 フィールドは、NULL 値を受け取るかどうか。  これは、2 種類の値のいずれか 1 つがです: フィールドに NULL 値を受け取るフィールドに NULL 値を受け取る **SQL\_NULLABLE**、または **SQL\_NO\_NULLS**。  
  
## 解説  
 この情報を取得するには、[CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md)を呼び出します。  
  
## 必要条件  
 **ヘッダー :** afxdb.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md)   
 [CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)
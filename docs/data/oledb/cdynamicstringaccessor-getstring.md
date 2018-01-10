---
title: "Cdynamicstringaccessor::getstring |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
dev_langs: C++
helpviewer_keywords: GetString method
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9fee0b531fa96d9767b28751e2dd8b3766278983
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicstringaccessorgetstring"></a>CDynamicStringAccessor::GetString
指定された列のデータを文字列として取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      BaseType* GetString(  
   DBORDINAL nColumn  
) const throw( );  
BaseType* GetString(  
   const CHAR* pColumnName  
) const throw( );  
BaseType* GetString(  
   const WCHAR* pColumnName  
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nColumn`  
 [in]列番号。 列番号は、1 から始まります。 値 0 は、存在する場合に、ブックマーク列を参照します。  
  
 `pColumnName`  
 [in]列の名前を表す文字列へのポインター。  
  
## <a name="return-value"></a>戻り値  
 文字列値へのポインターは、指定された列から取得されます。 値の型は***BaseType***、されます**CHAR**または**WCHAR** _UNICODE が定義されているかどうかどうかによって異なります。 指定された列が見つからない場合は、NULL を返します。  
  
## <a name="remarks"></a>コメント  
 2 番目のオーバーライド フォームは、ANSI 文字列として列名を取得します。 3 番目のオーバーライド フォームは、Unicode 文字列として列名を取得します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)
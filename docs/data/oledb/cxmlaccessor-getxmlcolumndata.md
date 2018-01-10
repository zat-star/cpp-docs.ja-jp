---
title: "Cxmlaccessor::getxmlcolumndata |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
dev_langs: C++
helpviewer_keywords: GetXMLColumnData method
ms.assetid: 719e8efe-8758-4af7-a855-0e44ea196546
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9183521d8c627d2d4befb33aa171a1651451ea12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cxmlaccessorgetxmlcolumndata"></a>CXMLAccessor::GetXMLColumnData
列で、XML 形式の文字列データとして、テーブルの列の型情報を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT GetXMLColumnData(   
   CSimpleStringW& strOutput    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `strOutput`  
 [out]取得する列の型情報を格納している文字列バッファーへの参照。 文字列には、データ ストアの列名と一致する XML タグ名が表示されます。  
  
## <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
## <a name="remarks"></a>コメント  
 列の型情報が XML でどのように書式設定方法を次に示します。 `type`列のデータ型を指定します。 データ型に基づいてされることがなく、そのアクセスされているデータベースの OLE DB データ型を使用すると、注意してください。  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CXMLAccessor クラス](../../data/oledb/cxmlaccessor-class.md)
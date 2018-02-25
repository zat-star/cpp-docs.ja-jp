---
title: "CDBErrorInfo クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDBErrorInfo class
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ae65a1a04d5befdfcd22327def8f60d96c9d4cff
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdberrorinfo-class"></a>CDBErrorInfo クラス
OLE DB を使用して OLE DB エラー処理のサポートを提供[IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
class CDBErrorInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|エラー レコードに含まれているすべてのエラー情報を返します。|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|呼び出し[IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx)指定したエラーに関する基本情報を返します。|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|呼び出し[IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx)に、カスタム エラー オブジェクトのインターフェイスへのポインターを返します。|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|呼び出し[IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx)を返す、 **IErrorInfo**指定されたレコードへのインターフェイス ポインター。|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|呼び出し[IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx)エラー パラメーターを取得します。|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|指定したオブジェクトのエラー レコードを取得します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、ユーザーに 1 つまたは複数のエラー レコードを返します。 呼び出す[cdberrorinfo::geterrorrecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)最初は、エラー レコードの数を取得します。 などのアクセスのいずれかの関数の呼び出し、 [cdberrorinfo::getallerrorinfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)、各レコードのエラー情報を取得します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)
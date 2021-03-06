---
title: "Cdatasource::openfrominitializationstring |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
dev_langs:
- C++
helpviewer_keywords:
- OpenFromInitializationString method
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f05654c9b8647f62d967f97fa4b373471e049cda
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdatasourceopenfrominitializationstring"></a>CDataSource::OpenFromInitializationString
ユーザーが指定した初期化文字列で指定されたデータ ソースを開きます。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,   
   bool fPromptForInfo= false) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *szInitializationString*  
 [in]初期化文字列。  
  
 *fPromptForInfo*  
 [in]この引数に設定されている場合**true**、し`OpenFromInitializationString`設定は、 **DBPROP_INIT_PROMPT**プロパティを**DBPROMPT_COMPLETEREQUIRED**ユーザーがあることを指定します。詳細については、必要な場合にのみを要求します。 これは、初期化文字列が、パスワードが必要なデータベースを指定する場合に便利ですが、文字列にパスワードが含まれていません。 ユーザーはパスワード (またはその他の不足している情報) を要求する、データベースに接続しようとしています。  
  
 既定値は**false**を指定することが求められます (設定**DBPROP_INIT_PROMPT**に**DBPROMPT_NOPROMPT**)。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)
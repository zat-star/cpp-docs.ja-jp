---
title: "IErrorRecordsImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IErrorRecordsImpl
- ATL.IErrorRecordsImpl
- IErrorRecordsImpl
dev_langs:
- C++
helpviewer_keywords:
- IErrorRecordsImpl class
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e69db8c89a60b7dee543bbdf87997514ba5f0cd7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="ierrorrecordsimpl-class"></a>IErrorRecordsImpl クラス
OLE DB を実装する[IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx)インターフェイス、レコードを追加して、データ メンバーからレコードを取得する ([m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)) 型の**CAtlArray <** `RecordClass`**>**.  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class RecordClass = ATLERRORINFO>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス`IErrorRecordsImpl`です。  
  
 `RecordClass`  
 OLE DB エラー オブジェクトを表すクラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|エラー レコードからエラーを説明する文字列を取得します。|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|エラー レコードからエラー GUID を取得します。|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|エラー レコードからのヘルプ コンテキスト ID を取得します。|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|エラー レコードからヘルプ ファイルの完全なパス名を取得します。|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|エラー レコードからエラーのソース コードを取得します。|  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[AddErrorRecord](../../data/oledb/ierrorrecordsimpl-adderrorrecord.md)|OLE DB エラー オブジェクトをレコードを追加します。|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|リターン コードとプロバイダー固有のエラー数など、エラーに関する基本情報を返します。|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|カスタム エラー オブジェクトのインターフェイスへのポインターを返します。|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|返します、 [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx)指定されたレコードのインターフェイス ポインター。|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|エラー パラメーターを返します。|  
|[GetRecordCount](../../mfc/reference/cdaorecordset-class.md#getrecordcount)|OLE DB レコード オブジェクト内のレコードの数を返します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|エラー レコードの配列。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
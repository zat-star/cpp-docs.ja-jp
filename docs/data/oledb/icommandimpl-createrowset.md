---
title: "Icommandimpl::createrowset |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
dev_langs: C++
helpviewer_keywords: CreateRowset method
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4fecb21b35e3941862cc38edc28a2b1e25ff6bcc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="icommandimplcreaterowset"></a>ICommandImpl::CreateRowset
によって呼び出されます[Execute](../../data/oledb/icommandimpl-execute.md)を単一の行セットを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `RowsetClass`  
 ユーザーの行セット クラスを表すテンプレート クラス メンバーです。 通常、ウィザードによって生成されます。  
  
 `pUnkOuter`  
 [in]制御へのポインター **IUnknown**インターフェイスの集計の一部として、行セットが作成される場合です。 それ以外の場合は null を返します。  
  
 `riid`  
 [in]対応する`riid`で`ICommand::Execute`です。  
  
 `pParams`  
 [入力/出力]対応する`pParams`で`ICommand::Execute`です。  
  
 `pcRowsAffected`  
 対応する`pcRowsAffected`で`ICommand::Execute`です。  
  
 `ppRowset`  
 [入力/出力]対応する`ppRowset`で`ICommand::Execute`です。  
  
 `pRowsetObj`  
 [out]行セット オブジェクトへのポインター。 通常、このパラメーターは使用されませんが COM オブジェクトを渡す前に、行セットに対してより多くの作業を実行する必要がありますと使用できます。 有効期間`pRowsetObj`によってバインドされる`ppRowset`です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。 参照してください`ICommand::Execute`の一般的な値の一覧についてはします。  
  
## <a name="remarks"></a>コメント  
 1 つ以上の行セットを作成するか、別の行セットを作成するための独自の条件を提供するには、配置に異なる呼び出し`CreateRowset`内から**Execute**です。  
  
 参照してください[icommand::execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx)で、 *OLE DB プログラマーズ リファレンスです。*  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [ICommandImpl クラス](../../data/oledb/icommandimpl-class.md)
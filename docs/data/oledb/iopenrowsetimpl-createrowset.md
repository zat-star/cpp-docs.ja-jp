---
title: "Iopenrowsetimpl::createrowset |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
dev_langs: C++
helpviewer_keywords: CreateRowset method
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dc67ec84af8125f92334077dcd3ab3580d31877a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="iopenrowsetimplcreaterowset"></a>IOpenRowsetImpl::CreateRowset
行セット オブジェクトを作成します。 ユーザーが直接呼び出されません。 参照してください[iopenrowset::openrowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx)で、 *OLE DB プログラマーズ リファレンスです。*  
  
## <a name="syntax"></a>構文  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `RowsetClass`  
 ユーザーの行セット クラスを表すテンプレート クラス メンバーです。 通常、ウィザードによって生成されます。  
  
 `pRowsetObj`  
 [out]行セット オブジェクトへのポインター。 通常、このパラメーターは使用されませんが COM オブジェクトを渡す前に、行セットに対してより多くの作業を実行する必要がありますと使用できます。 有効期間`pRowsetObj`によってバインドされる`ppRowset`です。  
  
 その他のパラメーターを参照してください。 [iopenrowset::openrowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx)で、 *OLE DB プログラマーズ リファレンスです。*  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IOpenRowsetImpl クラス](../../data/oledb/iopenrowsetimpl-class.md)
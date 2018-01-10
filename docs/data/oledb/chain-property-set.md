---
title: "CHAIN_PROPERTY_SET |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CHAIN_PROPERTY_SET
dev_langs: C++
helpviewer_keywords: CHAIN_PROPERTY_SET macro
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1de482b285f24ce9ed68bd70fa7b21b0b66a4d56
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="chainpropertyset"></a>CHAIN_PROPERTY_SET
このマクロは、プロパティのグループを一緒にチェーンします。  
  
## <a name="syntax"></a>構文  
  
```  
  
CHAIN_PROPERTY_SET(  
ChainClass   
)  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ChainClass*  
 [in]プロパティにチェーンするクラスの名前。 これは、セッション、コマンド、またはデータ ソース オブジェクト クラス) などのマップが格納されている ATL プロジェクト ウィザードで生成されるクラスです。  
  
## <a name="remarks"></a>コメント  
 独自のクラスを別のクラスからプロパティ セットのチェーンし、クラスから直接プロパティにアクセスすることができます。  
  
> [!CAUTION]
>  このマクロを慎重に使用します。 不適切に使用するには、コンシューマーの OLE DB 準拠合致テストが失敗する可能性があります。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)
---
title: "Cbookmark::cbookmark |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
dev_langs: C++
helpviewer_keywords: CBookmark class, constructor
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 63d5bef87a50b5027a743e9927f22c84636c1c9c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cbookmarkcbookmark"></a>CBookmark::CBookmark
コンストラクターです。  
  
## <a name="syntax"></a>構文  
  
```  
  
      CBookmark( );   
CBookmark(  
   DBLENGTH nSize   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nSize`  
 [in]ブックマークのバッファーのサイズ (バイト単位)。  
  
## <a name="remarks"></a>コメント  
 最初の関数では、バッファーを設定**NULL**バッファー サイズが 0 です。 2 番目の関数では、バッファー サイズを設定`nSize`、およびバッファーのバイト配列を`nSize`バイトです。  
  
> [!NOTE]
>  この関数はでのみ使用**CBookmark\<0 >**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CBookmark クラス](../../data/oledb/cbookmark-class.md)
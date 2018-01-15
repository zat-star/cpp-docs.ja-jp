---
title: "high_property_prefixes |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: high_property_prefixes
dev_langs: C++
helpviewer_keywords: high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed37cdc51c5e08899786ce82a9c3e5e3224f9f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="highpropertyprefixes"></a>high_property_prefixes
**C 固有の仕様**  
  
 3 つのプロパティ メソッドの代替プレフィックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `GetPrefix`  
 使用するプレフィックス、 **propget**メソッドです。  
  
 `PutPrefix`  
 使用するプレフィックス、 **propput**メソッドです。  
  
 `PutRefPrefix`  
 使用するプレフィックス、 **propputref**メソッドです。  
  
## <a name="remarks"></a>コメント  
 既定では、高レベルのエラー処理**propget**、 **propput**、および**propputref**メソッドは、というプレフィックスを持つメンバー関数によって公開**取得**、 `Put`、および**PutRef**、それぞれします。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
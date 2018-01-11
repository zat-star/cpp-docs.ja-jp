---
title: "raw_method_prefix |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_method_prefix
dev_langs: C++
helpviewer_keywords: raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f140bf7d65f620552dea9f2d25f4ae472139b98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rawmethodprefix"></a>raw_method_prefix
**C 固有の仕様**  
  
 名前の衝突を避けるために異なるプレフィックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
raw_method_prefix("Prefix")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Prefix`  
 使用されるプレフィックス。  
  
## <a name="remarks"></a>コメント  
 低レベルのプロパティとメソッドは、既定のプレフィックスの付いたメンバー関数によって公開される**raw _**高レベルのエラー処理メンバー関数の名前の衝突を避けるためにします。  
  
> [!NOTE]
>  場合の影響、`raw_method_prefix`の有無によって属性は変更されません、 [raw_interfaces_only](#_predir_raw_interfaces_only)属性。 `raw_method_prefix` は、プレフィックスの指定において、常に `raw_interfaces_only` に優先します。 両方の属性を同じ `#import` ステートメントで使用した場合、`raw_method_prefix` 属性で指定されているプレフィックスが使用されます。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
---
title: "high_method_prefix |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: high_method_prefix
dev_langs: C++
helpviewer_keywords: high_method_prefix attribute
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e72346573e11362f4e9b039bd87a7d3600825b04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="highmethodprefix"></a>high_method_prefix
**C 固有の仕様**  
  
 高レベルのプロパティおよびメソッドの名前付けで使用されるプレフィックスを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
high_method_prefix("Prefix")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Prefix`  
 使用されるプレフィックス。  
  
## <a name="remarks"></a>コメント  
 既定では、高度なエラー処理のプロパティとメソッドは、プレフィックスなしの名前のメンバー関数によって公開されます。 名前はタイプ ライブラリから取り込まれます。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
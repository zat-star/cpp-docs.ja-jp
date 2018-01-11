---
title: "no_implementation |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_implementation
dev_langs: C++
helpviewer_keywords: no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa0a8337de519b2b0d43e8d5035e3845e1aefbe4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="noimplementation"></a>no_implementation
**C 固有の仕様**  
  
 ラッパー メンバー関数の実装を含む .tli ヘッダーの生成を抑制します。  
  
## <a name="syntax"></a>構文  
  
```  
no_implementation  
```  
  
## <a name="remarks"></a>コメント  
 この属性を指定すると、タイプ ライブラリの項目の公開が宣言され、.tlh ヘッダーが生成されます。`#include` ステートメントによって .tli ヘッダー ファイルは取り込まれません。  
  
 この属性と組み合わせて使用[implementation_only](../preprocessor/implementation-only.md)です。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
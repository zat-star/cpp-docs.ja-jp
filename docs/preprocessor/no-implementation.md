---
title: "no_implementation |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_implementation
dev_langs:
- C++
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46d8aec1b04bca446dfacdabec272630cb20f0a6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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
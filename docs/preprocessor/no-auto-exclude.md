---
title: "no_auto_exclude |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_auto_exclude
dev_langs:
- C++
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 492e906b542ee8f378a350b04abfb1ec2e738801
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="noautoexclude"></a>no_auto_exclude
**C 固有の仕様**  
  
 自動除外を無効にします。  
  
## <a name="syntax"></a>構文  
  
```  
no_auto_exclude  
```  
  
## <a name="remarks"></a>コメント  
 タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 `#import` は、そのような項目を自動的に除外して多重定義エラーを回避します。 これが完了したら、[コンパイラの警告 (レベル 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)を除外するには、各項目に対して発行されます。 この自動除外を、この属性を使用して無効にすることができます。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
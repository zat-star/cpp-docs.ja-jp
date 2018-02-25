---
title: "rename_namespace |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- rename_namespace
dev_langs:
- C++
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37b2c01479cb489f7ed573f55a48f5807161bf63
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="renamenamespace"></a>rename_namespace
**C 固有の仕様**  
  
 タイプ ライブラリの内容を含む名前空間の名前を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
rename_namespace("NewName")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `NewName`  
 名前空間の新しい名前。  
  
## <a name="remarks"></a>コメント  
 1 つの引数を受け取る*NewName*、名前空間の新しい名前を指定します。  
  
 削除するには、名前空間を使用して、 [no_namespace](../preprocessor/no-namespace.md)属性の代わりにします。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
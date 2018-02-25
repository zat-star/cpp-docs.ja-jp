---
title: "inject_statement |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- inject_statement
dev_langs:
- C++
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7dacc2867b767495c608789b9efbe23bf7aa7110
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="injectstatement"></a>inject_statement
**C 固有の仕様**  
  
 タイプ ライブラリ ヘッダーに引数をソース テキストとして挿入します。  
  
## <a name="syntax"></a>構文  
  
```  
inject_statement("source_text")  
```  
  
#### <a name="parameters"></a>パラメーター  
 `source_text`  
 タイプ ライブラリ ヘッダー ファイルに挿入するソース テキスト。  
  
## <a name="remarks"></a>コメント  
 テキストは、ヘッダー ファイルのタイプ ライブラリの内容をラップする名前空間宣言の先頭に配置されます。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
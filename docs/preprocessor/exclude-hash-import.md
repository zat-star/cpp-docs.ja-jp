---
title: "除外 (#import) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exclude
dev_langs: C++
helpviewer_keywords: exclude attribute
ms.assetid: 0883248a-d4bf-420e-9848-807b28fa976e
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd63eed4eea9404fd0a542c0be20f1770e461508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="exclude-import"></a>exclude (#import)
**C 固有の仕様**  
  
 生成されるタイプ ライブラリのヘッダー ファイルから項目を除外します。  
  
## <a name="syntax"></a>構文  
  
```  
exclude("Name1"[, "Name2",...])  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Name1`  
 除外する最初の項目。  
  
 `Name2`  
 除外する 2 番目の項目 (必要な場合)。  
  
## <a name="remarks"></a>コメント  
 タイプ ライブラリは、システム ヘッダーまたはその他のタイプ ライブラリで定義された項目の定義を含むことがあります。 この属性は、任意の数の引数を受け取ることができます。各引数は、除外するトップ レベルのタイプ ライブラリ項目です。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
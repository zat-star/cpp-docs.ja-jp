---
title: "no_namespace |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: no_namespace
dev_langs: C++
helpviewer_keywords: no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b83e60aca7ea0e39ba67834ad1def0896dcdc07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nonamespace"></a>no_namespace
**C 固有の仕様**  
  
 名前空間名がコンパイラによって生成されないことを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
no_namespace  
```  
  
## <a name="remarks"></a>コメント  
 `#import` ヘッダー ファイルのタイプ ライブラリの内容は、通常、特定の名前空間で定義されます。 名前空間の名前がで指定された、**ライブラリ**元の IDL ファイルのステートメント。 `no_namespace` 属性を指定すると、この名前空間はコンパイラによって生成されません。  
  
 別の名前空間の名前を使用する場合を使用し、 [rename_namespace](../preprocessor/rename-namespace.md)属性の代わりにします。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
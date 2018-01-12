---
title: "バージョン (C/C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VERSION
dev_langs: C++
helpviewer_keywords: VERSION .def file statement
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63ea65a8e3732ee17cc30b3382aa7ebc56e48f59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="version-cc"></a>VERSION (C/C++)
.Exe ファイルのヘッダーに数値を格納するリンクまたは DLL に指示します。  
  
```  
VERSION major[.minor]  
```  
  
## <a name="remarks"></a>コメント  
 *メジャー*と*マイナー*引数には 0 ~ 65,535 の範囲の 10 進数。 既定値は、バージョン 0.0 です。  
  
 バージョン番号を指定するのと同じ方法は、[バージョン情報](../../build/reference/version-version-information.md)(/バージョン) オプション。  
  
## <a name="see-also"></a>参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)
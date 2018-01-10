---
title: "名前 (C/C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: name
dev_langs: C++
helpviewer_keywords: NAME .def file statement
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33e81f63e7647cbdbdc89b37ffdcb309b79e9340
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="name-cc"></a>NAME (C/C++)
メイン出力ファイルの名前を指定します。  
  
```  
NAME [application][BASE=address]  
```  
  
## <a name="remarks"></a>コメント  
 出力ファイル名を指定するのと同じ方法は、 [/out](../../build/reference/out-output-file-name.md)リンカー オプション、およびベース アドレスを設定するのと同じ方法では、 [/base](../../build/reference/base-base-address.md)リンカー オプション。 両方を指定すると、/アウトのオーバーライドの場合は**名前**です。  
  
 DLL をビルドする場合の名前は、DLL の名前のみ影響します。  
  
## <a name="see-also"></a>参照  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)
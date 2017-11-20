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
ms.openlocfilehash: 46bbbef9df3f68f322196962042039b32b4e0113
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="name-cc"></a>NAME (C/C++)
メイン出力ファイルの名前を指定します。  
  
```  
NAME [application][BASE=address]  
```  
  
## <a name="remarks"></a>コメント  
 出力ファイル名を指定するのと同じ方法は、 [/out](../../build/reference/out-output-file-name.md)リンカー オプション、およびベース アドレスを設定するのと同じ方法では、 [/base](../../build/reference/base-base-address.md)リンカー オプション。 両方を指定すると、/アウトのオーバーライドの場合は**名前**です。  
  
 DLL をビルドする場合の名前は、DLL の名前のみ影響します。  
  
## <a name="see-also"></a>関連項目  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)
---
title: "stdext 名前空間 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext
dev_langs:
- C++
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 213b760a134a645a0b6552e4c3600fc4762b0bb2
ms.lasthandoff: 02/24/2017

---
# <a name="stdext-namespace"></a>stdext 名前空間
[<hash_map>](../standard-library/hash-map.md) と [<hash_set>](../standard-library/hash-set.md) のヘッダー ファイルのメンバーは、現時点では ISO C++ 標準に含まれていません。 そのため、これらの型およびメンバーは、C++ の標準に準拠するように、名前空間 `std` から名前空間 `stdext`に移動されました。  
  
 コンパイル時に [/Ze](../build/reference/za-ze-disable-language-extensions.md) を指定すると (既定)、コンパイラは、<hash_map> および <hash_set> ヘッダー ファイルに含まれるメンバーで `std` が使用されていることについて警告を表示します。 この警告を無効にするには、[warning](../preprocessor/warning.md) プラグマを使用します。  
  
 コンパイラで **/Ze** を指定した場合に <hash_map> と <hash_set> のヘッダー ファイルのメンバーでの `std` の使用に関するエラーが生成されるようにするには、C++ 標準ライブラリ ヘッダー ファイルを #include 命令で取り込む前に、次のディレクティブを追加します。  
  
```  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  
  
 コンパイル時に **/Za**を指定すると、コンパイラはエラーを生成します。  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)



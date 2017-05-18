---
title: _SECURE_SCL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9e2bfb1095c28ea3592c5af2b89cb2fbeddcb60c
ms.openlocfilehash: f3712b4417c0fed972d9a20b6d82479561cce4b0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="securescl"></a>_SECURE_SCL
  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) に置き換えられています。このマクロは、[チェックを行う反復子](../standard-library/checked-iterators.md)を有効にするかどうかを定義します。 既定では、チェックを行う反復子はデバッグ ビルドで有効になっており、製品版ビルドで無効になっています。  
  
> [!IMPORTANT]
> `_SECURE_SCL` マクロは直接使用されなくなりました。 代わりに、`_ITERATOR_DEBUG_LEVEL` を使用して、チェックを行う反復子の設定を制御します。 詳細については、「[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
  
チェックを行う反復子が有効になっている場合、反復子の安全でない使用によってランタイム エラーが発生し、プログラムが終了します。 チェックを行う反復子を有効にするには、`_ITERATOR_DEBUG_LEVEL` を 1 または 2 に設定します。 これは、`_SECURE_SCL` を 1 または enabled に設定するのと同等です。  
  
```  
#define _ITERATOR_DEBUG_LEVEL 1  
```  
  
チェックを行う反復子を無効にするには、`_ITERATOR_DEBUG_LEVEL` を 0 に設定します。 これは、`_SECURE_SCL` を 0 または disabled に設定するのと同等です。  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
チェックを行う反復子に関する警告を無効にする方法の詳細については、「[_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
[チェックを行う反復子](../standard-library/checked-iterators.md)   
[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)   
[安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)



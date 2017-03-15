---
title: _HAS_ITERATOR_DEBUGGING | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 9e2bfb1095c28ea3592c5af2b89cb2fbeddcb60c
ms.openlocfilehash: 97d899ead2c556a39118dd49bf1f6ac7ef8a9b04
ms.lasthandoff: 02/24/2017

---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING  
  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) に置き換えられたこのマクロは、デバッグ ビルドで反復子のデバッグ機能を有効にするかどうかを定義します。 既定では、反復子のデバッグはデバッグ ビルドで有効になっており、製品版ビルドで無効になっています。 詳細については、「[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)」を参照してください。  
  
> [!IMPORTANT]
> `_HAS_ITERATOR_DEBUGGING` マクロは直接使用されなくなりました。 代わりに、`_ITERATOR_DEBUG_LEVEL` を使用して、反復子のデバッグの設定を制御します。 詳細については、「[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
デバッグ ビルドで反復子のデバッグを有効にするには、`_ITERATOR_DEBUG_LEVEL` を 2 に設定します。 これは、`_HAS_ITERATOR_DEBUGGING` を 1 または enabled に設定するのと同等です。  
  
```  
#define _ITERATOR_DEBUG_LEVEL 2  
```  
  
製品版ビルドで `_ITERATOR_DEBUG_LEVEL` を 2 に設定することはできません (`_HAS_ITERATOR_DEBUGGING` を 1 に設定することはできません)。  
  
デバッグ ビルドで反復子のデバッグを無効にするには、`_ITERATOR_DEBUG_LEVEL` を 0 または 1 に設定します。 これは、`_HAS_ITERATOR_DEBUGGING` を 0 または disabled に設定するのと同等です。  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
## <a name="see-also"></a>関連項目  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
 [反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)   
 [チェックを行う反復子](../standard-library/checked-iterators.md)   
 [安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)



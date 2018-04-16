---
title: _HAS_ITERATOR_DEBUGGING | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 39b82fbe2a7c3afa0d731185b2e9578d48c89b23
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
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
  
## <a name="see-also"></a>参照  
 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
 [反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)   
 [チェックを行う反復子](../standard-library/checked-iterators.md)   
 [安全なライブラリ: C++ 標準ライブラリ](../standard-library/safe-libraries-cpp-standard-library.md)


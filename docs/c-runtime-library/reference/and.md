---
title: and | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- And
- std.and
- std::and
dev_langs:
- C++
helpviewer_keywords:
- and macro
ms.assetid: 2644ab57-8e1b-48f0-9021-cafe3e26bdc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f32aba356acade280d86da685024c68f63e9968e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="and"></a>と、呼び出し

&& 演算子の代替手段。

## <a name="syntax"></a>構文

```C

#define and &&

```

## <a name="remarks"></a>コメント

マクロにより && 演算子が生成されます。

## <a name="example"></a>例

```cpp
// iso646_and.cpp
// compile with: /EHsc
#include <iostream>
#include <iso646.h>

int main( )
{
   using namespace std;
   bool a = true, b = false, result;

   boolalpha(cout);

   result= a && b;
   cout << result << endl;

   result= a and b;
   cout << result << endl;
}
```

```Output
false
false
```

## <a name="requirements"></a>要件

**ヘッダー:** \<iso646.h>
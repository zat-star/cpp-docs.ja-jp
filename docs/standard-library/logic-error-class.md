---
title: logic_error クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- stdexcept/std::logic_error
dev_langs:
- C++
helpviewer_keywords:
- logic_error class
ms.assetid: b290d73d-94e1-4288-af86-2bb5d71f677a
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3c7993e70b32c69b1c10bbf6c43613521cab25e4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="logicerror-class"></a>logic_error クラス

このクラスは、論理的前提条件に対する違反など、プログラムの実行前に検出可能なエラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。

## <a name="syntax"></a>構文

```cpp
class logic_error : public exception {
public:
    explicit logic_error(const string& message);

    explicit logic_error(const char *message);

};
```

## <a name="remarks"></a>コメント

[what](../standard-library/exception-class.md) によって返される値は、**message**`.`[data](../standard-library/basic-string-class.md#data) のコピーです。

## <a name="example"></a>例

```cpp
// logic_error.cpp
// compile with: /EHsc /GR
#include <iostream>
using namespace std;

int main( )
{
   try
   {
      throw logic_error( "logic error" );
   }
   catch ( exception &e )
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
```

```Output
Caught: logic error
Type: class std::logic_error
```

## <a name="requirements"></a>要件

**ヘッダー:** \<stdexcept>

**名前空間:** std

## <a name="see-also"></a>関連項目

[exception クラス](../standard-library/exception-class.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

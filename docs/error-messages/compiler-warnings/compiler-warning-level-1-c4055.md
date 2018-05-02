---
title: コンパイラの警告 (レベル 1) C4052 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- C4055
dev_langs:
- C++
helpviewer_keywords:
- C4055
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29b1c8bcc836e35f7b8b81954ef247527d8ec35e
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
---
# <a name="compiler-warning-level-1-c4055"></a>コンパイラの警告 (レベル 1) C4055

> '*変換*': データ ポインターが'*type1*'を関数ポインター'*type2*'

## <a name="remarks"></a>コメント

**古い形式:** この警告は、Visual Studio 2017 およびそれ以降のバージョンによっては生成されません。

データポインターが、誤って関数ポインターにキャストされています。 これは /Za ではレベル 1 の警告になり、/Ze ではレベル 4 の警告になります。

## <a name="example"></a>例

次の例では C4055 が生成されます。

```C
// C4055.c
// compile with: /Za /W1 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
   return (PFUNC)pi;   // C4055
}
```

これは、/Ze ではレベル 4 の警告です。

```C
// C4055b.c
// compile with: /W4 /c
typedef int (*PFUNC)();
int *pi;
PFUNC f() {
return (PFUNC)pi;   // C4055
}
```

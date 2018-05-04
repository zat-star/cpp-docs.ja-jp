---
title: 致命的なエラー C1189 |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b49f227b5fda20ab0ba202d3d7eca99492509b35
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="fatal-error-c1189"></a>致命的なエラー C1189

> **\#エラー:** *ユーザーが指定したエラー メッセージ*

## <a name="remarks"></a>コメント

C1189 がによって生成された、`#error`ディレクティブです。 ディレクティブをコード開発者は、エラー メッセージのテキストを指定します。 詳細については、次を参照してください。 [#error ディレクティブ (c/c++)](../../preprocessor/hash-error-directive-c-cpp.md)です。

## <a name="example"></a>例

次の例では、C1189 を生成します。 サンプルでは、開発者がカスタム エラー メッセージを発行、`_WIN32`識別子が定義されていません。

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>関連項目

[#define ディレクティブ (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)
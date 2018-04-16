---
title: "コンパイラの警告 (レベル 4) C4233 |Microsoft ドキュメント"
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4233
dev_langs:
- C++
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad27d2ec3d59df147d8bfc26372a2d25397e651f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4233"></a>コンパイラの警告 (レベル 4) C4233

> 使用される標準の拡張機能: '*キーワード*' キーワードは C++ では、C ではなくのみサポートされます

コンパイラは C++ ではなく、C として、ソース コードをコンパイルし、キーワードは C++ でのみ有効です。 ソース ファイルの拡張子が .c またはを使用する場合、コンパイラが C として、ソース ファイルをコンパイル[/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)です。

この警告は、自動的にエラーになります。 この動作を変更する場合は、使用[#pragma 警告](../../preprocessor/warning.md)です。 たとえば、C4233 に、レベル 4 の警告を発行するために、この行をソース コード ファイルに追加します。

```cpp
#pragma warning(4:4233)
```

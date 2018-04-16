---
title: コンパイラの警告 (レベル 1) C4124 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38588fb242b5b4167984e15d101594d1b015ec86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4124"></a>コンパイラの警告 (レベル 1) C4124
_ _fastcall スタック チェックでは効率的ではありません。  
  
 `__fastcall`スタック チェックが有効でキーワードが使用されました。  
  
 `__fastcall`規則には、高速のコードが生成されますが、低速コードをスタック チェックします。 使用する場合`__fastcall`、スタック チェックをオフにする、 **check_stack**プラグマまたは/Gs です。  
  
 この警告は、最初にこれらの条件下で宣言された関数に対してのみ実行されます。
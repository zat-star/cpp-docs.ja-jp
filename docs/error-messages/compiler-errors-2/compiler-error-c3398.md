---
title: "コンパイラ エラー C3398 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b332346dd8e8b7e906e961c86805ad0564f0f79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3398"></a>コンパイラ エラー C3398
'operator': 'function_signature' から 'function_pointer' に変換できません。 ソース式は関数シンボルでなければなりません  
  
 [/clr](../../cpp/clrcall.md) を使用してコンパイルするときに、 **__clrcall**呼び出し規則が指定されていないと、コンパイラは各関数に対して、ネイティブ エントリ ポイントとマネージ エントリ ポイントという 2 つのエントリ ポイント (アドレス) を生成します。  
  
 既定では、コンパイラはネイティブ エントリ ポイントを返しますが、場合によっては、マネージ エントリ ポイントが必要な場合があります (たとえば、 `__clrcall` 関数ポインターにアドレスを 割り当てる場合など)。 割り当てでコンパイラが確実にマネージ エントリ ポイントを選択するためには、右辺を関数シンボルにする必要があります。
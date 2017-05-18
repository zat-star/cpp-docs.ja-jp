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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 66bd229369456da18d8bed60b25b6e6b07e03f27
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3398"></a>コンパイラ エラー C3398
'operator': 'function_signature' から 'function_pointer' に変換できません。 ソース式は関数シンボルでなければなりません  
  
 ときに、 [_ _clrcall](../../cpp/clrcall.md)呼び出し規約が指定されていないでコンパイルするときに**/clr**をコンパイラには、各関数に対して、ネイティブ エントリ ポイントとマネージ エントリ ポイントの 2 つのエントリ ポイント (アドレス) が生成されます。  
  
 既定では、コンパイラはネイティブ エントリ ポイントを返しますが、場合によっては、マネージ エントリ ポイントが必要な場合があります (たとえば、 `__clrcall` 関数ポインターにアドレスを 割り当てる場合など)。 割り当てでコンパイラが確実にマネージ エントリ ポイントを選択するためには、右辺を関数シンボルにする必要があります。

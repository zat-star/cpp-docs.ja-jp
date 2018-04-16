---
title: "コンパイラの警告 (レベル 1) C4788 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4788
dev_langs:
- C++
helpviewer_keywords:
- C4788
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e6f876dada851f46b7708ef1b34da4bae6f96dc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4788"></a>コンパイラの警告 (レベル 1) C4788
'識別子' : 識別子は '数値' 文字に切り詰められました  
  
 コンパイラによって、関数名に使用できる最大文字数が制限されます。 いくつかのテキストに関数名を付加することによって作成された funclet 名を形成、コンパイラは、コードの funclets を生成するとき、"_ _catch"、"\__unwind"、または別の文字列。  
  
 作成された funclet 名が長すぎる場合、コンパイラはこれを切り捨てて C4788 を生成します。  
  
 この警告を解決するには、元の関数名を短くします。 関数が C++ テンプレート関数またはメソッドの場合は、名前の一部に typedef を使用します。 例:  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 これは次のように置換されます。  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 この警告は [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] コンパイラでのみ出力されます。
---
title: "構造化例外処理で C++ を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, mixed with SEH
- structured exception handling [C++], with C++ exception handling
ms.assetid: ec34b528-8c26-4429-b24a-6a68553aaa91
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db5d067a391512d56a2d01ce3052ac3fab061f28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-structured-exception-handling-with-c"></a>C++ での構造化例外処理の使用
これらの技術情報で説明されている構造化例外処理では、C および C++ ソース ファイルを使用します。 ただし、特に C++ 用にデザインされていないため、推奨されません。 C++ 例外処理を使用して、コードの移植性を高めることができます。 また、C++ 例外処理メカニズムは、任意の型の例外を処理できるという点で、より柔軟です。  
  
 Microsoft C++ は、ANSI C++ 規格に基づいて、C++ の例外処理モデルをサポートするようになりました。 この機構は、スタックのアンワインド中に、自動的にローカル オブジェクトの破棄を処理します。 フォルト トレラントな C++ コードを記述するときに、例外処理を実装する場合は、構造化例外処理ではなく、C++ 例外処理を使用することを強くお勧めします。 (これらの技術情報に説明されているように、C++ コンパイラは構造化例外処理の構造をサポートしますが、標準 C コンパイラは C++ 例外処理の構文をサポートしません)。C++ 例外処理の詳細については、次を参照してください。 [C++ 例外処理](../cpp/cpp-exception-handling.md)と*注解 C++ リファレンス マニュアル*Margaret Ellis と Bjarne Stroustrup でします。  
  
## <a name="see-also"></a>参照  
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
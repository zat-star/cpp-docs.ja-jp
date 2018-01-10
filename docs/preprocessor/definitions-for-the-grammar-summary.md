---
title: "文法概要の定義 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36ce8a4f1bf6e4c5e9c79298899c871c74c1707b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="definitions-for-the-grammar-summary"></a>文法の概要での定義
終端は構文定義内のエンドポイントです。 他の解決はありません。 終端には、予約語およびユーザー定義の識別子が含まれます。  
  
非終端は構文内のプレースホルダーです。 ほとんどは、この構文概要の他の場所で定義されています。 定義は再帰的に行うことができます。 次の非終端がで定義されている、[構文規則](../cpp/lexical-conventions.md)のセクションで、 *C++ 言語リファレンス*:  
  
`constant`、*定数式*、*識別子*、*キーワード*、 `operator`、`punctuator`  
  
省略可能な構成要素には添字 "opt" を付けます。 たとえば、次の例では、省略可能な式が中かっこで囲まれています。  
  
**{** *式*opt **}**  
  
## <a name="see-also"></a>参照  
[文法の概要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)
---
title: "コンパイラ エラー C2002 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a2cbd21c27cff3effad69b19f42eeaecacf20d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2002"></a>コンパイラ エラー C2002
無効なワイド文字定数  
  
 マルチバイト文字定数が正しくありません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ワイド文字定数には、予想よりも多くのバイト数が含まれています。  
  
2.  標準ヘッダー STDDEF.h は含まれません。  
  
3.  ワイド文字は、通常のリテラル文字列と連結ことはできません。  
  
4.  ワイド文字定数は、文字 'L' 続く必要があります。  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Microsoft C プリプロセッサ ディレクティブのテキストの引数は ASCII である必要があります。 たとえば、次のようなディレクティブがあると、 `#pragma message(L"string")`、無効です。
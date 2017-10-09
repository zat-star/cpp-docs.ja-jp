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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d8f6fc5983a462850581f69ca32dd7c305f9e847
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

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

---
title: "例外ハンドラーに対する制限 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9e55ba9c36fdbc5f3c19e7ad81373599ab138e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="restrictions-on-exception-handlers"></a>例外ハンドラーに関する制約
コードで例外ハンドラーを使用する際の主要な制限は、`goto` ステートメントを使用して `__try` ステートメント ブロック内に移動できないことです。 代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。 必要に応じて、`__try` ステートメント ブロックの外に移動して、例外ハンドラーを入れ子にすることができます。  
  
## <a name="see-also"></a>参照  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理 (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
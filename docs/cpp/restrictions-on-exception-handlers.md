---
title: "例外ハンドラーに関する制約 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例外処理, 例外ハンドラー"
  - "制限事項, 例外ハンドラー"
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 例外ハンドラーに関する制約
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コードで例外ハンドラーを使用する際の主要な制限は、`goto` ステートメントを使用して `__try` ステートメント ブロック内に移動できないことです。  代わりに、制御の標準フローに従ってステートメント ブロックに入る必要があります。  必要に応じて、`__try` ステートメント ブロックの外に移動して、例外ハンドラーを入れ子にすることができます。  
  
## 参照  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)
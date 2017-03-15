---
title: "1 つのウィンドウで複数のコントロールをホストできますか? | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール [ATL], ホスト (複数の)"
  - "ウィンドウ [C++], ホスト (複数のコントロールを)"
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1 つのウィンドウで複数のコントロールをホストできますか?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

単一の ATL のホスト ウィンドウで複数のコントロールをホストできません。  各ホスト ウィンドウは、1 種類のコントロールを一度に一つだけ保持するように設計されています \(これは、リフレクション メッセージと、コントロールのアンビエント プロパティの処理の単純な機構ができます\)。  ただし、ユーザーが一つのウィンドウで複数のコントロールを確認することが必要な場合は、そのウィンドウの子として複数のホスト ウィンドウを作成する単純な問題です。  
  
## 参照  
 [コントロール コンテインメント : Q & A 集](../atl/atl-control-containment-faq.md)
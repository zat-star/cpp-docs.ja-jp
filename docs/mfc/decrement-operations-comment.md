---
title: "--Operations コメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Operations comment in MFC source files
- comments, MFC
- MFC source files, Operations comments
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53d2470e0be0ca314da8486d74d8fc618e134c35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="-operations-comment"></a>// Operations コメント
`// Operations`の MFC クラス宣言のセクションには、操作を実行したり、(操作を実行する) アクションを実行するオブジェクトで呼び出すことができるメンバー関数が含まれています。 これらの関数は通常**const**副作用があるためです。 仮想またはクラスのニーズに応じて、非仮想があります。 通常、これらのメンバーはパブリックです。  
  
 クラスを一覧表示するサンプルで`CStdioFile`の[のコメントの例](../mfc/an-example-of-the-comments.md)、一覧には、このコメントの下の 2 つのメンバー関数が含まれています:`ReadString`と`WriteString`です。  
  
 同様に、属性は、操作をさらに分割します。  
  
## <a name="see-also"></a>参照  
 [MFC ソース ファイルを使用します。](../mfc/using-the-mfc-source-files.md)   
 [コメントの例](../mfc/an-example-of-the-comments.md)   
 [//Implementation コメント](../mfc/decrement-implementation-comment.md)   
 [//Constructors コメント](../mfc/decrement-constructors-comment.md)   
 [//Attributes コメント](../mfc/decrement-attributes-comment.md)   
 [//Overridables コメント](../mfc/decrement-overridables-comment.md)


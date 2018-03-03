---
title: "--//Constructors コメント |Microsoft ドキュメント"
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
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f6425252df34936d4ba3c9013664205b0038d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="-constructors-comment"></a>// Constructors コメント
`// Constructors`の MFC クラス宣言のセクションでは、実際にオブジェクトを使用するために必要なすべての初期化関数と同様に (C++ の) コンス トラクターを宣言しています。 たとえば、`CWnd::Create`使用する前にあるために、コンス トラクターに記載されて、`CWnd`オブジェクト、その必要があります「を完全に構築」まず C++ コンス トラクターを呼び出すし、呼び出すことによって、**作成**関数。 通常、これらのメンバーはパブリックです。  
  
 たとえば、クラス`CStdioFile`の下の一覧に表示されるうちの 1 つ、3 つのコンス トラクターを持つ[コメントの例を](../mfc/an-example-of-the-comments.md)です。  
  
## <a name="see-also"></a>参照  
 [MFC ソース ファイルを使用します。](../mfc/using-the-mfc-source-files.md)   
 [//Implementation コメント](../mfc/decrement-implementation-comment.md)   
 [//Attributes コメント](../mfc/decrement-attributes-comment.md)   
 [//Operations コメント](../mfc/decrement-operations-comment.md)   
 [//Overridables コメント](../mfc/decrement-overridables-comment.md)


---
title: "--属性コメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c93d27cb5a9c6ef83f5b4f027d0e54cbe69a6bbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="-attributes-comment"></a>// Attributes コメント
`// Attributes`の MFC クラス宣言のセクションには、オブジェクトのパブリックの属性 (またはプロパティ) が含まれています。 通常これらは、メンバー変数、または関数を取得または設定します。 "Get"および"Set"関数は、仮想できない可能性があります。 "Get"関数は、通常**const**ほとんどの場合ではありません副作用が生じるのため、します。 これらのメンバーは通常はパブリックです。protected および private の属性は、通常、implementation セクションであります。  
  
 クラスを一覧表示するサンプルの`CStdioFile`[のコメントの例](../mfc/an-example-of-the-comments.md)、一覧には、1 つのメンバー変数が含まれています。`m_pStream`です。 クラス`CDC`このコメントの下の 20 個のメンバーを一覧表示します。  
  
> [!NOTE]
>  などの大きなクラス`CDC`と`CWnd`、単に 1 つのグループ内のすべての属性を一覧表示をわかりやすくするためには追加されません非常に多くのメンバーがあります。 このような場合は、クラス ライブラリをさらに、メンバーを記述するその他のコメントを見出しとして使用します。 たとえば、`CDC`使用`// Device-Context Functions`、 `// Drawing Tool Functions`、`// Drawing Attribute Functions`などです。 属性を表すグループは上記で説明した通常の構文に従います。 OLE クラスの多くがあると呼ばれる implementation セクション`// Interface Maps`です。  
  
## <a name="see-also"></a>関連項目  
 [MFC ソース ファイルを使用します。](../mfc/using-the-mfc-source-files.md)   
 [コメントの例](../mfc/an-example-of-the-comments.md)   
 [//Implementation コメント](../mfc/decrement-implementation-comment.md)   
 [//Constructors コメント](../mfc/decrement-constructors-comment.md)   
 [//Operations コメント](../mfc/decrement-operations-comment.md)   
 [//Overridables コメント](../mfc/decrement-overridables-comment.md)


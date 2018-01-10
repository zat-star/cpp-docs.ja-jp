---
title: "2.7.2.1 プライベート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a08faf39ab2f82d76a936c216ba6707bee5c240
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="2721-private"></a>2.7.2.1 private
`private`句は、チーム内の各スレッドに対してプライベートである変数の一覧で変数を宣言します。 構文、`private`句を次に示します。  
  
```  
private(variable-list)  
```  
  
 指定された変数の動作、`private`句を次に示します。 自動ストレージ存続期間のある新しいオブジェクトは、構造に割り当てられます。 サイズと、新しいオブジェクトの配置については、変数の型によって決まります。 この割り当ては、チーム内の各スレッドの 1 回発生し、必要に応じてクラス オブジェクトの既定のコンス トラクターが呼び出されますそれ以外の場合、初期値は不定になります。  変数によって参照されている元のオブジェクトは、コンストラクトに入った不定値を持ち、コンストラクトの動的な範囲内で変更しないでくださいおよびコンストラクトからの終了時に中間値を持っています。  
  
 ディレクティブの構造の構文の範囲では、変数は、スレッドが割り当てられている新しいプライベート オブジェクトを参照します。  
  
 制限、`private`句は、次のようにします。  
  
-   指定されているクラス型の変数、`private`句は、アクセス可能なあいまいさのない既定のコンス トラクターを持つ必要があります。  
  
-   指定された変数、`private`句は必要ありません、 **const**-型がクラスがない限り、型を修飾、`mutable`メンバー。  
  
-   指定された変数、`private`句が不完全な型または参照型は必要ありません。  
  
-   表示される変数、`reduction`の句、**並列**ディレクティブを指定することはできません、 `private` parallel コンストラクトにバインドされる動作共有ディレクティブの句。
---
title: "メモリ上書きのチェックにデバッグ ビルドを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7b8fc223a1e4e1162ce99bb3275152c49828aa99
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>デバッグ ビルドを使用したメモリ上書きのチェック
デバッグ ビルドを使用して、メモリ上書きの確認するには、は、まずプロジェクトをデバッグを再構築する必要があります。 アプリケーションの先頭に移動し、`InitInstance`関数し、次の行を追加します。  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 デバッグ メモリ アロケーターは、すべてのメモリ割り当ての周囲のガード バイトを格納します。 ただし、これらのガード バイトが実行しないことも意味するかどうか変更されている (つまり、メモリの上書き) をチェックする場合を除き、します。 それ以外の場合、これだけ、バッファーを提供できる場合もあります、実際には、メモリの上書きを回避します。  
  
 オンで、 `checkAlwaysMemDF`、MFC の呼び出しを行うには強制は、`AfxCheckMemory`関数への呼び出しのたびに**新しい**または**削除**が行われます。 メモリ上書きが検出された場合、次のようなトレース メッセージを生成します。  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 これらのメッセージのいずれかの場合は、破損が発生した場所を決定するコードをステップ実行する必要があります。 具体的には、メモリの上書きが発生した場所を特定するには、明示的な呼び出しを行うことができます`AfxCheckMemory`自分でします。 例:  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 最初のアサートは成功し、2 つ目が失敗して場合、は、メモリ上書き関数は、次の 2 つの呼び出しの間で発生したことを意味します。  
  
 アプリケーションの性質、によってことがあります`afxMemDF`するテストも実行速度が遅すぎます。 `afxMemDF`変数`AfxCheckMemory`を新しい呼び出しごとに呼び出され、削除します。 その場合は、独自の呼び出しを散布図する必要があります`AfxCheckMemory`()、上記のようにしようとして、メモリを特定する方法を上書きします。  
  
## <a name="see-also"></a>関連項目  
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)
---
title: "リンカー ツールの警告 LNK4006 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4006
dev_langs: C++
helpviewer_keywords: LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 021961029d274172119ae92aa10cc6a236dd973b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4006"></a>リンカー ツールの警告 LNK4006
オブジェクトで既に定義されているシンボル2 つ目の定義を無視します  
  
 指定された `symbol` (修飾された形式で表示) は重複定義されています。 この警告が発生したときに`symbol`は 2 回追加されますが、最初の形式だけが使用されます。  
  
 2 つのインポート ライブラリを 1 つにマージしようとする場合は、この警告を取得できます。  
  
 C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  指定された`symbol`でコンパイルして作成された、パッケージ化された関数があります[/Gy](../../build/reference/gy-enable-function-level-linking.md)です。 このシンボルは、複数のファイルに含まれていましたが、コンパイルの間で変更されました。 含まれているすべてのファイルを再コンパイル、`symbol`です。  
  
2.  指定された`symbol`可能性がありますで定義されているが異なる別のライブラリ内の 2 つのメンバー オブジェクトです。  
  
3.  絶対は、可能性がありますで定義されている 2 回、それぞれの定義で別の値。  
  
4.  ライブラリを結合するときに、エラー メッセージを受信した場合`symbol`に追加されているライブラリに既に存在します。
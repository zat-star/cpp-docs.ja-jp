---
title: "リンカー ツールの警告 LNK4105 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4105
dev_langs: C++
helpviewer_keywords: LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 913a6da056908def8df5aab1c2425ef9a187c1e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4105"></a>リンカー ツールの警告 LNK4105
オプション 'option'; で指定された引数がいません。オプションを無視します  
  
 のみでこの警告が発生したときに、 [/LIBPATH](../../build/reference/libpath-additional-libpath.md)オプションを設定します。 このオプションでディレクトリが指定されていない場合、リンカーはオプションが無視され、この警告メッセージが生成されます。  
  
 既存の環境のライブラリ設定を上書きする必要がない場合は、リンカーのコマンドラインから/LIBPATH オプションを削除します。 ライブラリの別の検索パスを使用する場合は、/LIBPATH オプションを次に、代替パスを指定します。  
  
## <a name="example"></a>例  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 必要なライブラリを検索するようにリンカーを指示`c:\filepath\lib`の既定の場所で検索する前にします。
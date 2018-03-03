---
title: "リンカー ツールの警告 LNK4092 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4092
dev_langs:
- C++
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a25954b8dc15863a290bd5a99119cc79a5585e16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4092"></a>リンカー ツールの警告 LNK4092
共有書き込みセクション 'section' には、再配置; が含まれています。イメージは正しく動作しない可能性があります。  
  
 リンカーは、警告を取得する可能性がある重大な問題の共有セクションがある場合、この警告を出力します。  
  
 複数のプロセス間でデータを共有する方法の 1 つは、セクションに「共有」のマークを付けます ただし、共有セクションをマークすると問題が発生することができます。 たとえば、共有データ セクションに次のように宣言を含む DLL がある場合。  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 リンカーが解決できない`pvar`のため、その値は、DLL がメモリに読み込まれてに依存するために従った再配置レコードに入れます DLL です。 メモリのアドレスに DLL が読み込まれるときに`var`解決できると`pvar`割り当てられます。 別のプロセスは同じ DLL を読み込みますが、同時に読み込むことができませんがある場合、アドレスのアドレスの再配置`var`間違った宛先にポイントが 2 番目のプロセスと、最初にプロセスのアドレス空間が更新されます。
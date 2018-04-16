---
title: "コンパイラ エラー C2567 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28cd1dc74e15ae3cd63286fc6de9c3508bb1d279
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2567"></a>コンパイラ エラー C2567
'file' のメタデータを開くことができません、ファイルが削除されたか移動  
  
 ソースの参照されたメタデータ ファイル (で`#using`) が見つかりませんでした同じディレクトリに、コンパイラ バックエンド プロセスによってコンパイラ フロント エンドのプロセスによってだとします。 参照してください[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)詳細についてはします。  
  
 コンパイルする場合は、C2567 を原因となったでした**/c** 1 つでコンピューターし、その後、別のコンピューター上のリンク時コード生成を試みます。 詳細については、次を参照してください。 [/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md))。  
  
 お使いのコンピューターがメモリ不足であることを示すも可能性があります。  
  
 このエラーを解決するには、ビルド プロセスのすべてのフェーズの同じディレクトリの場所にメタデータ ファイルであることを確認します。
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
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6cd355d7654f931196acc324f7d58b99c6f25f29
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2567"></a>コンパイラ エラー C2567
'file' のメタデータを開けません、ファイルが削除されたか、移動  
  
 ソースの参照されたメタデータ ファイル (と`#using`) 同じディレクトリ内で見つからなかったコンパイラのバックエンド プロセスであったため、コンパイラのフロント エンドのプロセスによってです。 参照してください[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)の詳細。  
  
 コンパイルする場合は、C2567 を原因となったでした**/c**&1; つのマシンし、その後、別のコンピューターでのリンク時コード生成を試みます。 詳細については、次を参照してください。 [/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md))。  
  
 お使いのコンピューターがメモリ不足であることを示すも可能性があります。  
  
 このエラーを解決するには、メタデータ ファイルが同じディレクトリの場所にビルド プロセスのすべてのフェーズになっていることを確認します。

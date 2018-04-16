---
title: "致命的なエラー C1061 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1061
dev_langs:
- C++
helpviewer_keywords:
- C1061
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81963b0fffdf1b86b56b10c0776874b37ae9daa2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1061"></a>致命的なエラー C1061
コンパイラの制限 : プログラム内のブロックの入れ子のレベルが深すぎます。  
  
 コード内のブロックの入れ子レベルが、制限値 128 を超えています。 これは、32 ビットおよび 64 ビットのツール セットにおける、C と C++ の両方のコンパイラのハード リミットです。 入れ子レベルの数を増やすには、スコープまたはブロックを作成します。 たとえば、名前空間、ディレクティブの使用、プリプロセッサ拡張、テンプレート拡張、例外処理、ループ構造、および else-if 句のすべてが、コンパイラによって参照される入れ子レベルを増やすことができます。  
  
 このエラーを解決するには、コードをリファクタリングする必要があります。 いずれにしても、入れ子のレベルが深いコードはわかりにくく、推論も困難です。 コードをリファクタリングして入れ子レベルを減らすと、コードの品質が向上し、保守しやすくなる場合があります。 まず、入れ子のレベルが深いコードを、元のコンテキストから呼び出される関数に分割します。 そして、ブロック内のループまたはチェーンされた else-if 句の数を制限します。
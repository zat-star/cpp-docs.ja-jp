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
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 57766a4ff0b58fdc599a7124e217892e4b28539d
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1061"></a>致命的なエラー C1061
コンパイラの制限 : プログラム内のブロックの入れ子のレベルが深すぎます。  
  
 コード内のブロックの入れ子レベルが、制限値 128 を超えています。 これは、32 ビットおよび 64 ビットのツール セットにおける、C と C++ の両方のコンパイラのハード リミットです。 入れ子レベルの数を増やすには、スコープまたはブロックを作成します。 たとえば、名前空間、ディレクティブの使用、プリプロセッサ拡張、テンプレート拡張、例外処理、ループ構造、および else-if 句のすべてが、コンパイラによって参照される入れ子レベルを増やすことができます。  
  
 このエラーを解決するには、コードをリファクタリングする必要があります。 いずれにしても、入れ子のレベルが深いコードはわかりにくく、推論も困難です。 コードをリファクタリングして入れ子レベルを減らすと、コードの品質が向上し、保守しやすくなる場合があります。 まず、入れ子のレベルが深いコードを、元のコンテキストから呼び出される関数に分割します。 そして、ブロック内のループまたはチェーンされた else-if 句の数を制限します。

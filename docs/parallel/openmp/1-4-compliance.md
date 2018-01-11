---
title: "1.4 コンプライアンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d3fca67cb50cf91195d7edfb1e5e2fccfc9f8c5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="14-compliance"></a>1.4 準拠
OpenMP C と C++ API の実装は*OpenMP 準拠*かどうかを認識し、章 1、2、3、4、レイアウトとは、この仕様のすべての要素のセマンティクスを保持および付録 C A、B、D、E、および F情報は、目的でのみと仕様の一部ではないです。 API のサブセットのみを含む実装は、OpenMP 準拠ではありません。  
  
 OpenMP C および C++ API、実装でサポートされているベース言語拡張であります。 基本言語は、このドキュメントで言語コンストラクトまたは表示される拡張機能をサポートしない場合、OpenMP の実装をサポートするように必要はありません。  
  
 すべての C および C++ の標準ライブラリ関数および組み込み関数 (つまり、コンパイラが特定のナレッジには、関数) のスレッド セーフである必要があります。 並行領域内の別のスレッドでスレッド セーフである関数の非同期の使用には、未定義の動作は生成されません。 ただし、動作はありませんシリアル領域のものと同じです。 (ランダムな番号生成関数は、例を示します)。  
  
 OpenMP C と C++ API では、特定の動作は、ことを指定します*実装で定義します。* OpenMP に準拠した実装を定義し、このような場合は、その動作を文書化する必要があります。 参照してください[付録 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md)、実装定義の動作の一覧については、97 のページです。
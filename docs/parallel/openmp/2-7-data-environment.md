---
title: "2.7 データ環境 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e018a2c1b20bef640852ced913dc90266e733c06
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="27-data-environment"></a>2.7 データ環境
このセクションでは、ディレクティブと次のように、並行領域の実行中に、データの環境を制御するためのいくつかの句が表示されます。  
  
-   A **threadprivate**するため、ファイル スコープ、名前空間スコープ、または静的ブロック スコープ変数をこのスレッドにローカル ディレクティブのものは (次のセクションを参照してください)。  
  
-   属性を制御、共有変数の並列または work-sharing コンス トラクターの実行中のディレクティブで指定できる句は「[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 ページ。
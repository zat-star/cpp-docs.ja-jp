---
title: "リンカー ツールの警告 LNK4102 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4102
dev_langs: C++
helpviewer_keywords: LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80efad60da9f6742110811a5cf4c12f07c7def67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4102"></a>リンカー ツールの警告 LNK4102
削除するデストラクター 'name';イメージは正しく動作しない可能性があります。  
  
 プログラムは削除するデストラクターをエクスポートしようとしています。 結果として得られる削除は、DLL の境界を越えて、プロセスが所有していないメモリを解放するように発生します。 特定のシンボルが、.def ファイルに表示されていないことと、シンボルがの引数として表示されていないことを確認してください、 **/インポート**または**/export**リンカーのコマンドラインでオプションです。  
  
 C ランタイム ライブラリを再構築する場合は、このメッセージを無視できます。
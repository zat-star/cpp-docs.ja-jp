---
title: "リンカ ツール エラー LNK1264 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1264
dev_langs: C++
helpviewer_keywords: LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f590de75998becb9c03c73ac3083b04445a02156
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1264"></a>リンカ ツール エラー LNK1264
指定された/LTCG:PGINSTRUMENT がコード生成は必要はありません。インストルメンテーションに失敗しました  
  
 **/LTCG:PGINSTRUMENT**でコンパイルされたなしの .obj ファイルが見つかりましたが、指定された[/GL](../../build/reference/gl-whole-program-optimization.md)です。 場所とリンクが失敗しました、インストルメンテーションを使用できません。 コンパイルでは、コマンドラインでの 1 つ以上の .obj ファイルが必要がある**/GL**インストルメンテーションを実行できるようにします。  
  
 最適化のガイド付きプロファイル (PGO) では、64 ビットのコンパイラで使用できるのみです。
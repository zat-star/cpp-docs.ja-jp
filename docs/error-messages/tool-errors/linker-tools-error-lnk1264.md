---
title: "リンカ ツール エラー LNK1264 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: 9
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
ms.openlocfilehash: 0d075c807a698e62b4d46fcbd39e660d3e39d469
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1264"></a>リンカ ツール エラー LNK1264
/LTCG: PGINSTRUMENT が指定されていますが、コードの生成は必要ありません。インストルメンテーションに失敗しました。  
  
 **/LTCG:PGINSTRUMENT**でコンパイルされたなしの .obj ファイルが見つかりましたが、指定された[/GL](../../build/reference/gl-whole-program-optimization.md)します。 インストルメンテーションは、場所とリンクが失敗しましたをとることはできません。 コンパイルでは、コマンドラインでの&1; つ以上の .obj ファイルがある**/GL**インストルメンテーションを実行できるようにします。  
  
 最適化のガイド付きプロファイル (PGO) では、64 ビット コンパイラでは使用のみです。

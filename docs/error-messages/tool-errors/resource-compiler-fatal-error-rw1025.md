---
title: "リソース コンパイラの致命的なエラー RW1025 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW1025
dev_langs: C++
helpviewer_keywords: RW1025
ms.assetid: 561a02af-e7e0-442a-8ad3-a00b2ca1b62e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6e8b8ced110b13b65d91f968e476b5d20cf93c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-fatal-error-rw1025"></a>リソース コンパイラの致命的なエラー RW1025
相手側のヒープのメモリ不足  
  
 いる可能性がある領域が過度のメモリに常駐するソフトウェアを確認します。 CHKDSK プログラムを使用して、必要があるメモリの量を確認します。  
  
 サイズの大きいリソース ファイルを作成する場合は、2 つのファイルにリソース スクリプトを分割します。 2 つの .res ファイルを作成した後にに結合するのに MS-DOS コマンドラインを使用します。  
  
```  
copy first.res /b + second.res /b full.res  
```
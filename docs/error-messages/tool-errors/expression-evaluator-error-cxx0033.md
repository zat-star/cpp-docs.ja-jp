---
title: "式エバリュエーター エラー CXX0033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0033
dev_langs: C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 618dbe464adc64f36e35b9c329eb476166b8b5e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0033"></a>式エバリュエーター エラー CXX0033
OMF の型についてのエラー  
  
 実行可能ファイルには、デバッグの有効なオブジェクト モジュール形式 (OMF) がありませんでした。  
  
 このエラーは、can0033 と同じものと同じです。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  実行可能ファイルは、このバージョンの Visual C リンカーによって作成されませんでした。 LINK.exe の現在のバージョンを使用してオブジェクト コードを再リンクします。  
  
2.  .Exe ファイルが壊れている可能性があります。 再コンパイルし、プログラムを再リンクします。
---
title: "コンパイラの警告 C4962 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4962
dev_langs: C++
helpviewer_keywords: C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da57dfd020b1763d0749f66098a17c37a722a44d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4962"></a>コンパイラの警告 C4962
'function' : 最適化によってプロファイル データに矛盾が生じたため、ガイド付き最適化のプロファイルを無効にします。  
  
 関数のカウント (プロファイル) データの信頼性が低かったため、この関数は /LTCG:PGO を指定してコンパイルされませんでした。 その関数の信頼性の低いプロファイル データを格納している .pgc ファイルを再生成するためにプロファイリングを再実行します。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。
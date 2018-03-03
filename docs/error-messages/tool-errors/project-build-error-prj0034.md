---
title: "プロジェクト ビルド エラー PRJ0034 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0034
dev_langs:
- C++
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e68097d234519cdea75875d355ef798672ad4b22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0034"></a>プロジェクト ビルド エラー PRJ0034
プロジェクト レベルのカスタムの ' Additional Dependencies プロパティは、手順が含まれている 'macro' 評価を出す 'macro_expansion' を作成します。  
  
 プロジェクトでカスタム ビルド ステップには、おそらくマクロ評価の問題により、追加の依存関係のエラーが含まれています。 このエラー意味する場合も、パスの形式が文字またはファイル パスに無効な文字の組み合わせを含むです。  
  
 このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。
---
title: "プロジェクト ビルド エラー PRJ0032 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0032
dev_langs:
- C++
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92497027db3a2449914696f03fc86a144a48b62e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0032"></a>プロジェクト ビルド エラー PRJ0032
プロジェクト レベルのカスタム ビルド ステップの 'Outputs' プロパティには、評価を出す 'macro_expansion' の ' macro' が含まれています。  
  
 プロジェクトでカスタム ビルド ステップには、おそらくマクロ評価の問題により、不正な出力が必要があります。 このエラー意味する場合も、パスの形式が文字またはファイル パスに無効な文字の組み合わせを含むです。  
  
 このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。
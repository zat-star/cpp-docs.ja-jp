---
title: "プロジェクト ビルド エラー PRJ0032 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0032
dev_langs: C++
helpviewer_keywords: PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3ea007346793f8d06ac85f20649b7d348014e17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0032"></a>プロジェクト ビルド エラー PRJ0032
プロジェクト レベルのカスタム ビルド ステップの 'Outputs' プロパティには、評価を出す 'macro_expansion' の ' macro' が含まれています。  
  
 プロジェクトでカスタム ビルド ステップには、おそらくマクロ評価の問題により、不正な出力が必要があります。 このエラー意味する場合も、パスの形式が文字またはファイル パスに無効な文字の組み合わせを含むです。  
  
 このエラーを解決するには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。
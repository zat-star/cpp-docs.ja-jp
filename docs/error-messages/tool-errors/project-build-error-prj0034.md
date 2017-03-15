---
title: "プロジェクト ビルド エラー PRJ0034 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- PRJ0034
dev_langs:
- C++
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
caps.latest.revision: 6
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0c4b9e5fc6c2b80729df021f439f537d60b34501
ms.lasthandoff: 02/24/2017

---
# <a name="project-build-error-prj0034"></a>プロジェクト ビルド エラー PRJ0034
追加依存関係 プロパティの中で、プロジェクト レベルのカスタム ビルド ステップが含まれている 'マクロ' を 'macro_expansion' として評価されます。  
  
 プロジェクトでカスタム ビルド ステップには、追加の依存マクロ評価の問題が原因と思わでエラーが含まれています。 このエラーにパスを正しくない形式して、文字またはファイルのパスに無効な文字の組み合わせを含むもします。  
  
 このエラーを解決するのには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。

---
title: "コンパイラの警告 C4962 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4962
dev_langs:
- C++
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 9daeb42e0a6b0eea6d0f3e98656e3b0bd2416142
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4962"></a>コンパイラの警告 C4962
'function' : 最適化によってプロファイル データに矛盾が生じたため、ガイド付き最適化のプロファイルを無効にします。  
  
 関数のカウント (プロファイル) データの信頼性が低かったため、この関数は /LTCG:PGO を指定してコンパイルされませんでした。 その関数の信頼性の低いプロファイル データを格納している .pgc ファイルを再生成するためにプロファイリングを再実行します。  
  
 既定では、この警告はオフに設定されています。 詳細については、次を参照してください。[コンパイラの警告無効になっている既定](../../preprocessor/compiler-warnings-that-are-off-by-default.md)です。

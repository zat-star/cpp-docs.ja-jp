---
title: "式エバリュエーター エラー CXX0015 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 22b4db607b40f73cc5c240b7fd75f5230832ec0f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluator-error-cxx0015"></a>式エバリュエーター エラー CXX0015
式が複雑すぎます (スタック オーバーフロー)  
  
 入力された式は、複雑すぎるか、C の式エバリュエーターで使用できるストレージ量レベルが深すぎます入れ子になったでした。  
  
 オーバーフローは、通常、保留中の多数の計算のために発生します。  
  
 その他の部分式を計算するを待たずにするのではなくが検出すると、式の各コンポーネントを評価できるように、式のレイアウトを変更します。  
  
 式を複数のコマンドに分割します。  
  
 このエラーは、can0015 と同じものと同じです。

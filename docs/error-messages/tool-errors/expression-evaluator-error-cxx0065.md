---
title: "式エバリュエーター エラー CXX0065 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
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
ms.openlocfilehash: ff7093ee69dea3f39a37110bdc8076d1dc0e5cbe
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluator-error-cxx0065"></a>式エバリュエーター エラー CXX0065
変数にはスタック フレームが必要です  
  
 式には、現在のスコープ内に存在するが、まだ作成されていない変数が含まれています。  
  
 このエラーは、関数がまだ、関数のスタック フレームのセットアップのプロローグにステップ インする場合、または関数の終了コードにステップ インする場合に発生することができます。  
  
 までステップ実行、プロローグ コード式を評価する前に、スタック フレームが設定されてください。  
  
 このエラーは、can0065 と同じものと同じです。

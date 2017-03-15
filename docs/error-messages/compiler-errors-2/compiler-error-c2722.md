---
title: "コンパイラ エラー C2722 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2722
dev_langs:
- C++
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: 7
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
ms.openlocfilehash: 65bfd2b4f939d5dc59c5162b13251eb34896ed00
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2722"></a>コンパイラ エラー C2722
':: 演算子 ': 次の演算子のコマンドは正しくありません'演算子' を使用してください。  
  
 `operator`ステートメントの再定義`::new`または`::delete`です。 `new`と`delete`演算子はグローバルなため、スコープ解決演算子 (`::`) は意味がありません。 削除、`::`演算子。

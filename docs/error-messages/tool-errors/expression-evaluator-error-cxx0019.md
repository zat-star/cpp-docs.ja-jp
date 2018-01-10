---
title: "式エバリュエーター エラー CXX0019 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0019
dev_langs: C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c62391bb770a49810a87c52b2f75d5a0d4426fbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0019"></a>式エバリュエーター エラー CXX0019
不適切な型キャスト  
  
 C の式エバリュエーターでは、型キャストを実行できません。  
  
 このエラーは、can0019 と同じものと同じです。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  指定した型が不明です。  
  
2.  ポインター型のレベルが多すぎますが発生しました。 たとえば、型キャスト  
  
    ```  
    (char **)h_message  
    ```  
  
     C の式エバリュエーターによって評価できません。
---
title: "致命的なエラー C1045 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1045
dev_langs:
- C++
helpviewer_keywords:
- C1045
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: e2e060465ffca50b116aa7a7020d9e1bdda8f2de
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1045"></a>致命的なエラー C1045
コンパイラの制限 : 外部参照の入れ子のレベルがコンパイラの限界を超えています。  
  
 入れ子になった外部参照がコンパイラの制限を超えています。 入れ子になった外部参照は、 `extern` "C++" などの外部リンケージの種類で許可されます。 エラーを解決するには、入れ子になった外部参照の数を減らします。

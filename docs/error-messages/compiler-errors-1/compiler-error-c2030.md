---
title: "コンパイラ エラー C2030 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: c76a4fc5de139c2cc9f6802fc66526f291b862a2
ms.contentlocale: ja-jp
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2030"></a>コンパイラ エラー C2030
アクセシビリティが 'protected private' であるデストラクターは、'sealed' として宣言されたクラスのメンバーになることはできません  
  
 `sealed` として宣言された Windows ランタイム クラスは、protected private デストラクターを持つことはできません。 sealed 型では、パブリック仮想デストラクターとプライベート非仮想デストラクターだけが許可されています。 詳細については、次を参照してください。 [Ref クラスと構造体](../../cppcx/ref-classes-and-structs-c-cx.md)です。  
  
 このエラーを解決するには、デストラクターのアクセシビリティを変更します。

---
title: "コンパイラ エラー C2030 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: b38e76d73cf6e933145d8d382b653b8a5ed1892e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2030"></a>コンパイラ エラー C2030
アクセシビリティが 'protected private' であるデストラクターは、'sealed' として宣言されたクラスのメンバーになることはできません  
  
 `sealed` として宣言された Windows ランタイム クラスは、protected private デストラクターを持つことはできません。 sealed 型では、パブリック仮想デストラクターとプライベート非仮想デストラクターだけが許可されています。 詳細については、次を参照してください。 [Ref クラスと構造体](http://msdn.microsoft.com/Library/3d736b82-0bf0-48cf-bac1-cc9d110b70d1)します。  
  
 このエラーを解決するには、デストラクターのアクセシビリティを変更します。

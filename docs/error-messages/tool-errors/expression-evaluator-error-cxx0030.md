---
title: "式エバリュエーター エラー CXX0030 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
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
ms.openlocfilehash: 4a4e82e51943db988805f1ba76495218e8188d2e
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluator-error-cxx0030"></a>式エバリュエーター エラー CXX0030
評価できない式  
  
 書き込まれると、デバッガーの式エバリュエーターは式の値を取得できませんでした。 1 つの考えられる原因は、式が外部プログラムのアドレス空間にあるメモリを指すこと (1 つの例は、null ポインターを逆参照)。 Windows では、プログラムのアドレス空間の外部では、メモリにアクセスをできません。  
  
 評価の順序を制御するかっこを使用して、式を書き直すことができます。  
  
 このエラーは、can0030 と同じものと同じです。

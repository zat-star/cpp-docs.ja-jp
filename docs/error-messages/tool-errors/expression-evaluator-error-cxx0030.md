---
title: "式エバリュエーター エラー CXX0030 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0030
dev_langs: C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb120103714c3711fb059fa736398458209b52a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0030"></a>式エバリュエーター エラー CXX0030
評価できない式  
  
 書き込まれると、デバッガーの式エバリュエーターは式の値を取得できませんでした。 1 つの考えられる原因は、式が外部プログラムのアドレス空間にあるメモリを指すこと (1 つの例では null ポインターの逆参照)。 Windows は、プログラムのアドレス空間の外部では、メモリへのアクセスを許可しません。  
  
 評価の順序を制御するかっこを使用して、式を書き直すことができます。  
  
 このエラーは、can0030 と同じものと同じです。
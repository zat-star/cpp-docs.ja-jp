---
title: "致命的なエラー C1190 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1190
dev_langs:
- C++
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1b04b08bd57a527145cafde1073430a78d68b89b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1190"></a>致命的なエラー C1190
マネージ ターゲット コードには '/clr' が必要です。  
  
 CLR コンストラクトを使用していますが、 **/clr**を指定していませんでした。  
  
 詳細については、「 [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 次の例では C1190 が生成されます。  
  
```  
// C1190.cpp  
// compile with: /c  
__gc class A {};   // C1190  
ref class A {};  
```

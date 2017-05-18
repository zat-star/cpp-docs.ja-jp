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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 39c30c3f6d2c923e585a4581164734c3aa63eae5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1190"></a>致命的なエラー C1190
マネージ ターゲット コードには '/clr' が必要です。  
  
 CLR コンストラクトを使用していますが、 **/clr**を指定していませんでした。  
  
 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 次の例では C1190 が生成されます。  
  
```  
// C1190.cpp  
// compile with: /c  
__gc class A {};   // C1190  
ref class A {};  
```

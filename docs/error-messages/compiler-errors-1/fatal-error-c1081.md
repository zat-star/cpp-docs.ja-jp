---
title: "致命的なエラー C1081 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 8
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
ms.openlocfilehash: 39c3a48e3fa01eb9bf2f357df73ef0bb466d1b10
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1081"></a>致命的なエラー C1081
'symbol': ファイル名が長すぎます  
  
 ファイルのパス名の長さを超えています`_MAX_PATH`(260 文字として STDLIB.h で定義されます)。 ファイルの名前を短きます。  
  
 短いファイル名を持つ CL.exe を呼び出した場合、コンパイラは、完全なパス名を生成する必要があります。 たとえば、`cl -c myfile.cpp`を生成するコンパイラが発生する可能性があります。  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```

---
title: "stdin、stdout、stderr |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdin
- stderr
- stdout
dev_langs:
- C++
helpviewer_keywords:
- stdout function
- standard output stream
- standard error stream
- stdin function
- standard input stream
- stderr function
ms.assetid: badd4735-596d-4498-857c-ec8b7e670e4c
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 331b60a8cd06e42c032c6d8c81b58b8e4f4501ae
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="stdin-stdout-stderr"></a>stdin、stdout、stderr
## <a name="syntax"></a>構文  
  
```  
  
      FILE *stdin;   
FILE *stdout;   
FILE *stderr;   
#include <stdio.h>  
```  
  
## <a name="remarks"></a>コメント  
 これらは、入力、出力、エラー出力の標準ストリームです。  
  
 既定では、標準入力はキーボードから読み取られ、標準出力と標準エラーは画面に出力されます。  
  
 標準ストリームにアクセスするには、次のストリーム ポインターを使用できます。  
  
|ポインター|ストリーム|  
|-------------|------------|  
|`stdin`|標準入力|  
|**stdout**|標準出力|  
|`stderr`|標準エラー|  
  
 これらのポインターは、関数への引数として使用できます。 **getchar** や `putchar` などのいくつかの関数では、`stdin` と **stdout** が自動的に使用されます。  
  
 これらのポインターは定数であり、新しい値を割り当てることはできません。 ディスク ファイルやその他のデバイスにストリームをリダイレクトするには、`freopen` 関数を使用できます。 オペレーティング システムでは、プログラムの標準入力と出力をコマンド レベルでリダイレクトすることができます。  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../c-runtime-library/stream-i-o.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)

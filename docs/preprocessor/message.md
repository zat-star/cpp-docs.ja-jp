---
title: "メッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs: C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad91fdc0fb024fe87c2096f91962f715c0835262
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="message"></a>message
コンパイルを終了せずに、標準出力に文字列リテラルを送信します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma message( messagestring )  
```  
  
## <a name="remarks"></a>コメント  
 一般的な使用、**メッセージ**プラグマは、コンパイル時に情報メッセージを表示します。  
  
 *Messagestring*パラメーターは、リテラル、文字列に展開されるマクロを指定でき、こうしたマクロと文字列リテラルの任意の組み合わせを連結することができます。  
  
 定義済みマクロを使用する場合、**メッセージ**プラグマ マクロが文字列を返す必要があります、それ以外の場合、マクロの出力を文字列に変換する必要があります。  
  
 次のコード片では、**メッセージ**プラグマはコンパイル時にメッセージを表示します。  
  
```  
// pragma_directives_message1.cpp  
// compile with: /LD  
#if _M_IX86 >= 500  
#pragma message("_M_IX86 >= 500")  
#endif  
  
#pragma message("")  
  
#pragma message( "Compiling " __FILE__ )   
#pragma message( "Last modified on " __TIMESTAMP__ )  
  
#pragma message("")  
  
// with line number  
#define STRING2(x) #x  
#define STRING(x) STRING2(x)  
  
#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")  
  
#pragma message("")  
```  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
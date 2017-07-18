---
title: "インライン関数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- fast code
- inline functions, __inline keyword
- functions [C++], inline functions
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: cdcf109b76725855aeb6daae1628bbc6a57e6e32
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="inline-functions"></a>インライン関数
**Microsoft 固有の仕様**  
  
 `__inline` キーワードは、関数呼び出しのすべてのインスタンスを、関数定義内のコードに置き換えるようコンパイラに指示します。 ただし、実際に置き換えるかどうかは、コンパイラの判断に任されています。 たとえば、関数のアドレスが取得されている場合、または、関数が大きすぎてインライン展開できない場合、関数はインライン展開されません。  
  
 関数をインライン展開の候補とするには、新しいスタイルの関数定義を使用する必要があります。  
  
 インライン関数を指定するには、この形式を使用します。  
  
 `__inline` *type*opt*function-definition*`;`  
  
 インライン関数を使用すると、次の理由により、同等の関数呼び出しで生成されるコードよりも速いコードが生成され、ときにはサイズが小さくなることもあります。  
  
-   関数呼び出しを実行するために必要な時間が短縮されます。  
  
-   引数と戻り値を処理するコードが生成されないため、小さなインライン関数 (およそ 3 行以下) であれば、同等の関数呼び出しよりも生成されるコードが小さくなります。  
  
-   コンパイラでは関数を超えた最適化が実行されないため、通常の関数呼び出しではコード最適化の対象になりませんが、インライン展開された関数はコード最適化の対象になります。  
  
 `__inline` を使用する関数を、インライン アセンブラー コードと混同しないでください。 詳細については、「[インライン アセンブラー](../c-language/inline-assembler-c.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## <a name="see-also"></a>関連項目  
 [inline、__inline、\__forceinline](../cpp/inline-functions-cpp.md)



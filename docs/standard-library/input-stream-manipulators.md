---
title: "入力ストリーム マニピュレーター | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e1c7e8f5e1075230f008e4cb5f9a6ac843c75502
ms.lasthandoff: 02/24/2017

---
# <a name="input-stream-manipulators"></a>入力ストリーム マニピュレーター
[setprecision]--brokenlink--(../Topic/not%20found:3ddde610-70cc-4cfa-8a89-3e83d1d356a8.md#setprecision) などの多くのマニピュレーターは、`ios` クラスに対して定義されており、入力ストリームに適用されます。 ただし、入力ストリーム オブジェクトに実際に影響を与えるマニピュレーターはわずかです。 該当するマニピュレーターのうち最も重要なのは、入力ストリームからの数値で使用される変換ベースを決定する基数マニピュレーターの `dec`、`oct`、および `hex` です。  
  
 抽出時に、`hex` マニピュレーターでは、さまざまな入力形式を処理できます。 たとえば、c、C、0xc、0xC、0Xc、および 0XC は、すべて 10 進整数の 12 として解釈されます。 0 から 9、A から F、a から f、x、および X 以外の任意の文字によって、数値変換が終了されます。 したがって、シーケンス `"124n5"` は、[basic_ios::fail](../standard-library/basic-ios-class.md#basic_ios__fail) ビットが設定された数値 124 に変換されます。  
  
## <a name="see-also"></a>関連項目  
 [入力ストリーム](../standard-library/input-streams.md)



---
title: 入力ストリーム マニピュレーター | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 4f7542579ade578f449a621028d210186bcbbf8e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="input-stream-manipulators"></a>入力ストリーム マニピュレーター

多くのマニピュレーターなど[setprecision](../standard-library/iomanip-functions.md#setprecision)、用に定義された、`ios`クラス、つまり入力ストリームに適用します。 ただし、入力ストリーム オブジェクトに実際に影響を与えるマニピュレーターはわずかです。 該当するマニピュレーターのうち最も重要なのは、入力ストリームからの数値で使用される変換ベースを決定する基数マニピュレーターの `dec`、`oct`、および `hex` です。

抽出時に、`hex` マニピュレーターでは、さまざまな入力形式を処理できます。 たとえば、c、C、0xc、0xC、0Xc、および 0XC は、すべて 10 進整数の 12 として解釈されます。 0 から 9、A から F、a から f、x、および X 以外の任意の文字によって、数値変換が終了されます。 したがって、シーケンス `"124n5"` は、[basic_ios::fail](../standard-library/basic-ios-class.md#fail) ビットが設定された数値 124 に変換されます。

## <a name="see-also"></a>関連項目

[入力ストリーム](../standard-library/input-streams.md)<br/>

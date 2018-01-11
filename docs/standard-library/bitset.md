---
title: '&lt;bitset&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <bitset>
dev_langs: C++
helpviewer_keywords:
- <bitset> header
- bitset header
ms.assetid: af30a9b9-489e-46e3-9d29-5f3ea07ae6dc
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe8d012c0034354328e5a10f1fa977002639506b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ltbitsetgt"></a>&lt;bitset&gt;
ビットの固定サイズ シーケンスを表して処理するための、テンプレート クラス ビットセットと 2 つのサポート テンプレート関数を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#include <bitset>  
  
```  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator&](../standard-library/bitset-operators.md#op_amp)|次の 2 つのビットセット間でビットごとの AND を実行します。|  
|[operator<\<](../standard-library/bitset-operators.md#op_lt_lt)|ビット シーケンスのテキスト表現を標準出力ストリームに挿入します。|  
|[operator>>](../standard-library/bitset-operators.md#op_gt_gt)|ビット シーケンスのテキスト表現を標準入力ストリームに挿入します。|  
|[operator^](../standard-library/bitset-operators.md#op_xor)|次の 2 つのビットセット間でビットごとの EXCLUSIVE-OR を実行します。|  
|[operator&#124;](../standard-library/bitset-operators.md#op_or)|次の 2 つのビットセット間でビットごとの OR を実行します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[bitset クラス](../standard-library/bitset-class.md)|このテンプレート クラスは、固定数のビットで構成されるシーケンスを格納するオブジェクト型を記述します。これらのビットによって、一連の項目または条件のフラグを保持するためのコンパクトな方法が提供されます。|  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




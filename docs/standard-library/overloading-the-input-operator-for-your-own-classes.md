---
title: "独自クラスの &gt;&gt; 演算子のオーバーロード | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fb029ee7e20a50ef00c2902bda0cca9fb48dbe2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>独自クラスの &gt;&gt; 演算子のオーバーロード
入力ストリームは、標準型に抽出 (`>>`) 演算子を使用します。 独自の型に同様の抽出演算子を記述できます。空白を正確に使用することにより、演算子は適切に機能します。  
  
 ここでは、前に示した `Date` クラスの抽出演算子の例を示します。  
  
```  
istream& operator>> (istream& is, Date& dt)  
{  
    is>> dt.mo>> dt.da>> dt.yr;  
    return is;  
}  
```  
  
## <a name="see-also"></a>参照  
 [入力ストリーム](../standard-library/input-streams.md)


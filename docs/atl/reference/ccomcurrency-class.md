---
title: "CComCurrency クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComCurrency"
  - "ATL.CComCurrency"
  - "ATL::CComCurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCurrency クラス"
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComCurrency クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComCurrency` には、CURRENCY オブジェクトを作成および管理するためのメソッドと演算子があります。  
  
## 構文  
  
```  
  
class CComCurrency  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComCurrency::CComCurrency](../Topic/CComCurrency::CComCurrency.md)|`CComCurrency` オブジェクトのコンストラクター。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComCurrency::GetCurrencyPtr](../Topic/CComCurrency::GetCurrencyPtr.md)|`m_currency` データ メンバーのアドレスを返します。|  
|[CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md)|`CComCurrency` オブジェクトの小数部を返すには、このメソッドを呼び出します。|  
|[CComCurrency::GetInteger](../Topic/CComCurrency::GetInteger.md)|`CComCurrency` オブジェクトの整数部を返すには、このメソッドを呼び出します。|  
|[CComCurrency::Round](../Topic/CComCurrency::Round.md)|`CComCurrency` オブジェクトを最も近い整数値に四捨五入するには、このメソッドを呼び出します。|  
|[CComCurrency::SetFraction](../Topic/CComCurrency::SetFraction.md)|`CComCurrency` オブジェクトの小数部を設定するには、このメソッドを呼び出します。|  
|[CComCurrency::SetInteger](../Topic/CComCurrency::SetInteger.md)|`CComCurrency` オブジェクトの整数部を設定するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CComCurrency::operator \-](../Topic/CComCurrency::operator%20-2.md)|この演算子は、`CComCurrency` オブジェクトで減算を実行するために使用します。|  
|[CComCurrency::operator \!\=](../Topic/CComCurrency::operator%20!=.md)|2 つの `CComCurrency` オブジェクトが等しくないかどうかを比較します。|  
|[CComCurrency::operator \*](../Topic/CComCurrency::operator%20*.md)|この演算子は、`CComCurrency` オブジェクトで乗算を実行するために使用します。|  
|[CComCurrency::operator \*\=](../Topic/CComCurrency::operator%20*=.md)|この演算子は、`CComCurrency` オブジェクトで乗算を実行し、オブジェクトに結果を代入するために使用します。|  
|[CComCurrency::operator \/](../Topic/CComCurrency::operator%20-1.md)|この演算子は、`CComCurrency` オブジェクトで除算を実行するために使用します。|  
|[CComCurrency::operator \/\=](../Topic/CComCurrency::operator%20-=2.md)|この演算子は、`CComCurrency` オブジェクトで除算を実行し、オブジェクトに結果を代入するために使用します。|  
|[CComCurrency::operator \+](../Topic/CComCurrency::operator%20+.md)|この演算子は、`CComCurrency` オブジェクトで加算を実行するために使用します。|  
|[CComCurrency::operator \+\=](../Topic/CComCurrency::operator%20+=.md)|この演算子は、`CComCurrency` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。|  
|[CComCurrency::operator \<](../Topic/CComCurrency::operator%20%3C.md)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、小さい方を決定します。|  
|[CComCurrency::operator \<\=](../Topic/CComCurrency::operator%20%3C=.md)|この演算子では、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。|  
|[CComCurrency::operator \=](../Topic/CComCurrency::operator%20=.md)|この演算子は、`CComCurrency` オブジェクトに新しい値を割り当てます。|  
|[CComCurrency::operator \-\=](../Topic/CComCurrency::operator%20-=1.md)|この演算子は、`CComCurrency` オブジェクトで減算を実行し、オブジェクトに結果を代入するために使用します。|  
|[CComCurrency::operator \=\=](../Topic/CComCurrency::operator%20==.md)|この演算子は、2 つの `CComCurrency` オブジェクトが等しいかどうかを比較します。|  
|[CComCurrency::operator \>](../Topic/CComCurrency::operator%20%3E.md)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、大きい方を決定します。|  
|[CComCurrency::operator \>\=](../Topic/CComCurrency::operator%20%3E=.md)|この演算子は、2 つの `CComCurrency` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。|  
|[CComCurrency::operator CURRENCY](../Topic/CComCurrency::operator%20CURRENCY.md)|`CURRENCY` オブジェクトをキャストします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComCurrency::m\_currency](../Topic/CComCurrency::m_currency.md)|クラス インスタンスによって作成された `CURRENCY` 変数。|  
  
## 解説  
 `CComCurrency` は、**CURRENCY** データ型のラッパーです。  **CURRENCY** は、10,000 倍した値を 8 バイトの 2 の補数で表現した整数値として実装されます。  これは、15 桁の整数部と 4 桁の小数部を持つ固定小数点数として表現されます。  **CURRENCY** データ型は、通貨に関連する計算、または精度が重要となる固定小数点数の計算に非常に役立ちます。  
  
 **CComCurrency** ラッパーは、この固定小数点型の算術演算、代入演算、および比較演算を実装します。  固定小数点数の計算中に発生する可能性のある丸め誤差を制御するために、サポートするアプリケーションが選択されています。  
  
 `CComCurrency` オブジェクトは、小数点の左側に値を格納する整数部と小数点の右側に値を格納する小数部という 2 つの構成要素を使用した形で、小数点の左側と右側の数値にアクセスできます。  小数部は、\-9999 \(**CY\_MIN\_FRACTION**\) から \+9999 \(**CY\_MAX\_FRACTION**\) までの整数値として内部に格納されます。  [CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md) メソッドは、係数 10,000 \(**CY\_SCALE**\) で拡大された値を返します。  
  
 **CComCurrency**  オブジェクトの整数部と小数部を指定した場合は、小数部が 0 ～ 9999 の数値であることに注意してください。  これは、小数点の後の有効桁数に 2 桁のみを使用して金額を表す米ドルなどの通貨を扱う場合に重要です。  最後の 2 桁が表示されていない場合でも考慮する必要があります。  
  
|値|考えられる CComCurrency の割り当て|  
|-------|------------------------------|  
|$10.50|CComCurrency\(10,5000\) *または* CComCurrency\(10.50\)|  
|$10.05|CComCurrency\(10,500\) *または* CComCurrency\(10.05\)|  
  
 値  **CY\_MIN\_FRACTION**、**CY\_MAX\_FRACTION**、および  **CY\_SCALE** は、atlcur.h で定義されています。  
  
## 必要条件  
 **ヘッダー:** atlcur.h  
  
## 参照  
 [COleCurrency クラス](../Topic/COleCurrency%20Class.md)   
 [CURRENCY](http://msdn.microsoft.com/ja-jp/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [クラスの概要](../../atl/atl-class-overview.md)
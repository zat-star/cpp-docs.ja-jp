---
title: "_variant_t クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Variant"
  - "_variant_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_variant_t クラス"
  - "_variant_t クラス, メンバー関数"
  - "_variant_t クラス, 演算子"
  - "VARIANT オブジェクト"
  - "VARIANT オブジェクト, COM のカプセル化"
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# _variant_t クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_variant_t` オブジェクトは、`VARIANT` データ型をカプセル化します。  このクラスは、リソースの割り当てと解放を管理し、適切な **VariantInit** 関数と **VariantClear** 関数を呼び出します。  
  
### 構築  
  
|||  
|-|-|  
|[\_variant\_t](../Topic/_variant_t::_variant_t.md)|`_variant_t` オブジェクトを構築します。|  
  
### 操作  
  
|||  
|-|-|  
|[Attach](../cpp/variant-t-attach.md)|`_variant_t` オブジェクトに **VARIANT** オブジェクトをアタッチします。|  
|[Clear](../cpp/variant-t-clear.md)|カプセル化された **VARIANT** オブジェクトをクリアします。|  
|[ChangeType](../Topic/_variant_t::ChangeType.md)|`_variant_t` オブジェクトの型を、指定された **VARTYPE** に変更します。|  
|[Detach](../cpp/variant-t-detach.md)|この `_variant_t` オブジェクトからカプセル化された **VARIANT** オブジェクトをデタッチします。|  
|[SetString](../cpp/variant-t-setstring.md)|この `_variant_t` オブジェクトに文字列を代入します。|  
  
### 演算子  
  
|||  
|-|-|  
|[Operator \=](../cpp/variant-t-operator-equal.md)|既存の `_variant_t` オブジェクトに新しい値を代入します。|  
|[operator \=\=、\!\=](../cpp/variant-t-relational-operators.md)|2 つの `_variant_t` オブジェクトを比較して、等しいかどうかを確認します。|  
|[抽出](../cpp/variant-t-extractors.md)|カプセル化された **VARIANT** オブジェクトからデータを抽出します。|  
  
## END Microsoft 固有の仕様  
  
## 要件  
 **ヘッダー:** comutil.h  
  
 **ライブラリ:** comsuppw.lib または comsuppwd.lib \(詳細については、「[\/Zc:wchar\_t \(wchar\_t をネイティブ型として認識\)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)」を参照\)  
  
## 参照  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)
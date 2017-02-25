---
title: "_variant_t 抽出 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t.operatordouble"
  - "operatorlong"
  - "_variant_t::operator_bstr_t"
  - "operatordouble"
  - "_variant_t.operatorCY"
  - "operatorCY"
  - "_variant_t::operatorCY"
  - "_variant_t::operatordouble"
  - "operatorfloat"
  - "operatorBYTE"
  - "_variant_t.operatorDECIMAL"
  - "_variant_t::operatorlong"
  - "operatorIDispatch"
  - "_variant_t.operatorBYTE"
  - "operatorDECIMAL"
  - "_variant_t.operator_bstr_t"
  - "_variant_t::operatorDECIMAL"
  - "_variant_t.operatorIUnknown"
  - "_variant_t.operatorlong"
  - "_variant_t::operatorIDispatch"
  - "_variant_t::operatorIUnknown"
  - "operatorIUnknown"
  - "_variant_t.operatorbool"
  - "_variant_t::operatorBYTE"
  - "_variant_t.operatorfloat"
  - "operator_bstr_t"
  - "_variant_t::operatorbool"
  - "operatorshort"
  - "_variant_t::operatorshort"
  - "_variant_t::operatorfloat"
  - "_variant_t.operatorIDispatch"
  - "_variant_t.operatorshort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "抽出, _variant_t クラス"
  - "operator _bstr_t"
  - "演算子 bool"
  - "演算子 BYTE"
  - "演算子 CY"
  - "演算子 DECIMAL"
  - "演算子 double"
  - "演算子 float"
  - "演算子 IDispatch"
  - "演算子 IUnknown"
  - "演算子 long"
  - "SHORT 演算子"
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _variant_t 抽出
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 カプセル化された **VARIANT** オブジェクトからデータを抽出します。  
  
## 構文  
  
```  
  
      operator short( ) const;   
operator long( ) const;   
operator float( ) const;   
operator double( ) const;   
operator CY( ) const;   
operator _bstr_t( ) const;   
operator IDispatch*( ) const;   
operator bool( ) const;   
operator IUnknown*( ) const;   
operator DECIMAL( ) const;   
operator BYTE( ) const;  
operator VARIANT() const throw();  
operator char() const;  
operator unsigned short() const;  
operator unsigned long() const;  
operator int() const;  
operator unsigned int() const;  
operator __int64() const;  
operator unsigned __int64() const;  
```  
  
## 解説  
 カプセル化された **VARIANT** オブジェクトから生データを抽出します。  **VARIANT** が適切な型になっていない場合、**VariantChangeType** が変換を実行するために使用され、失敗するとエラーが発生します。  
  
-   **operator short\( \) short** 整数値を抽出します。  
  
-   **operator long\( \) long** 整数値を抽出します。  
  
-   **operator float\( \) float** 数値を抽出します。  
  
-   **operator double\( \) double** 数値を抽出します。  
  
-   **operator CY\( \) CY** オブジェクトを抽出します。  
  
-   **operator bool\( \)** `bool` 値を抽出します。  
  
-   **operator DECIMAL\( \) DECIMAL** 値を抽出します。  
  
-   **operator BYTE\( \) BYTE** 値を抽出します。  
  
-   **operator \_bstr\_t\( \)** `_bstr_t` オブジェクトにカプセル化された文字列を抽出します。  
  
-   **operator IDispatch\*\( \)** カプセル化された **VARIANT** からディスパッチ インターフェイス ポインターを抽出します。  `AddRef` が結果のポインターから呼び出されるため、それを解放する **Release** を呼び出す必要があります。  
  
-   **operator IUnknown\*\( \)** カプセル化された **VARIANT** から COM インターフェイス ポインターを抽出します。  `AddRef` が結果のポインターから呼び出されるため、それを解放する **Release** を呼び出す必要があります。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_variant\_t クラス](../cpp/variant-t-class.md)
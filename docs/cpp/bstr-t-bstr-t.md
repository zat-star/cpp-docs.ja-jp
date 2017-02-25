---
title: "_bstr_t::_bstr_t | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::_bstr_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_bstr_t クラス"
  - "_bstr_t メソッド"
  - "BSTR オブジェクト"
ms.assetid: 116d994e-5a72-4351-afbe-866c80b4c165
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# _bstr_t::_bstr_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_bstr_t` オブジェクトを構築します。  
  
## 構文  
  
```  
_bstr_t( ) throw( );   
_bstr_t(  
   const _bstr_t& s1   
) throw( );  
_bstr_t(  
   const char* s2   
);  
_bstr_t(  
   const wchar_t* s3   
);  
_bstr_t(  
   const _variant_t& var   
);  
_bstr_t(  
   BSTR bstr,  
   bool fCopy   
);  
```  
  
#### パラメーター  
 `s1`  
 コピーされる `_bstr_t` オブジェクト。  
  
 `s2`  
 マルチバイト文字列。  
  
 `s3`  
 Unicode 文字列。  
  
 `var`  
 [\_variant\_t](../cpp/variant-t-class.md) オブジェクト。  
  
 `bstr`  
 既存の `BSTR` オブジェクト。  
  
 `fCopy`  
 `false` の場合、`SysAllocString` を呼び出してコピーを作成せずに、`bstr` 引数が新しいオブジェクトにアタッチされます。  
  
## 解説  
 `_bstr_t` のコンストラクターについて次の表で説明します。  
  
|コンストラクター|説明|  
|--------------|--------|  
|`_bstr_t( )`|null の `BSTR` オブジェクトをカプセル化する、既定の `_bstr_t` オブジェクトを構築します。|  
|`_bstr_t( _bstr_t&`  `s1`  `)`|別のコピーとして `_bstr_t` オブジェクトを構築します。<br /><br /> これは*簡易*コピーであり、新しいカプセル化された `BSTR` オブジェクトを作成する代わりに、その参照カウントをインクリメントします。|  
|`_bstr_t( char*`  `s2`  `)`|`SysAllocString` を呼び出して新しい `BSTR` オブジェクトを作成することで `_bstr_t` オブジェクトを構築し、そのオブジェクトをカプセル化します。<br /><br /> このコンストラクターは、マルチバイトから Unicode への変換を最初に実行します。|  
|`_bstr_t( wchar_t*`  `s3`  `)`|`SysAllocString` を呼び出して新しい `BSTR` オブジェクトを作成することで `_bstr_t` オブジェクトを構築し、そのオブジェクトをカプセル化します。|  
|`_bstr_t( _variant_t&`  `var`  `)`|最初に、カプセル化された VARIANT オブジェクトから `BSTR` オブジェクトを取得することによって、`_variant_t` オブジェクトから `_bstr_t` オブジェクトを構築します。|  
|`_bstr_t( BSTR`  `bstr` `, bool`  `fCopy`  `)`|\(`wchar_t*` 文字列ではなく\) 既存の `BSTR` から `_bstr_t` オブジェクトを構築します。  `fCopy` が false の場合、指定された `BSTR` オブジェクトは、`SysAllocString` を使って新しいコピーを作成せずに、新しいオブジェクトにアタッチされます。<br /><br /> このコンストラクターは、インターフェイス メソッドによって返される `BSTR` をカプセル化し、その所有権を得るために、タイプ ライブラリ ヘッダーのラッパー関数によって使用されます。|  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_bstr\_t クラス](../cpp/bstr-t-class.md)   
 [\_variant\_t クラス](../cpp/variant-t-class.md)